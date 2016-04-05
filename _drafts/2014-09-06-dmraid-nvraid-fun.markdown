---
title: dmraid and nvraid on fakeraid 5
layout: post
summary: Using dmraid to run on NVRaid FakeRaid 5 is painful. It can't actually do what it's supposed to.
---
I recently had a bit of a scare. I was going through a much needed backup of my home server when all of a sudden it had unmounted and became read only. It did this after showing a slew of errors of course. Not good, but I had setup my machine to use Raid 5 using the FakeRaid controller I have on my motherboard. That, in theory, means that there is always one redundant drive in an array of three or more, oh I how I wish this were true. I then spent the next week or so of my free time devoted to figuring out how to switch out a drive, their is some prep after all. I also didn't have a spare drive, sort of the worse case scenario.

Since the data on the Internet is sparse a scattered far and wide, let me she some light on what I've learned.


__DMRaid does not have readily apparent documentation__
Short of looking at source code, I couldn't find any documentation beyond a man page. Unfortunately, that manpage doesn't have the best information.
__DMRaid primarily supports Intel hardware__
Not surprisingly, intel motherboards are the most prevalent of any other motherboard and that means more FakeRaid controllers than any other. It's not suprising then, that the DMRaid has more support for that hardware. It leaves NVRaid, a bit in the dust.
__FakeRaid definitely not recommended__
FakeRaid attempts to use hardware controllers, which means it needs to understand different hardware drivers. Unfortunately, that means things can change from hardware to hardware and makes it harder to support.
__Linux Pure Software Raid is recommended instead__
Since it's not recommended it's better to be even more fake and just have Linux be its own driving force. In this case, just informing Linux that there are multiple drives either physical or virtual, then informing them how you just want to work with those drives through software. It of course has it's pluses and minuses. Technically it is slower, but not very noticeably. It's main benefit, is that is not dependent on any firmware, including the need to have a dedicated hardware RAID controller on your motherboard.
__Windows is needed for FakeRaid__
Since DMRaid can not have the best support for all hardware. It's recommended to have a windows instance to handle all of the motherboard RAID controller actions, especially things like rebuilding an array, DMRaid cannot rebuild an array, except in very limited instances, the main reason for being able to use RAID.

Given this FakeRaid is not recommended. It further cements why you need to make constant backups. Make sure to do CONSTANT backups.

Despite my broken raid, the drives were working enough that I could still pull data off of it. So, crisis averted. Don't let this happen to you!
