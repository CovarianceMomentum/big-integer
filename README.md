# big-integer
Heavily optimized C++ library implementing long arithmetic.

## Implementation

### Features
`big_integer` class is implemented, including:
- `int`, `uint_32t`, `uint_64t` and copy implicit
 constructors, as well as explicit string constructor;
- `swap` and `to_string` functions;
- Overloaded unary operators (`+`, `-`, and `~`);
- Overloaded increments and decrements;
- Overloaded boolean operators (`==`, `!=`, `<`, `>`, `<=` and `>=`);
- Overloaded binary operators (`+`, `-`, `/`, `*` and `%`);
- Overloaded bitwise binary operators (`&`, `|` and `^`) and bitwise shifts (`<<` and `>>`);
- Overloaded assignment operators derived from binary operators.

### Multiplication
Multiplication has a complexity of <img src="https://render.githubusercontent.com/render/math?math=\mathcal{O}(n \cdot m)" alt="O(n*m)">,
where <img src="https://render.githubusercontent.com/render/math?math=n" alt="n"> 
and <img src="https://render.githubusercontent.com/render/math?math=m" alt="m"> 
are lengths of multiplicands using naive algorithm.

_Possible improvement: use FFT (Fast Fourier Transform) to speed up multiplication._

### Division
Division also has a complexity of <img src="https://render.githubusercontent.com/render/math?math=\mathcal{O}(n \cdot m)" alt="O(n*m)">, 
where <img src="https://render.githubusercontent.com/render/math?math=n" alt="n"> 
and <img src="https://render.githubusercontent.com/render/math?math=m" alt="m"> 
are lengths of divident and divisor, respectively. Algorithm used in
division is [this one](http://surface.syr.edu/cgi/viewcontent.cgi?article=1162&context=eecs_techreports).

### Other optimizations
#### Small Object (also known as Small String)
Important optimization that stores `big_integer` instances with small values
differently and more memory efficient. You can learn more about this optimization
from [this](https://blogs.msmvps.com/gdicanio/2016/11/17/the-small-string-optimization/) *CppCon* speach.

#### Copy-on-write 
Optimization that optimizes memory usage of `big_integer` instances that are copied from each other
withou being modified. You can learn more about this optimization from [this](https://en.wikipedia.org/wiki/Copy-on-write) article.
