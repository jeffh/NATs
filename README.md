Nimble Acceptance Tests
=======================

High-level tests that exercises [Nimble](https://github.com/Quick/Nimble) as a
dependency though common supported configurations. This helps verify if changes
to Nimble configurations break consumers of Nimble as well as providing an
example configuration of Nimble in its various configurations.

Current testing configurations:

- iOS, Test Bundle
- iOS, UI Test Bundle
- iOS, Without XCTest (in app)
- OS X, Test Bundle
- OS X, UI Test Bundle
- OS X, Without XCTest (in app)

Running
-------

**Note:** Can only be run on OS X versions that support UI Testing (10.11+)

To run locally, clone this repository and then run:

```bash
# Downloads Nimble locally for testing
rake vendor_nimble

# Runs all configurations
rake
```

If you prefer, you can change `Vendor/Nimble` to point to a branch of Nimble if
you want to see how your changes affect these configurations.

`vendor_nimble` rake task supports optional configuration arguments to change the source of Nimble:

```bash
rake 'vendor_nimble[http://github.com/user/Nimble-Fork.git,my-branch]'
```

Notes
-----

**Why not use submodules?**

Carthage has a [bug](https://github.com/Carthage/Carthage/issues/135) that
prevents submoduling Nimble in this repository, so the rakefile will
dynamically fetch it instead.

