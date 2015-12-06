## Pointer Argument Passing: Part III
Let's change the value of `y` in the function `foo` and have that change reflected in the function `main`. See this live at [Ideone](http://ideone.com/nAR8Vd).

``` cpp
#include <iostream>

void foo(int** z) {
  *z = new int(3);
}

int main(int argc, char* argv[]) {
  int x = 10;
  int* y = &x;
  int** z = &y;
  
  foo(z);
  
  std::cout << *y << std::endl;
  
  delete *z;
  
  return 0;
}

```

What is the output?
