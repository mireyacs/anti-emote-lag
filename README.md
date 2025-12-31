# Anti Emote Lag Script

A Roblox client-side script designed to prevent exploiters from using malicious emotes and animations to lag players and servers. This script actively monitors all players and automatically cancels any animations that are not in the whitelist.

## Overview

This script addresses a critical vulnerability in Roblox where exploiters can use custom emotes and animations to cause severe lag, frame drops, and server performance issues. By maintaining a comprehensive whitelist of approved animation IDs, the script ensures only legitimate animations can play while blocking potentially harmful ones.

**⚠️ Important**: This script is intended to be used with a **scripting utility/executor**, **NOT** to be placed directly in a Roblox game. Do not add this script to your game's ServerScriptService or any other location in Roblox Studio.

## Features

- **Active Monitoring**: Continuously monitors all players every frame to detect and cancel non-whitelisted animations
- **Comprehensive Whitelist**: Includes all standard Roblox animation packs (Astronaut, Bubbly, Cartoony, Elder, Knight, Levitation, Mage, Ninja, Pirate, Robot, Rthro, Stylish, Superhero, Toy, Vampire, Werewolf, Zombie)
- **R6 & R15 Support**: Whitelists both classic R6 and modern R15 animations
- **Additional Animation Packs**: Includes popular animation packs from various brands and collaborations
- **Configurable Console Output**: Toggle console warnings on/off for cleaner logs
- **Automatic Cleanup**: Properly handles character respawns and disconnections

## Installation

**⚠️ This script is for use with scripting utilities/executors, NOT for placement in Roblox games.**

1. Open your preferred Roblox scripting utility/executor
2. Copy the contents of `AntiEmoteLag.lua` or `loadstring(game:HttpGet("https://raw.githubusercontent.com/mireyacs/anti-emote-lag/refs/heads/main/AntiEmoteLag.lua", true))()`
3. Paste and execute the script in your executor
4. The script will automatically start monitoring all players in the current server

**Do NOT place this script in ServerScriptService or any location in Roblox Studio.**

## Configuration

### Console Output

By default, console output is disabled. To enable warnings when animations are blocked:

```lua
local SHOW_CONSOLE_OUTPUT = true  -- Change to true to see blocked animations
```

### Whitelist Management

The script includes a comprehensive whitelist of approved animation IDs. To add or remove animations, edit the `ANIMATION_WHITELIST` table:

```lua
local ANIMATION_WHITELIST = {
	-- Add your animation IDs here
	1234567890,
	9876543210,
}
```

**⚠️ Important Note on Emotes**: Emotes cannot be whitelisted at the moment. There is a significant risk that a malicious emote responsible for crashes or lag could slip into the whitelist, which would render the script completely useless. For security reasons, only standard movement animations (run, walk, jump, idle, fall, swim, climb) and approved animation packs are included in the whitelist.

## How It Works

1. **Player Monitoring**: When a player joins or their character spawns, the script begins monitoring their character
2. **Active Detection**: Every frame, the script checks all currently playing animation tracks
3. **Whitelist Check**: Each animation's ID is extracted and checked against the whitelist
4. **Automatic Cancellation**: Any animation not in the whitelist is immediately stopped
5. **Continuous Protection**: Monitoring continues for as long as the character exists

## Addressing Recent Concerns

### The Emote Lag Exploit

Recently, a significant vulnerability has been discovered where exploiters can use custom emotes and animations to cause severe lag and performance issues for players and servers. This is a **Roblox platform issue**, not something created by any individual developer or script.

### Regarding Accusations

There have been false accusations made by CatThatDrinksSprite regarding my involvement with this exploit and the sale of related scripts. I want to set the record straight:

1. **I did not create or enable this exploit** - This is a platform-level vulnerability in Roblox's animation system that affects all games
2. **I was not involved in the decision to sell any scripts** - The lead developer, jvrre, made the decision to put scripts up for sale **before I joined the team**
3. **My role and mission** - Since joining the team, my sole purpose has been to:
   - Improve the quality and functionality of scripts
   - Help users implement and use scripts responsibly
   - Prevent abuse and ensure scripts are used for their intended purpose (protection, not exploitation)
   - Contribute positively to the community

This Anti Emote Lag script is a **defensive solution** designed to protect games from the exploit, not enable it. It is provided to help developers safeguard their games and players.

## Technical Details

- **Usage**: Intended for scripting utilities/executors (NOT for placement in Roblox games)
- **Script Type**: Client-side script (runs on client when executed via executor)
- **Performance**: Minimal overhead - uses efficient hash table lookups for whitelist checking
- **Compatibility**: Works with all Roblox avatar types (R6, R15, Rthro)
- **Dependencies**: Only uses built-in Roblox services (Players, RunService)
- **Emote Support**: Emotes are intentionally excluded from the whitelist for security reasons

## Animation Packs Included

The whitelist includes animations from:

- All 16 standard Roblox animation packs
- Classic R6 animations
- Modern R15 animations
- Wicked Popular Animation Pack
- Catwalk Glam by e.l.f.
- adidas Community Animation Pack
- Bold by e.l.f.
- Wicked "Dancing Through Life" Animation Pack
- Unboxed by Amazon
- adidas Sports Animation Pack
- adidas aura animation pack
- No Boundaries by Walmart
- Oldschool Animation Pack
- NFL Animation Pack

## Support

If you encounter any issues or have questions about the script:

1. Verify the script is being executed through your scripting utility/executor
2. Check that the script is running (it should start monitoring automatically)
3. Check the console for any errors (if `SHOW_CONSOLE_OUTPUT` is enabled)
4. Ensure your whitelist includes all animations you want to allow
5. Remember: Emotes are intentionally excluded from the whitelist for security reasons

## License

This script is provided as-is for the purpose of protecting Roblox games from emote lag exploits. Use responsibly and in accordance with Roblox's Terms of Service.

## Disclaimer

This script is a defensive tool designed to protect games from exploits. It does not create, enable, or facilitate any exploits. The emote lag vulnerability is a platform-level issue in Roblox that this script helps mitigate.
