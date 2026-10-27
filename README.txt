FrostPVP v3.2.5 — Meteor motion hotfix for Minecraft Paper 1.21.11
=================================================================

This is the complete existing v3.2.4 FrostPVP plugin plus a Frozen Meteor fix.

THE ACTUAL FIX
- Previously nine BlockDisplays were teleported every tick with a 2-tick
  teleport interpolation. That can cause the client to render them as stationary.
- The animation now sends real, instantaneous position updates every 2 ticks.
- Each piece starts with its proper offset, not stacked at one location.
- The complete flight corridor is kept loaded using server plugin chunk tickets,
  including when no players are near the meteor impact location.
- A removed display no longer cancels the scheduled meteor impact.
- The 5-block ice meteor core, impact sounds, particles, 7-block crater, chest,
  border checks, and normal block restoration are preserved.
- All chunk tickets are released after the event ends or is stopped.

HOW TO INSTALL
1. Place BOTH Java files in src/main/java/com/example/punchsnowball/.
2. Update plugin.yml and build.gradle.kts.
3. Run GitHub Actions, then replace the previous JAR with the new build.
4. Restart your Paper server. NEVER leave two versions installed at once.
5. Test: /frost event meteor frostsword 5m
6. The ice structure should visibly descend over about 7 seconds, then land.
7. IMPORTANT: back up worlds first when testing event terrain changes.

The server configuration folder stays plugins/FrostPVP/.
No resource pack is required. All earlier weapons/events remain intact.
The Java/Paper API project has NOT been compiled in this environment.


v3.2.6 chosen/treasure changes:
- Chosen One is now tag-based (melee hit). No kill necessary.
- Current holder glows and has a floating Heart of the Sea display above their head.
- Holder coordinates announced in chat and boss bar every minute.
- Treasure now generates a visible temporary surface shrine or an underground ice vault
  accessible through a decorated surface ladder shaft. Hints include depth/Y.
- Event-built blocks are temporary; test on a backed-up world.


FrostPVP 3.2.7 updates:
- Frost Titan damage now reflects raw hits, criticals and weapon enchantments; old 7.2 damage bottleneck migrated.
- Scripted Warden steps up one block and descends up to four blocks while seeking players.
- Meteor randomly lands in the world-centered 2500 x 2500 X/Z area, always inside the full current world border footprint.
- Meteor keeps its location hidden by default and avoids the event starter by at least 325 blocks.
- Adjust defaults in plugins/FrostPVP/config.yml.
