# Repository of self-signed root authorities or master signing keys

Files in this repository should be validated before use.
Download the repository contents and validate using the following:



# Checksum Validation of Repositry: SHA512

    $ cd ~/.../Self-Signed_RootAuthority-main

    $ shasum -a 512 * > SHA512SUMS.new

    $ diff SHA512SUMS SHA512SUMS.new 


\n

The expected output of $diff is that if checksums (lines) match, then nothing is output!




# GPG Importing Master Signing Key and Verifying SHA512SUMS

Master Signing keyID: **0CB54A16295A59F7**

Software Signing keyID: **ADE59E4B52BF9D95**

_ADE59E4B52BF9D95 has been signed with 0CB54A16295A59F7_

## GPG Instructions

    $ gpg --keyserver [URL] --recv-key [keyID of Master Signing GPG]

    $ gpg --import [keyID of Master Signing GPG]

    $ gpg --verify SHA512SUMS
