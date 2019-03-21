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

https://dmitripavlutin.com/detailed-overview-of-well-known-symbols/

https://lucasfcosta.com/2016/12/01/Meta-Programming-in-JavaScript-Part-Four.html

https://itnext.io/straits-9ef2b9a563cd

