## Pointer Argument Passing: Part I
Just like the integer in the previous example, pointers can also be passed to functions using value semantics. See this live at [Ideone](http://ideone.com/YEOdIE).

``` cpp
#include <iostream>

void foo(int* y) {
  *y = 3;
}

int main(int argc, char* argv[]) {
  int x = 10;
  int* y = &x;
  foo(y);
  
  std::cout << *y << std::endl;
  
  return 0;
}

```

What is the output?

We are still using value semantics when we pass `y` to the function `foo`. This means the function `foo` is passed a copy of `y` from the function `main`. Even though the pointer is a copy of the pointer in the `main` function, both pointers point to the same memory address (the address of `x`). Because both pointers (the original and copy) point to the same memory address, either can be used to access/mutate the value stored at that memory address.

What would happen if changed where `y` pointed in the function `foo`?
