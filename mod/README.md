**_DEPRECATED:_** The Prosperity tradition's finisher has changed with 3.1.1 "Lem" - it is now +5 stability and +5% job output.  The Mercantile tradition also provides a tradition for +1 trade value per Clerk.  For me, that means this mod is no longer adding or tweaking gameplay in a meaningful way.  It remains listed for players who choose to play in the 3.0.3 and 3.0.4 "Dick" versions of Stellaris.

# Prosperity Tradition Rebalance

Patch 3.0 (Dick) and its immediate bugfix patches have reduced Pop counts on most planets (or habitats/ringworlds) drastically.  The Prosperity tradition has not been updated to reflect the expected lower Pop counts, so this mod makes a few small changes to improve it.

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

Stellaris requires overriding the entire containing file to make changes to a district or job (there are technical consequences if not).  That means this mod is incompatible with other mods that make changes to almost any type of districts (other than the rural types: generator, mining, and farming) and mods that change worker-strata jobs.  Additionally it will not be compatible with mods that alter the same traditions (Prosperity Finisher and Interstellar Franchising).

This mod is not compatible with achievements because it overwrites core Stellaris files.

### When to Install

This mod can be safely added or removed from your save game after the game has started.  Adding it will result in more Merchant jobs on some of your planets, but fewer Clerk jobs.  Removing it will cause the reverse - fewer Merchants and more Clerks.  In either case you will probably end up with unemployment.  Code-wise, however, it will not break your savegames.

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
* 1.1.0 Add event to flag the mod as installed
* 1.1.1 Remove extra images files to keep distribution lightweight (no script changes)
* 1.2.0 Maintenance release
    * Update description
    * Remove monthly pulse event
    * Add event to flag as installed when single-player game is loaded
* 1.2.1 Mark as deprecated - redundant in Stellaris 3.1.1 "Lem" and higher

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/prosperity_tradition_rebalance)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.