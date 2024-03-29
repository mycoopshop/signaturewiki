If M is x, you replace λx.x with id (id is usually denoted by I in combinatory logic).

If M doesn't contain x, you replace the term with const M (const is usually denoted by K in combinatory logic).

If M is PQ, that is the term is λx.PQ, you want to "push" x inside both parts of the function application so that you can recursively process both parts. This is accomplished by using the S combinator defined as λfgx.(fx)(gx), that is, it takes two functions and passes x to both of them, and applies the results together. You can easily verify that that λx.PQ is equivalent to S(λx.P)(λx.Q), and we can recursively process both subterms.

* https://www.lucasfcosta.com/2018/05/20/Y-The-Most-Beautiful-Idea-in-Computer-Science.html
* https://crypto.stanford.edu/~blynn/haskell/curry-howard.html
* http://www.cs.virginia.edu/~cs655/readings/mockingbird.html
* http://www.annblake.com/wp-content/uploads/2015/01/est-final-functional-use-published.pdf
* https://github.com/louthy/language-ext/wiki/Thinking-Functionally:-Combinators
* http://xn--wxak1a.com/blog/Combinators.html
* https://www.computer.org/csdl/trans/tc/1985/10/06312191.pdf
* https://bartoszmilewski.com/2011/07/11/monads-in-c/
* http://brandon.si/code/do-applicative-functors-generalize-the-s-k-combinators/
* https://news.ycombinator.com/item?id=7895719
* https://en.wikipedia.org/wiki/Parser_combinator
* https://www.cprogramming.com/tutorial/functors-function-objects-in-c++.html
* https://www.quantstart.com/articles/Function-Objects-Functors-in-C-Part-1

## Identity Function
https://www.oreilly.com/library/view/functional-javascript/9781449360757/ch04.html
https://medium.com/@kaw2k/a-map-to-success-functors-in-javascript-6eb6638ce966
http://raganwald.com/2015/02/13/functional-quantum-electrodynamics.html
https://medium.com/javascript-scene/you-might-not-need-typescript-or-static-types-aa7cb670a77b
https://blog.bigbinary.com/2018/03/20/practical-usage-of-identity-function.html