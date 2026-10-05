# Grand Line Sentinel Bot

Telegram RPG bot for One Piece-style gameplay.

## Version 1.2.0

This release keeps the complete `grandlineG_bot6` base and adds the latest feature and reliability updates.

### Fishing

- `/fish`, `/fishing`, `/fishes`, and `/sell_fish`
- Seven fish types with bounty rewards
- Wooden, steel, diamond, and mythical rods and bait
- Durability, shop purchases, fish inventory, individual selling, and Sell All
- Fishing shop captions show each rod/bait price, uses, and XP bonus; purchases require confirmation
- Fishing rewards normal player XP
- Owner-only `/setfish` sticker setup

### Mines gambling

- Start with `/mines [amount]`, for example `/mines 100K`
- The board has 25 tiles and 5 hidden mines
- Each safe tile increases the potential cash-out multiplier
- Tap **Cash Out** to collect the current payout
- Hitting a mine loses the placed bet
- Ending a game also forfeits the placed bet
- Owner can reply to an active board with `/trackmines` to reveal mine locations

### Custom character rarities

- Owner creates a rarity with `/addrarity [name]`, for example `/addrarity Celestial`
- Admins can view available rarities with `/rarities`
- Owner/admin can assign it with `/edit [id] rarity CELESTIAL`
- Owner can add characters with `/celestialadd` and delete them with `/celestialdelete [id]`
- Owner can remove a custom rarity with `/deleterarity [name]`
- Owner can configure winning bounty with `/setrarityreward [rarity] [minimum] [maximum]`
- Custom rarity definitions are saved in `data/rarities.json` and included in backups

### Player and collection UI

- `/xp` level and XP-bar view
- `/fruits` with styled Devil Fruit and category text
- Confirm/Cancel flow before selling a Devil Fruit
- `/mychars` IDs, pagination, two-column buttons, and Check All
- `/show [name]` searches all rarities and displays matching character cards one at a time
- Inline cached-photo results and image recovery fallback
- Inline cached-video results for video characters
- `/c [id]` is the short character-ID lookup command
- `/charslist` shows every configured rarity and emoji
- Challenge buttons removed from inline character results

### Leaderboards and administration

- Interactive `/top`, `/xtop`, and `/crewtop`
- Crew, player, and level leaderboard switching
- Owner-only `/addbounty` and `/addxp` using a reply or user ID
- Owner-only `/downloadjson` and confirmed `/restorejson`
- Automatic and manual backups include the fishing sticker, group settings, and pattern state
- Buyer starts a trade with `/trade [price]` by replying to the seller; seller accepts, buyer selects a character, and seller confirms

### Group permissions and registration

- The bot reacts to group commands and gameplay only while it is an administrator in that group.
- If the bot is not an administrator, group messages are ignored silently.
- `/start` is the only group exception and registers the player before the bot is promoted.
- `/start` continues to work normally in private chat.

### Preserved base modules

The merged project also preserves the base ZIP modules and assets:

- Games, PvP, world boss, giveaways, inventory, crews, Haki, and update notifier
- Channel storage synchronization
- Fonts, wanted poster, requirements, and existing JSON player/character data

## Setup

1. Clone or upload the project.
2. Install dependencies with `pip install -r requirements.txt`.
3. Create a `.env` file with your Telegram credentials and existing bot settings.
4. Set the release variables in Railway:

   ```env
   BOT_VERSION=1.2.0
   BOT_CHANGELOG=🚀 MAJOR UPDATE — VERSION 1.2.0
   ```

5. Start the bot with `python bot.py`.

Do not commit `.env`, Telegram session files, `__pycache__`, or runtime backup/import folders.
