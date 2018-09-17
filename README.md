# Go snapcraft part

This is a proposal go part to use with `snapcraft.yaml` files that need to build go files. The advantage of this go part over the current go part is:

* Faster build times
* More go version options

## Faster build times

This part simply downloads the official releases directly from https://golang.ord/dl. This provides faster build times because we don't have to rebuild the entire go source tree every time, and helps with building on low memory devices. 

## More go version options

The upstream branch naming convention supports all versions of go, but doesn't currently provide a way to track a major release, i.e. doing something like "go1.10.X", where that resolves to go1.10.4 (or whatever the most recent release to 1.10 is), but here we can provide that.

## Supported tags/branches

The convention is the same as the upstream go git repository, prefixing `go` before the version number. For example, to build with version 1.11.1, you would checkout git tag `go1.11.1`. 

Additionally, the following branches are provided for automatic updates:

* `go1.10` -> this is currently at `go1.10.4`, if `go1.10.5` is released, this will be automatically moved to `go1.10.5`.
* `go1.11` -> this follows the 1.11 release tracks
* `master` -> this follows the most recent stable release (i.e. currently it is at `go1.11`, when `go1.12` is released, this will be moved to `go.1.12`)
