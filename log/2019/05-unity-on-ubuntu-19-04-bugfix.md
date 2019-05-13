# Unity3D on Ubuntu 19.04 - Bugfix

## Problem

The embedded mono depends on `libssl1.0` that has been removed from both debian and ubuntu repo. The error is non-obvious, but the log file indicates that mono is unable to start due to not finding the openssl library.

## Solution

- Install `libssl1.0` from `bionic`. (`cosmic` should work as well, but bionic being LTS is guareenteed to be supported better)
    - https://packages.ubuntu.com/search?suite=bionic-updates&searchon=names&keywords=libssl1.0

- Install Unity now as usual.
- The embedded Mono should work as expected.
