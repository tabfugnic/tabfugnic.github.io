---
title: dmraid and nvraid on fakeraid 5
summary: Using dmraid to run on NVRaid FakeRaid 5 is painful. It can't actually do what it's supposed to.
---
I recently had a bit of a scare. I was going through a much needed backup of my home server when all of a sudden it had unmounted and became read only. It did this after showing a slew of errors of course. Not good, but I had setup my machine to use Raid 5 using the FakeRaid controller I have on my motherboard. That, in theory, means that there is always one redundant drive in an array of three or more, oh I how I wish this were true. I then spent the next week or so of my free time devoted to figuring out how to switch out a drive, their is some prep after all. I also didn't have a spare drive, sort of the worse case scenario.

Since the data on the Internet is sparse a scattered far and wide, let me she some light on what I've learned.


__DMRaid does not have readily apparent documentation__
__FakeRaid definitely not recommended__
__Linux Pure Software Raid is recommended instead__
__Windows is needed for FakeRaid__
__DMRaid does not support writing metadata__
What this basically means is that dmraid, even if it could see


Despite all of this the drive itself was well enough that I could still pull data off of it. So, crisis averted. Don't let this happen to you!
