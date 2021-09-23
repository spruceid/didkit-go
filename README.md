Check out the DIDKit documentation [here](https://spruceid.dev/docs/didkit/).

# DIDKit

DIDKit provides Verifiable Credential and Decentralized Identifier
functionality across different platforms. It was written primarily in Rust due
to Rust's expressive type system, memory safety, simple dependency web, and
suitability across different platforms including embedded systems. DIDKit
embeds the [`ssi`](https://github.com/spruceid/ssi) library, which contains the
core functionality.

![DIDKit core components](https://spruceid.dev/assets/images/didkit-core-components-7abba2778ffe8dde24997f305e706bd8.png)

## go get

`go get` needs some additional steps in order to work as expected.

Get the source, add DIDKit and SSI as submodules to your repo, build it and point to it:

```bash
$ go get github.com/spruceid/didkit-go
$ git submodule add https://github.com/spruceid/didkit.git extern/didkit
$ git submodule add https://github.com/spruceid/ssi.git extern/ssi
$ make -C extern/didkit/lib ../target/test/c.stamp
$ go mod edit -replace=github.com/spruceid/didkit-go=./extern/didkit/lib/didkit-go
```

## Maturity Disclaimer

Please note: this readme documents an early-stage open-source product ported 
manually to python, and we are still incorporating feedback from our first 
comprehensive third-party code audit. These artefacts are presented as 
functional "betas" for experimentation and to show the direction of the 
project (inviting proposals for changes of direction, even!). They are not,
 however, intended for transacting real-world business yet.
