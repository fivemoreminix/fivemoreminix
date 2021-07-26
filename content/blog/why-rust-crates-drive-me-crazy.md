---
title: "Why Rust Crates Drive Me Crazy (A Semver Rant)"
date: 2021-07-25
---

Since I started using Rust back in 2017, I began to notice an odd pattern: crates always staying in the minor versions. Crates are versioned with a string identifying their state of development, production-readiness, and likely whether any breaking changes occurred since the last version. All of these things can be determined by reading the version of a Rust crate. This system is known as Semantic Versioning, and every Rust crate agrees to it by a) using the version field, and b) publishing their crate on [crates.io](https://crates.io).

Semantic Versioning defines the method of writing versions on the front page of [their website](https://semver.org/):

> Given a version number MAJOR.MINOR.PATCH, increment the:
> 
> * MAJOR version when you make incompatible API changes,
> * MINOR version when you add functionality in a backwards compatible manner, and
> * PATCH version when you make backwards compatible bug fixes.

Although it's simple, a lot of crates get this wrong. And I cannot stress enough, *a lot* of crates. I'll admit, I have gotten some of these rules wrong before. But you see them used wrongly so often, you almost wonder what the versioning is for, at all.

So what do some crates get wrong about their versioning? Well, since Semver is used to make assumptions about backwards compatibility, it could go very wrong...

The second rule above states that you only increment the minor version when you add functionality in a "backwards compatible manner". That means that if you rely on a crate such as "serde" for struct serialization/deserialization, and validly mark the required version for it as so:

```rs
[dependencies]
serde = "^1"
```

Then you should be able to assume that you get all of the new features when they're added to the major 1 version without any breaking changes, as any breaking changes would go into major version 2. Furthermore, any bug fixes will land themselves in the patch versions like 1.0.1, so we are ensured bug fixes and non-breaking changes. And serde is a vital crate, as it has existed since 2016 and exists as a [dependency to thousands of other crates][1] in the ecosystem.

So you build your program and notice the lock file says serde is version 1.0.126. wtf? So you mosey on over to the crates.io page for serde, go to versions tab, and get a quick idea of what these versions might have changed. Looks like version 1.0 was released over 4 years ago, and the latest 1.0.126 was 2 months ago. So, it can't be that only non-breaking patches were being made since April of 2017? Well let's look at the difference in SLOC of the crate from the first 1.0 release to the latest 1.0.126 "patch".

In version 1.0 there were 15,912 SLOC of Rust, excluding comments and whitespace (that's what SLOC means). And version 1.0.126 is sporting *double* at 33,185 SLOC. That's a lot of backwards compatible patches.

There are other major crates with just as painful Semver violations as the last. I found all of these examples on the front page of crates.io, I'm not cherry-picking crates here -- these violations are just so commonplace that about every other crate has some major problems with its semantic versioning.

Let's play spot the semantic versioning issue in the top downloaded crates.
Starting with [rand][2] the essential crate for random numbers, downloaded over 74 million times directly, not including the hundreds of millions of downloads of the 5,953 dependent crates like [regex][3], [base64][4], and [time][5]. To its defense, it never said it was production ready. The fact the version is not in major 1 means it is in active development, with frequent breaking changes, and no promises of compatibility with older versions. Now that's a normal thing for crates, but why does almost the entire ecosystem rely on a crate that isn't considered ready to be used in production?

Looks like the same "increment only the patch number" problem occurs in the syn crate as serde, because they are both published by the same dude. While [libc][7] has a similar problem but is being driven crazy by a completely different person.

Last on our list is [unicode-xid][6] sitting at version 0.2.2, and thus having been "under heavy construction" since April 26th of 2015. The updates are infrequent and this crate seems to be implementing behavior defined by a standard. So the question is, why not make it *available to use* by releasing a 1.0 version? Because until you publish your crate as 1.0, you are telling everyone, *do not use my crate, it will break your code and waste your time!* But in this case, we have a perfectly fine crate, with a semantic version telling us that we shouldn't use it. Therefore, if I use unicode-xid in my crate version 1.0, I am lying by saying that my code is production ready, when I am relying on a crate that is not. Shameful for ruining semantic versioning for everyone.

That's the end of the list. I could go on for the length of your /dev/sda about crates on crates.io that imply being production ready while not being major versioned. I'm just getting bored.

But there are a few bright stars that hold the banner in the war on terrori- semver, I mean, that we can't thank enough. Thank you [regex][3], thank you [clap][8], and thank you to the many others that we cannot find but must honor for their valient compliance to Semver, the oh-so-difficult three number system. Cheers to you 🍺

[1]: https://crates.io/crates/syn/reverse_dependencies
[2]: https://crates.io/crates/rand
[3]: https://crates.io/crates/regex
[4]: https://crates.io/crates/base64
[5]: https://crates.io/crates/time
[6]: https://crates.io/crates/unicode-xid
[7]: https://crates.io/crates/libc
[8]: https://crates.io/crates/clap
