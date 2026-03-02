<div style="text-align: center; margin-top: 40px">
<img src="./Assets/triangle.png" alt="alt text" width="140"/>
<h1 style="margin-bottom: 0px; margin-top: 0px">Triangle</h1>
<h3 style="margin-top: 0px">A completely unnecessary programming language</h3>
</div>

---

![GitHub stars](https://img.shields.io/github/stars/nickgermaine/triangle?style=social)
![GitHub forks](https://img.shields.io/github/forks/nickgermaine/triangle?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/nickgermaine/triangle?style=social)

![version](https://img.shields.io/badge/version-3.15.0-blue)
![GitHub repo size](https://img.shields.io/github/repo-size/nickgermaine/triangle)
![GitHub language count](https://img.shields.io/github/languages/count/nickgermaine/triangle)
![GitHub top language](https://img.shields.io/github/languages/top/nickgermaine/triangle)
![GitHub last commit](https://img.shields.io/github/last-commit/nickgermaine/triangle?color=green)



# Triangle Programming Language

Triangle programming language is a completely imaginary and unnecessary fork of Python.

It should not be used for anything, ever, unless you really want to.

Currently based on Python 3.15.


## Features

1. 100% functional
2. 100% reliable
3. 100% statically typed
4. 100% dynamically typed

---

## New Features

- [x] "when" keyword
- [x] "is kinda" operator
- [ ] const variables
- [ ] Strongly typed language features
- [ ] Wtv else is not a thing and some things are not even possible

---

## Performance Benchmarks
- **Fuzzy Matching**: infinity% faster than `difflib`.
- **Logic Consistency**: 0% (by design).
- **Vibe Check Latency**: < -23ms.

---

# Documentation
### "when" keyword

The "when" keyword is used to define a branch of code that will execute as soon as the condition
resolves to `True`.

Example:

```python
import time


def main():
    print("Application is ready.")
    print("Executing logic and stuff.")
    # Do your stuff here


def is_ready():
    # Do some setup tasks, return true when ready
    # Simulating with a sleeptime of 2 seconds
    time.sleep(2)
    return True


if __name__ == '__main__':
    print("Waiting for the server to be ready...")

    when is_ready():
        main()

    print("Do other stuff here...")
```

Output:
```text
Waiting for the server to be ready...
Do other stuff here...
Application is ready.
Executing logic and stuff.
```

---

### "is kinda" operator

The "is kinda" operator is used to check if two values are kinda the same.

Example:

```python
def main():
    if 4 is kinda 5:
        print("4 is kinda 5")
    else:
        print("4 is not kinda 5")

    if [1, 2, 3] is kinda [1, 2, 3.3]:
        print("Lists are kinda equal")
    else:
        print("Lists are not kinda equal")

    if "Dave" is kinda "Wave":
        print("Dave is kinda Wave")
    else:
        print("Dave is not kinda Wave")


if __name__ is kinda "__main__":
    main()


```

Output:

```text
4 is not kinda 5
Lists are kinda equal
Dave is kinda Wave
```


### Installation:

Building Triangle requires standard CPython build dependencies. On Arch Linux, ensure you have base-devel, gdb, zlib, and openssl installed.

#### Configure the Environment

Since Triangle utilizes the latest 3.15 free-threading features for its async when keyword, you must configure the build with the GIL disabled
(this will be done whether you want it or not, I have disabled the GIL by default)

```bash
./configure --disable-gil --enable-optimizations
```

#### Regenerate Grammar and Opcodes
Because Triangle introduces the when keyword and the is kinda operator (index 6 in cmp_op), you must regenerate the internal files before compiling. This ensures the new grammar is baked into the parser.

```bash
make regen-all
```

#### Compile

```bash
make -j$(nproc)
```

#### Alternative Installation
DO NOT run make install. This will overwrite your system's default Python binary and likely break your Linux installation. Use altinstall to keep Triangle isolated as its own binary.

```bash
sudo make altinstall
```

#### Usage
Once installed, you can launch the Triangle REPL from your terminal:

```bash
triangle
```

#### Verifying the Vibe

To ensure your installation was successful and the C-level intercepts are working:

```python
>>> # Check numbers
>>> 9.8 is kinda 10
True
>>> # Check recursive data structures
>>> {"status": 200} is kinda {"status": 200.1}
True
>>> # Check the banner
>>> help
# This will trigger some text
```
