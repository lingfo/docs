<p align='center'>
    <img src="https://user-images.githubusercontent.com/47505116/237992533-a31a4afb-953f-466b-b35e-f429ba24349e.png" alt="Lingfo logo">
</p>

---

Lingfo is a library that allows you to run functions from other languages without needing to translate the code.

## How it works

Lingfo compiles or interprets the code to create a runnable file which then can be executed, displaying the output in the terminal. Removing the translation step allows for code to run at its native language speed.

## The idea

Lingfo is a FFI that works with _any_ language.

In future, we want lingfo to work really **from any language, to any language**. To achieve this, we want to have lingfo being executed as a app when using other languages than python. So, for example, if we want to get C++ function in rust, to call the function (inside rust), the output file for lingfo would look like this:

```rust
use std::process::Command;

fn example() {
    Command::new("lingfopy")
            .arg("lib/main.hpp") // function path
            .arg("example") // function name
            .arg("arg1, arg2, arg3") // and some args for function to execute
            .spawn()
            .expect("lingfo error");
}

```

This might require a lot of optimization, configuration etc. But by using some not released yet lingfo apps this will be probally easier to do.
