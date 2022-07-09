# Project Structure

The following pseudocode represents the layout we're *currently* aiming for with all wrappers. All of this is up for debate, and contributions to the [ongoing discussions](https://github.com/hypixelapiwrapper/specification/discussions) are greatly appreciated.

```kotlin
HypixelAPI {

  // Methods for interfacing with areas of the API related to players.
  players {
  
    // Uses the /counts endpoint.
    totalOnline(): number
    
    withUuid(playerUuid: uuid): HypixelPlayer?
    
    // Uses the /player endpoint.
    named(playerName: string): HypixelPlayer?
    
    // Uses the /friends endpoint.
    friendsWith(playerName: string): Set<HypixelPlayer>?
    
    // Uses the /friends endpoint.
    friendsWith(playerUuid: uuid): Set<HypixelPlayer>?
    
    // Uses the /status endpoint.
    statusOf(playerName: string): HypixelPlayerStatus?
    
    // Uses the /status endpoint.
    statusOf(playerUuid: uuid): HypixelPlayerStatus?
    
    // Uses the /recentgames endpoint.
    recentGamesOf(playerUuid: uuid): List<HypixelGameSession>?
    
    // Uses the /recentgames endpoint.
    recentGamesOf(playerName: string): List<HypixelGameSession>?
    
    // Uses the /guild endpoint.
    inGuild(guildId: objectid): Set<HypixelPlayer>?
    
    // Uses the /guild endpoint.
    inGuild(guildName: String): Set<HypixelPlayer>?
    
    // Uses the /guild endpoint.
    inSameGuildAs(playerName: string): Set<HypixelPlayer>?
    
    // Uses the /guild endpoint.
    inSameGuildAs(playerUuid: uuid): Set<HypixelPlayer>?
  }
  
  // TODO: 7/9/22 Add details for guilds, skyblock, network punishments, leaderboards, boosters, etc.
}
```
