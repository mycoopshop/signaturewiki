== Operator Overloading Getter 
<pre>
function addPointOrVector(a, b) {
    if (a instanceof Point) a = new Vector([a])
    if (b instanceof Point) b = new Vector([b])
    return new Vector(...a.points, ...b.points])
  }
  class Vector() {
    constructor(points) { ... }
    get [Symbol.operator('+')]() { return addPointOrVector }
  }
  class Point() {
    constructor(x, y) { this.x = x, this.y = y }
    get [Symbol.operator('+')]() { return addPointOrVector }
  }
  Point(1, 0) + Point(1, 1) == Vector([[1,1], [1,0]])
</pre>

## References

https://www.tonymarston.net/php-mysql/singletons-are-not-evil.html

https://www.keithcirkel.co.uk/proposal-operator-overloading/

https://derickbailey.com/2016/03/09/creating-a-true-singleton-in-node-js-with-es6-symbols/

https://dmitripavlutin.com/detailed-overview-of-well-known-symbols/

https://lucasfcosta.com/2016/12/01/Meta-Programming-in-JavaScript-Part-Four.html

https://itnext.io/straits-9ef2b9a563cd

https://www.cs.princeton.edu/courses/archive/fall05/cos217/reading/as.html

http://www.iitk.ac.in/LDP/LDP/Linux-Dictionary/html/Linux-Dictionary.html

http://web.cs.iastate.edu/~weile/cs440.540/5.SemanticAnalysis.scope.pdf

https://www.tutorialspoint.com/compiler_design/compiler_design_symbol_table.htm

https://www.tutorialspoint.com/lisp/lisp_quick_guide.htm

https://steemit.com/programming/@drifter1/writing-a-simple-compiler-on-my-own-symbol-table-basic-structure

https://www.brainkart.com/article/Symbol-Table-Per-Scope-and-Use-of-Symbol-Tables_8132/

https://www.kttpro.com/2017/02/09/six-phases-of-the-compilation-process/

http://turbopascal.org/turbo-pascal-internals

https://qlikcentral.com/2015/06/08/the-qlikview-engine/

http://flipcode.com/archives/Implementing_A_Scripting_Engine-Part_1_Overview.shtml

https://systemml.apache.org/docs/0.15.0/api/java/org/apache/sysml/api/mlcontext/MLContext.html

http://www.newlisp.org/newlisp_manual.html

https://en.wikibooks.org/wiki/Introduction_to_newLISP/Working_with_XML

http://www.gigamonkeys.com/book/programming-in-the-large-packages-and-symbols.html

https://xml.apache.org/xalan-j/xsltc/xsl_variable_design.html

https://developer.android.com/reference/android/icu/text/SymbolTable

https://xml.apache.org/xindice/dev/guide-internals.html

https://www.codeproject.com/Articles/1032231/What-is-the-Symbol-Table-and-What-is-the-Global-Of