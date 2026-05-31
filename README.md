# ReaperBountySystem

RocketMod Unturned plugin that lets players place Uconomy-backed bounties on other players.

## What It Does

- `/setbounty <playername> <amount>` immediately removes the amount from the placer.
- When the target is killed by another player, the killer receives the total active bounty.
- Multiple bounties on the same target stack.
- Unclaimed bounty entries expire after the configured number of real-life days.
- Expired bounties are refunded to the original placer when `RefundExpiredBounties` is enabled.
- Bounties are saved to `bounties.xml` so they survive restarts.

## Commands

```text
/setbounty <playername> <amount>
/removebounty <playername>
/bounties
/bounty <playername>
```

## Permissions

```text
reaperbounty.setbounty
reaperbounty.removebounty
reaperbounty.bounties
reaperbounty.bounty
```

## Install

Drag the included `Plugins` and `Libraries` folders into the server's `Rocket` folder.

```text
Rocket/
  Plugins/
    ReaperBountySystem.dll
  Libraries/
    MySql.Data.dll
```

Restart the server once so Rocket creates the config.

`BountyExpireDays` is real-life days, not in-game days.

## Discord Bounty Board

Set these in the config to maintain one live Discord message ranked highest to lowest:

```xml
<DiscordBountyBoardEnabled>true</DiscordBountyBoardEnabled>
<DiscordWebhookUrl>YOUR_WEBHOOK_URL</DiscordWebhookUrl>
<DiscordServerName>Reaper</DiscordServerName>
<DiscordUpdateIntervalSeconds>300</DiscordUpdateIntervalSeconds>
<DiscordMaxBounties>10</DiscordMaxBounties>
```

The plugin stores the Discord message ID in `discord-bounty-board.xml` and edits that same message instead of posting new ones. Rows include the soonest bounty expiration in hours.
