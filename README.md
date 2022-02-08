# Repository of self-signed root authorities or master signing keys

Files in this repository should be validated before use.
Download the repository contents and validate using the following:

# Checksum Validation of Repositry: SHA512
$ cd ~/.../Self-Signed_RootAuthority-main
$ shasum -a 512 * > SHA512SUMS.new
$ diff SHA512SUMS SHA512SUMS.new 

The expected output of $diff is that if checksums (lines) match, then nothing is output!


# GPG Importing Master Signing Key and Verifying SHA512SUMS
$ gpg --keyserver [URL] --recv-key [keyID of Master Signing GPG]
$ gpg --import [keyID of Master Signing GPG]
$ gpg --verify SHA512SUMS
