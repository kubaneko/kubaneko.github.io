---
title: 'PackageRank for Hackage (GSoC)'
date: 2022-09-01
permalink: /posts/2022/PackageRank
tags:
  - Haskell
  - Hackage
  - GSoC
---

I took part in GSoC in the summer of 2022 with Haskell.org on the Hackage project. The aim of the project was to develop a way to sort heuristically sort packages based on [PackageRank](https://gitlab.com/crates.rs/crates.rs/-/blob/main/ranking/src/lib_ranking.rs) from crates.rs

My work can be found [here](https://github.com/haskell/hackage-server/pull/1091). The work for GSoC ends with the commit [7c36cf7](https://github.com/haskell/hackage-server/pull/1091/commits/7c36cf7e42d8d0a19ba3d9b0c46d56c5cde52d86) and was done under the mentorship of [Gershom Bazerman](http://gbaz.github.io/)

## Future work

In its basic form the project is complete but there are several other improvements that could be made.

- once Reverse dependencies are accepted, they should be added to PackageRank
- my next goal is to make a cache for PackageRank values and values for freshness calculations, so freshness for dependencies can be calculated efficiently.
- most downloads ever per month - would enable comparing the popularity of a package presently versus in the past.
- Readme Score could be easily extended to reward other syntax features such as math syntax and others
- Size of documentation of the package is currently calculated from file size of its .html files this is not too accurate so some parsing would help/other heuristic.
- the size of documentation of a package is currently calculated from the file size of its .html files, this is not too accurate so some parsing would help or another heuristic
- There is also an infinite amount of tuning the parameters until they are perfect that can be done.

## How it went

Each point in the list loosely corresponds to two weeks of the 12-week project.

- I mainly finished schoolwork and started to look around the src of hackage and with the help of my mentor compared what was feasible to do with what was available from hackage in contrast to crates.rs
- I started to gather needed information from hackage about packages (src code, documentation, versions , etc.)
- I integrated PackageRank into PackageList and changed Browse Feature to be compatible and added co    lumn for PackageRank into the UI
- I added the readme score (made a custom markdown parser with commonmark)
- I tuned some parameters, moved PackageRank over to PackageList Feature and handled exceptions.

## What I learned

- how to orient in a large codebase 
- some new Haskell features (ex. MonadFail)
- some self-discipline
- how to collaborate effectively with other people.

## Overall

I enjoyed this experience and learned a lot, and I am thankful to google for the opportunity and to my mentor for his patience. I would like to continue my work with implementing previously mentioned cache.
