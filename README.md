# Prosperity Tradition Rebalance

Patch 3.0 (Dick) and its immediate bugfix patches 3.0.1, 3.0.2, and 3.0.3 have reduced Pop counts on most planets (or habitats/ringworlds) drastically.  The Prosperity tradition has not been updated to reflect the expected lower Pop counts, so this mod makes a few small changes to improve it.

Inspired by [this](https://www.reddit.com/r/Stellaris/comments/njvnys/is_there_a_mod_that_rebalanced_the_prosperity/) post on Reddit.

# Changes

The regular empire tradition Interstellar Franchising added 1 Clerk job to each city district.  Because Pop counts are now much lower (and in the spirit of the 3.0.3 changes to the job bonus production buildings), this has been altered to instead increase the Trade Value of each Clerk by 1 and Amenities by 0.5.  Machine and hive-minded empires already receive a bonus to energy production instead, and that did not need adjustment.

The regular finishing effect provided 1 Merchant job per 50 Pops.  In the spirit of the approximately halved capital building Pops requirements, the finisher has been changed to 1 Merchant job per 30 jobs.  Similarly, machine empires and hive-minded empires receive 1 maintenance/synapse drone (respectively) per 15 Pops (rather than 1 per 20).

## Compatibility

Requires Stellaris version 3.0.3.  This mod alters the following core Stellaris files:

* `districts/00_urban_districts.txt` - entire file, removes section for bonus clerk job for city districts
* `districts/01_arcology_districts.txt` - entire file, removes section for bonus clerk jobs for residential arcologies
* `districts/03_habitat_districts.txt` - entire file, removes section for bonus clerk job for commercial districts
* `districts/04_ringworld_districts.txt` - entire file, removes section for bonus clerk jobs for commercial segments
* `pop_jobs/03_worker_jobs.txt` - entire file, contains most worker-tier jobs (**NOT** compatible with my mod [Technician Job Priority Fix for Slaves](https://steamcommunity.com/workshop/filedetails/?id=2484702578) - this one includes the same fix)
* `traditions/00_prosperity.txt` - replaces two traditions `tr_prosperity_finish` and `tr_prosperity_interstellar_franchising` (new file `01_prosperity_overrides.txt`)

Stellaris requires overriding the entire containing file to make changes to a district or job (there are technical consequences if not).  That means this mod is incompatible with other mods that make changes to almost any type of districts (other than the rural types: generator, mining, and farming) and mods that change worker-strata jobs.  Additionally it may not be compatible with mods that alter the same traditions (Prosperity Finisher and Interstellar Franchising).

This mod is not compatible with achievements because it overwrites core Stellaris files.

## Known Issues

Overriding a tradition generates an error log.  Expect to see two lines in the error.log file similar to these:

```
[00:56:58][game_singleobjectdatabase.h:147]: Object with key: tr_prosperity_finish already exists
[00:56:58][game_singleobjectdatabase.h:147]: Object with key: tr_prosperity_interstellar_franchising already exists
```

## Changelog

* 1.0.0 Initial version
* 1.0.1 Credit inspiration
* 1.0.2 Fix tooltip to match actual Clerk Trade Value bonus
* 1.0.3 Speeeeling
* 1.0.4 Tagged as "Balance" and fixed the image for Interstellar Franchising to show the actual effect of the mod (no script changes)