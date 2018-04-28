# slow-hash
Implementation of Moneros hash function in pure python

The actual Proof-of-Work hash behind Monero is quite a beast. The basic "actual" POW centers around expanding the data into a 2 Mb of mostly random data via AES encryption, then reading and writing points in it based on said data. This make memory access, rather than pure CPU compute power, the actual bottleneck. The concept seems, so far, to have kept mining power fairly well distributed and resistant to specialized hardware miners.

But there is lots of extra obfuscation around that part. It also requires implementations of Keccak, Groestl, JH, Skein and Blake hashes (the finalists and winner of SHA3). It's certainly possible to just lift public implementions of them, but for all the gusto in the community, I havn't really seen a full rewrite in a higher level language. It's understandable, because it becomes clear pretty soon that the other hashes are mostly there to make it a chore to imnplement. But either way, after a lot of time and false starts, I ended up doing so. So here's an implementaion in python, no dependenices.
