# nizk_authentication
A Rust library for a Non-Interactive Zero-Knowledge Authentication protocol in collaboration with the [Technical University of Munich (TUM)](https://www.tum.de/en/).

## Project compilation and Cross tool
* In this project we use the [cross tool](https://github.com/cross-rs/cross) to cross compile our crate for target `arm-unknown-linux-gnueabihf` and `armv7-unknown-linux-gnueabihf`. For example, inside the folder lib, run:\
`cross build --target=arm-unknown-linux-gnueabihf`
* The standard cargo tool could be used to build for Debian computers:\
`cargo build`

## Library
The crate code can be found at `./lib`

## Examples
Examples on using this crate can be found at `./examples`

## Security Analysis
Formal security analysis of this protocl using Tamarin-Prover is avaialble at [this repo](https://github.com/tum-esi/act-nizkp)

## Contribution
More contribution could be added to this repo. For example:
* Replacing the setup phase with a more efficient key agreement protocol. (In our research, we did not compare the current key agreement protocols.)
* Adding support for 128-bit shared secret key. (Currently 256-bit keys are utilized.)
* Improving our session key agreement protocol by utilizing only one NIZK proof from Prover A to verifier B and then calculating the shared session key with the randon value and commitment of A and public and private key pair of B. (Ephemeural session key agreement without interaction and with a 2 factor authentication.)
