---
slug: discord
title: MintGarden Discord integration
description: How to integrate the MintGarden Discord bot
authors: acevail
image: /img/discord/discord_bot_offer_notification.png
---

The MintGarden Discord integration includes the following features

- Token gate specific channels based on the NFTs a user owns
- Post offer and sales data to a specific channel

<img alt="discord bot screenshot" src="/img/discord/discord_bot_offer_notification.png" width="400"/>

## Inviting the bot

Before you can use the integration, you have to invite the MintGarden Discord bot into your Discord server.

<a href='https://discord.com/oauth2/authorize?client_id=928618126319419422&scope=bot&permissions=268453888' target='_blank' className='discord-button'>
  <svg fill="#ffffff" viewBox="0 0 16 16" className="discord-button-icon" aria-hidden="true">
    <path
      d="M13.545 2.907a13.227 13.227 0 0 0-3.257-1.011.05.05 0 0 0-.052.025c-.141.25-.297.577-.406.833a12.19 12.19 0 0 0-3.658 0 8.258 8.258 0 0 0-.412-.833.051.051 0 0 0-.052-.025c-1.125.194-2.22.534-3.257 1.011a.041.041 0 0 0-.021.018C.356 6.024-.213 9.047.066 12.032c.001.014.01.028.021.037a13.276 13.276 0 0 0 3.995 2.02.05.05 0 0 0 .056-.019c.308-.42.582-.863.818-1.329a.05.05 0 0 0-.01-.059.051.051 0 0 0-.018-.011 8.875 8.875 0 0 1-1.248-.595.05.05 0 0 1-.02-.066.051.051 0 0 1 .015-.019c.084-.063.168-.129.248-.195a.05.05 0 0 1 .051-.007c2.619 1.196 5.454 1.196 8.041 0a.052.052 0 0 1 .053.007c.08.066.164.132.248.195a.051.051 0 0 1-.004.085 8.254 8.254 0 0 1-1.249.594.05.05 0 0 0-.03.03.052.052 0 0 0 .003.041c.24.465.515.909.817 1.329a.05.05 0 0 0 .056.019 13.235 13.235 0 0 0 4.001-2.02.049.049 0 0 0 .021-.037c.334-3.451-.559-6.449-2.366-9.106a.034.034 0 0 0-.02-.019Zm-8.198 7.307c-.789 0-1.438-.724-1.438-1.612 0-.889.637-1.613 1.438-1.613.807 0 1.45.73 1.438 1.613 0 .888-.637 1.612-1.438 1.612Zm5.316 0c-.788 0-1.438-.724-1.438-1.612 0-.889.637-1.613 1.438-1.613.807 0 1.451.73 1.438 1.613 0 .888-.631 1.612-1.438 1.612Z"
    />
  </svg>
  <span style={{marginLeft: 0.5 + 'rem'}}>Invite Discord bot</span>
</a>

## Token gating

The bot will assign roles based on the NFTs a user holds. 

### Repare roles to assign

In order to token gate specific channels, you first have to create Discord roles that control the permissions.

On your Discord server, head to **Server Settings** -> **Roles**.
Then create a new role, for example `NFT Holder`.

Make sure the role is sorted lower than the `MintGarden` role that has been created when inviting the bot.
Otherwise the bot is not allowed to assign your new role.

### Link the role to a collection 

Use the command `/collectionrole` to link a role to a specific NFT collection.
The command can be run in any channel in your Discord server.

:::info

Do not copy-paste the whole Discord command, it doesn't work properly. Instead, start with typing the `/command` first, then fill in the gaps.

:::

An example command looks like this:

![](/img/discord/discord_collectionrole_example.png)

You can find your collection ID on MintGarden, as part of the URL.

![](/img/discord/mintgarden_collection_id.png)

### Link the role to a creator

Use the command `/creatorrole` to link a role to a specific NFT creator.

An example command looks like this:

![](/img/discord/discord_creatorrole_example.png)

You can find the creator DID on MintGarden, on the profile page.

![](/img/discord/mintgarden_creator_id.png)


### Verify as a holder

The holders of your NFTs can now call the `/verify` command to connect their Discord account to MintGarden and receive the roles.
The command will explain all the steps to the user.

## Offer notifications

Coming soon...
