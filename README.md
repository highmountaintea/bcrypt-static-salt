# bcrypt-static-salt

Provides a list of static salts to use for bcrypt

## Purpose

bcrypt is one of the good hashing algorithms that are difficult to brute force. It is a good candidate for converting strings and secrets into hashes.

However, bcrypt is not deterministic because it hashes with a random salt each time. In order to produce deterministic hash, a static or deterministic salt has to be used. Typically this static salt is embedded in the implmentation of the algorithm (in the code), which introduces a tightly coupled dependency to a specific implementation of bcrypt.

Instead, we simply provice a set of static salt below. As long as the salt listed below is used, you can generate the same deterministic hash regardless of which bcrypt implementation used. There is one salt per round:

* we will generate the salt entries later. Once they are generated, they will never change

## Benefits

* the deterministic nature is not tied to a code implementation
* easy to use with existing bcrypt implementation without modifying code
* easy to reference
* easy to understand

