# Introduction

This is the second part of the embedded lab. Start from Part 1 before proceeding to this second part.

# PART 2: Final Boss

## Identify Cryptographic Assets
Joe says some of the cryptographic data extracted is familiar, but he can't pinpoint why that is so.
Maybe look at the strings or entropy of the firmware and reveal suspicious information.

**TARGET 4: Identify the cryptographic data**
>Hint:
>Some data may stand out due to how it is encoded.
>After decoding, it is usually trivial to infer if we are dealing with an encrypted block, or structured information via the existing magic numbers.

## Find the pot of gold
After some `openssl` back and forth, it seems we were able to extract a hash of some kind from the signature. Fortunately, we have a very comprehensive (and short...) rainbow table we can use to reveal the hashed intel.

**TARGET 5: c&c password**

## Crack the code
The messages we found hint at a random number generator and our reverse engineering team found a bug that leads to the code repeating after some attempts. But it seems the codes are different on each boot...

**TARGET 6: Crack the OTP generator**

## Connect to the C&C
With the C&C password in our hands, and with the OTP system cracked, we can finally connect to their servers!

**TARGET 7: Final secret**
