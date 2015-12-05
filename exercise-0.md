## Value Semantics (Assignment)

Consider this simple example:

``` cpp
int x = 10;
int y = x;
x = 3;
```

Here we initialize `x` to 10 and then `y` to `x`. Up until this point both `x` and `y` are equal to 10. What happens when we change the value of `x` to 3? Does this also change the value of `y`?

The value of `x` is assigned to `y` using value semantics. This means that the value of `x` is copied and assigned to `y`, so changing the value of `x` will not change the value of `y`. 





## Value Semantics (Argument Passing)
Arguments can be passed to function under the saw value semantics: the values passed to the function are *copies*. See this live at [Ideone](http://ideone.com/VBRd3V).

``` cpp
#include <iostream>

void foo(int y) {
  y = 3;
}

int main(int argc, char* argv[]) {
  int x = 10;
  
  foo(x);
  
  std::cout << x << std::endl;
  
  return 0;
}

```

What is the output?

We are using value semantics when we pass `x` to the function `foo`. This means the function `foo` is passed a *copy* of the value `x` from the function `main`. Since `foo` operates a copy of the value in `main`, changing the value of the copy in `foo` does not affect the value of `x` in the function `main`.

Is there a way we can effect change to the value `x` in the function `main` using value semantics?
