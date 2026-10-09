PROJECT TRIUNE - LDON.MAC README
================================

PURPOSE
-------
ldon.mac automates LDoN adventures on Project Triune, working through five
adventure camps in a fixed order. It uses the character's in-game Adventure
Stats to decide which camp still needs successful completions. The goal is
10 successful adventures at each camp (50 total).

CAMP ORDER
----------
1. SRO - South Ro / Deepest Guk          10 successes
2. EP  - Everfrost / Miragul's Menagerie 10 successes
3. EC  - East Commonlands / Rujarkian    10 successes
4. NRO - North Ro / Takish               10 successes
5. BM  - Butcherblock / Mistmoore        10 successes

A later camp is not selected until all earlier camps have 10 successes.
If you already have successes, the macro reads them rather than starting
from zero. After every completed mission, it checks Adventure Stats again
instead of trusting a running counter.

INSTALLATION AND RUNNING IN GAME
--------------------------------
1. Place the ldon.mac file in the macros folder inside your MacroQuest
   installation folder (for example: MacroQuest\macros\ldon.mac).
2. Start Project Triune with MacroQuest running.
3. From inside the game, type one of the /mac commands listed below
   into your chat/command line and press Enter.
4. Use /mac ldon for normal operation, or use the skip/resume switch
   only when recovering an already accepted adventure.

HOW TO START / COMMAND SWITCHES
-------------------------------
/mac ldon
    Normal operation. Reads your adventure success counts, selects the next
    required camp, travels to it, requests an adventure and completes it.
    Use this when you do NOT already have an active mission to recover.

/mac ldon skip
    You already ACCEPTED an adventure but are still OUTSIDE its dungeon.
    On the first loop, skips asking the recruiter for another mission and
    proceeds toward the existing mission entrance. After that mission,
    normal automated operation resumes.

/mac ldon resume
    You are already INSIDE an active adventure instance.
    Skips recruiter/travel/entrance steps and resumes dungeon clearing.
    Afterward, returns via Bazaar and Back, checks the actual Adventure
    Stats and continues normally.

Only 'skip' and 'resume' are supported startup switches. Do not combine
them. Camp names (such as 'nro') are not supported as manual overrides.
The macro chooses the camp automatically from your Adventure Stats.

WHAT IT DOES AUTOMATICALLY
--------------------------
- Reads in-game Adventure Stats at startup and after each completed run.
- Completes the needed successes for SRO, EP, EC, NRO and BM in order.
- Navigates between camps, recruiter, mission entrance and mission areas.
- On the first visit to a camp in the current macro run, targets and
  confirms the Adventure Recruiter BEFORE sending Hail; retries targeting
  if needed. It then requests the adventure.
- Uses Bazaar and Back for return travel. Both the Bazaar and the East
  Commonlands (EC tunnel) are accepted as return destinations.
- If it lands in the EC tunnel, it does not try to use the Bazaar map;
  it continues the route toward the appropriate camp/Magus.
- Upon reaching all five goals (10 successes each), ends the macro at
  the Bazaar or EC-tunnel return landing.

IMPORTANT NOTES
---------------
- Every zone traversed by the route needs a usable navigation mesh.
- Your character must have the abilities, transportation and navigation
  setup that the macro uses (including Bazaar and Back and relevant Magus
  routes).
- The first-time recruiter Hail is performed once per camp per macro run,
  not stored permanently between separate macro launches.
- 'skip' is for outside the instance; 'resume' is for inside the instance.
  Picking the wrong switch can send the character through the wrong steps.
- These features describe the supplied macro's programmed behavior;
  actual travel and mission completion depend on in-game conditions.

QUICK EXAMPLES
--------------
Starting fresh or after finishing a mission:    /mac ldon
Adventure accepted, still standing at camp:     /mac ldon skip
Already inside the adventure dungeon:          /mac ldon resume

File: ldon.mac
