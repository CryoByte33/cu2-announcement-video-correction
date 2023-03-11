**TL;DR:** I made a mistake logging the FPS for Tomb Raider in my CU2 announcement video, so I re-tested. The new results still show that CU2 is a performance benefit, and the other results shown alongside Tomb Raider in the video are still valid.

# What Happened

A Discord user (thank you ViolentLeaf!) asked for reproducibility steps for my Rise of the Tomb Raider testing, and I provided it. However, during the course of doing so I found that I used an outdated (pre deep dive content) MangoHUD config for the Rise of the Tomb Raider testing during the video. This was because I reformatted my Deck in the middle of the CU2 update video and copied an outdated MangoHUD config onto my Deck to resume tested.

**To be clear, no other results were affected.**

While the results weren't inherently "bad", they were only measuring every 100ms, not every frame as is my normal process.

The outdated config file has been deleted, but in order to verify my results and provide any necessary guidance to the community, a re-test of RotTR was in order.

**The results of the re-test are located in [GitHub here](https://github.com/CryoByte33/cu2-announcement-video-correction)**, and including the source MangoHUD logs for the testing done.

# Methodology

I ran 3 sets of benchmarks, each for low and high preset in RotTR.

1. Default
2. CU2 with all recommendations & 1GB UMA
3. CU2 with all recommendations & 4GB UMA

512GB Q3 Steam DeckGame build 9575745, using the Feral Linux port

A test run consisted of the following

1. Boot the game
2. Set the graphics preset to Low
3. Quit game
4. Boot game
5. Run in-game benchmark and log with MangoHUD
6. Set graphics preset to High
7. Quit game
8. Boot Game
9. Run in-game benchmark and log with MangoHUD
10. Quit Game
11. Go to Desktop Mode
12. Use CU2 to "Clean" all data for the game, ensuring a clean run in the next test (force recreation of prefix and shadercache)
13. Configure Deck for next round of tests
14. Reboot
15. GOTO 1

# Results
* Low - Excluded FPS over 200 to accommodate for loading screens
* High - Excluded FPS over 150 to accommodate for loading screens
* All - Includes all FPS ranges for comparison, including loading screens mid-bench
* Comparison - These include the results for the new baseline, the original results in the CU2 announcement video, and the new results with CU2 and 1GB of VRAM.

# Differences from previous results

All results were very similar to expectations, with a few notable differences:

1. In my video, I show differences between swap sizes, and it seems that the 100ms granularity had a very large effect on the lows in that testing. **The new results show that the CU2 recommendations still help, but the 1% and 0.1% differences in RotTR were not as significantly affected by swap size as it originally seemed.**

2. The results for Tomb Raider are higher across the board here, even at default settings. Even counting this, CU2 is still increasing lows, while also being at an even higher average FPS than the video showcased.

# Summary

**CU2 is still shown and validated to be a boost to lows in Rise of the Tomb Raider, but the effect of the swap file size is different than originally shown.**

I'll be investigating the swap file size more in the future anyway (I would really like to reduce the necessary size), so I'll make sure that Rise of the Tomb Raider is part of that testing suite.

Thank you again to ViolentLeaf on Discord for inadvertently bringing this to my attention, and I'm deeply sorry for the accident with the MangoHUD configuration.

Please let me know if you have any questions, and I'll do my best to get to them in a timely manner!
