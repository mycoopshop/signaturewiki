File: HashedArrayTree.java
 * Author: Keith Schwarz (htiek@cs.stanford.edu)
 *
 * An implementation of the List abstraction backed by a hashed array tree
 * (HAT), a data structure supporting amortized O(1) lookup, append, and
 * last-element removal.  In this sense it is akin to a standard dynamic
 * array implementation.  However, a hashed array tree also has the advantage
 * that its memory overhead is only O(sqrt(n)) rather than the typical O(n)
 * found in dynamic arrays and their variants.
 *
 * Internally, the hashed array tree is implemented as an array of pointers
 * that optionally point to an array of elements.  The topmost array and each
 * element always have the same size, which is always a power of two.  In
 * this sense, the hashed array tree is essentially a two-dimensional array
 * of elements.  However, the advantage of the hashed array tree is that the
 * topmost array pointers are all initially null and only filled in when space
 * is needed.  This means that the maximum overhead of the structure is the
 * size of the topmost array, plus the number of unused elements in the current
 * block.  Here is one sample HAT:
 *
 *           [ ] [ ] [ ] [ ]
 *            |   |   |
 *            v   v   v
 *           [0] [4] [8]
 *           [1] [5] [9]
 *           [2] [6] [ ]
 *           [3] [7] [ ]
 *
 * Here, the topmost array of pointers has three pointers in use, each of which
 * point to an array of the corresponding number of elements.
 *
 * Whenever an element is added to a hashed array tree, one of three cases
 * must hold:
 *
 * 1. There is extra space at the end of the final subarray (for example, in
 *    the top picture).  In that case, the element is added to that position.
 * 2. The final subarray is full, but space for another subarray exists in the
 *    topmost array.  In that case, a new array is allocated and the element
 *    is added to that array.
 * 3. The final subarray is full and no new arrays remain open.  In that case,
 *    since the topmost array has size 2^n and each array has size 2^n, there
 *    must be a total of 2^(2n) elements in the hashed array tree.  We
 *    next double the size of the topmost array to 2^(n + 1), then allocate
 *    2^(n - 1) subarrays of size 2^(n + 1) elements for a total of 2^(2n)
 *    elements' worth of space.  The elements from the old HAT are then copied
 *    over, a new array is allocated for the new element, and it is added as
 *    the first element of that array.
 *
 * Let's now talk about the performance and memory usage of this structure.
 * First, we note that we can perform lookups in O(1), assuming that the
 * machine is transdichotomous (meaning that a single machine word can hold
 * the size of any array).  This can be done by breaking the input index in
 * half, then using the first half to choose which array to look into (the
 * "hashed" part of HAT) and the second half to choose which index to select.
 * This trick is similar to the trick used to represent a two-dimensional
 * array using a linear structure.
 *
 * Next, let's think about how much time it takes to do an append operation.
 * Each append when space remains takes O(1) to look up the proper position
 * in the hashed array tree for writing, but appends can be much more expensive
 * when the HAT needs to be resized.  Fortunately, this does not happen very
 * often.  Whenever the HAT doubles in size, its capacity grows from 2^(2n) to
 * 2^(2n + 2), meaning that four times as many elements must be inserted before
 * the next copy operation.  If we define a potential function as twice the 
 * number of filled-in elements in the HAT above half capacity (i.e. the
 * number of elements in the arrays in the second half), then we can prove an
 * amortized O(1) time for append.  Consider any series of appends.  If the
 * append does not expand the HAT, then it takes O(1) time and increases the
 * potential by 1/2.  If the append does expand the HAT, and the HAT's topmost
 * array has size 2^n, then there must be 2^(n-1) elements in the latter half
 * of the HAT, so the potential is 2^(2n).  The time required to move each
 * of the 2^(2n) elements is 2^(2n), and in the new HAT there are no elements
 * in the latter half of the array.  Consequently, the new potential is zero.
 * The actual time required to perform the append is thus 2^2n + O(1), and
 * the decrease in potential is -2^2n, so the amortized cost is O(1) as
 * expected.
 *
 * Last, let's talk about the cost to do a remove.  This is similar to the 
 * append case - we delete the last element of the last array, removing the
 * array from the topmost array if it becomes empty.  We also compact the
 * HAT if it becomes too sparse by shrinking from a HAT of size 2^(2n + 2) to
 * a HAT of size 2^(2n) if the HAT becomes one-eighth full.  A similar
 * potential method can be used to show that this operation runs in amortized
 * O(1).
 *
 * Finally, let's consider the memory overhead of the HAT.  For any HAT of
 * topmost array size 8 or more, since the HAT is always at least one-eighth
 * full, there must be at least one full array.  This array has size equal to
 * the size of the topmost array (call this k), and so if every array were to
 * be filled in to capacity, there would be a total of k arrays of size k,
 * for a total of k^2 elements.  Of this capacity, we know that at least an
 * eighth of them are filled in, so k^2 must be at most 8n, and so 
 * k = O(sqrt(n)).  To finish the analysis, the overhead of the structure is
 * at most the overhead of this top-level array, plus potentially k - 1
 * unused elements in some array.  This is a total of O(k) = O(sqrt(n))
 * overhead, which is what we originally desired.
 */