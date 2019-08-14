# ortools-with-cmake
How-to demonstrating integration of binary OR-tools for C++ package inside of a cmake project.

## Install `or-tools` from binary

Follow the steps [here](https://developers.google.com/optimization/install/cpp/).

## Build this repo
_Note:_ this has only been tested on Ubuntu 18.04 but should work on other distros / OSes.

```bash
cd {path-to-this-repo}
mkdir build && cd build
cmake -DORTOOLS_ROOT:STRING="{path-to-ortools-root-dir}" ..
make
```

You'll see some warnings most likely.

## Test the build
The test executable built in the previous step uses the toy example provided by Google from [here](https://developers.google.com/optimization/introduction/cpp).

Run the test:

```bash
./test-app
```

You should see the following output:

```bash
WARNING: Logging before InitGoogleLogging() is written to STDERR
I0814 10:15:02.698244 12745 program.cc:12] Number of variables = 2
I0814 10:15:02.698365 12745 program.cc:19] Number of constraints = 1
I0814 10:15:02.700047 12745 program.cc:29] Solution:
I0814 10:15:02.700063 12745 program.cc:30] Objective value = 4
I0814 10:15:02.700076 12745 program.cc:31] x = 1
I0814 10:15:02.700080 12745 program.cc:32] y = 1
```
