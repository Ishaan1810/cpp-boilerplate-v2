# Valgrind Exercise

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```

EXTRA CREDIT :-

Q)What happens when the executable is linked statically?  Does Valgrind still detect those same bugs?
Why or why not.


A)When an executable is linked statically, it means that all the libraries it depends on are included within the executable itself. This makes the executable self-contained and doesn't rely on dynamic shared libraries or external dependencies. Static linking can have an impact on the behavior of Valgrind in the following ways:

1.Valgrind will detect some errors in a statically linked executable, but its effectiveness may be limited, especially when identifying issues within the static libraries bundled with the executable.

2.Valgrind may not be able to track memory leaks in the bundled libraries, but it can still identify memory leaks in your application code.

So Valgrind checks like uninitialized memory access will still work on statically linked executables b. However, Valgrind's ability to detect issues in the static libraries may be constrained.

