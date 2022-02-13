# Repository of self-signed root authorities or master signing keys

Files in this repository should be validated before use.
Download the repository contents and validate using the following:



# Checksum Validation of Repositry: SHA512

    $ cd ~/.../Self-Signed_RootAuthority-main

    $ find -type f ! -iname "SHA512SUMS.new" -exec sha512sum "{}" + > SHA512SUMS.new

    $ diff SHA512SUMS SHA512SUMS.new 


\n

The expected output of $diff is that if checksums (lines) match, then nothing is output!




# GPG Importing Software Signing Key and Verifying SHA512SUMS

Master Signing keyID: **0CB54A16295A59F7**

Software Signing keyID: **36DE9A59CD869EE2**

36DE9A59CD869EE2 has been signed with 0CB54A16295A59F7_

## GPG Instructions

    $ gpg --keyserver [URL] --recv-key 36DE9A59CD869EE2
    $ gpg --verify SHA512SUMS

or,

    $ gpg --import ~/36DE9A59CD869EE2.asc
    $ gpg --verify SHA512SUMS

## Expected Output

        safesploit@guest Self-Signed_RootAuthority-main$ **gpg --fingerprint**

        pub   rsa4096 2017-08-07 [SC] [expires: 2030-01-02]
              6079 E6ED E834 5507 5B2E  1462 0CB5 4A16 295A 59F7
        uid           [ultimate] safesploit - Root CA

        pub   rsa4096 2022-02-13 [SC] [expires: 2025-02-13]
              1E3E E4C2 E838 A0FE EEFA  FA92 36DE 9A59 CD86 9EE2
        uid           [ultimate] SWS Software Signing

        safesploit@guest Self-Signed_RootAuthority-main$ **gpg --verify SHA512SUMS **
        gpg: Signature made [OMITTED]
        gpg:                using RSA key 1E3EE4C2E838A0FEEEFAFA9236DE9A59CD869EE2
        gpg: Good signature from "SWS Software Signing" [ultimate]
