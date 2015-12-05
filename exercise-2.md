## Pointer Argument Passing: Part II
Let's change the value of `y` (i.e. change where `y` points) in the function `foo`. See this live at [Ideone](http://ideone.com/9pSYQJ).

``` cpp
#include <iostream>

void foo(int* y) {
  y = new int(3);
} // memory leak! lost all references to y before deleting it

int main(int argc, char* argv[]) {
  int x = 10;
  int* y = &x;
  foo(y);
  
  std::cout << *y << std::endl;
  
  return 0;
}

```

What is the output?

Again, the function `foo` is passed a copy of `y` from the function `main`. Because the pointer in the function `foo` is a copy, changing where it points does not affect the pointer in the function `main`.

There are no differences between how `y` is being passed here and in the previous example. In this example it is important to realize that we are changing *where* the copy points to -- not *what* it points to.

What would we need to do in order to change the value of `y` in the function `foo` and that change reflected in the function `main`?
