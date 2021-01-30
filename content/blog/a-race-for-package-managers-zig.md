---
title: "A Race for Package Managers - Zig"
date: 2021-1-29
tags: ["programming", "zig"]
# photo:
description: "Members of the Zig community are rushing to develop the first package managers."
draft: false
---

Currently, the [Zig project][1] is in development for 0.8. Creator, Andrew Kelley, is [encouraging the design of decentralized package managers][2]. Interested developers see this as the blowing of the trumpets to create a package manager for Zig. [mattnite](https://github.com/mattknite) has just recently pushed [a new version of gyro][3] (previously zkg) with semantic versioning, the ability to pull from multiple package registries, and ease of use importing, e.g. `@import("some-package")`.

Development for gyro has stayed consistent since November, but received almost half of its total commits in October of last year, alone. gyro is the oldest package manager in development for Zig, and the most popular. It has roughly followed [the design plans set forth by marler][4], to address the problem of build dependencies and signing of packages. Although, it is nowhere near as verbose as marler's proposals. I can't tell whether that is a good thing or not.

I see the gyro project and have trust that it will be the leading package manager for Zig someday. When something deeply roots itself into a project like Zig, it will be terribly hard to remove. Today, it is a new project, but yet quite more advanced than any of the others. At the same time, I think the opportunity is ripe for a competing package manager. Maybe one that operates entirely out of the `build.zig`?

It is very interesting to follow the development of all of these different package manager implementations as they sprout up. Like a capitalist market, they will all compete for attention and usage. As one becomes more used than others, it will receive more development and usage. Someday it will be the chicken or the egg problem with Zig package managers, but today they are all eggs.

[1]: https://ziglang.org
[2]: https://github.com/ziglang/zig/issues/943#issuecomment-383610569
[3]: https://github.com/mattnite/gyro/releases/tag/0.1.0
[4]: https://github.com/marler8997/zig-package-manager
