---
slug: web-minting
title: MintGarden Web Minting
description: Mint your first Chia NFT in the browser in minutes
authors: acevail
image: /img/web-minting-banner.png
---

Creating NFTs on Chia just got way easier.<br/>
We’re excited to release web minting to MintGarden!

![web minting banner](/img/web-minting-banner.png)

Connect your Goby wallet and mint your first NFT in minutes:<br/>
[https://mintgarden.io/mint](https://mintgarden.io/mint)

This first version allows you to mint one NFT at a time, with edition and collection minting coming soon!

## Set up your creator profile

### Create a profile

On the MintGarden website, we provide wallet interface for Goby, making it easy to interact with DIDs and NFTs.

Head over to https://mintgarden.io/wallet, connect Goby, and immediately see all your NFTs.

![wallet screenshot](/img/web-minting/wallet.png)

Create a new profile in the „Profiles“ tab to use it for minting or to move NFTs into that profile.

![wallet screenshot](/img/web-minting/wallet-2.png)

After the profile has been confirmed on-chain, refresh the page and click the little pen icon to customize your profile
and connect your Twitter account.

![wallet screenshot](/img/web-minting/wallet-3.png)

### Migrate your existing profile to Goby

If you already have a DID in your Chia wallet, you can migrate it to Goby by running the following commands in your terminal.

First find the internal ID of your DID wallet:

```bash
$ chia wallet show
```

Example output:
```bash
Wallet height: 5165302
Sync status: Synced
Balances, fingerprint: 592245864

Chia Wallet:
   -Total Balance:         1.234 xch (1234000000000 mojo)
   -Pending Total Balance: 1.234 xch (1234000000000 mojo)
   -Spendable:             1.234 xch (1234000000000 mojo)
   -Type:                  STANDARD_WALLET
   -Wallet ID:             1
   
Acevail:
   -Total Balance:         1.0
   -Pending Total Balance: 1.0
   -Spendable:             1.0
   -Type:                  DECENTRALIZED_ID
   -DID ID:                did:chia:1zflc8mkghju28cvf67mpwq5065vz5akyzhzek7lvrgp689f28j3q4dhg9f
   -Wallet ID:             2
```

Then take that wallet ID (in this case 2), as well as the address of your Goby wallet and run the following command:
```bash
$ chia rpc wallet did_transfer_did '{"wallet_id": <WALLET_ID>, "inner_address": "<YOUR_GOBY_ADDRESS>", "fee": 1000000000, "with_recovery_info": true}'
```

Example:
```bash
$ chia rpc wallet did_transfer_did '{"wallet_id": 2, "inner_address": "xch1ysveu6vh0evhuwq30708syfep7nfaed29l0ejee9nw3wjfjalq8s4fjjvy", "fee": 1000000000, "with_recovery_info": true}'

{
    "success": true,
    "transaction": {
      ...
    }
}
```

This will transfer the DID to Goby and you can now use it in MintGarden.

## Mint a single NFT

To mint your first NFT, create a profile and then head over to https://mintgarden.io/mint

Select „Single“.

![minting type selection](/img/web-minting/minting-1.png)

Select one of your profiles as the creator.

![minting profile selection](/img/web-minting/minting-2.png)

Create a new collection if you want to group multiple NFTs together, or select one of your existing collections.

![minting collection selection](/img/web-minting/minting-3.png)

Upload the image or video you want to reference in the NFT.

![minting data selection](/img/web-minting/minting-4.png)

Finally, enter some metadata, such as a name and description, as well as the royalty percentage you want to enforce
on-chain.

Click “Mint NFT” and let the magic happen!

![minting details](/img/web-minting/minting-5.png)

Your NFT will now be uploaded, minted and awaited. After that, you can inspect the NFT by clicking the preview!

If you want, you can offer it for other people by clicking „List for Sale“ and creating an offer with Goby.

![NFT details](/img/web-minting/minting-6.png)

That’s it, you minted a Chia NFT with just a few clicks and offered it for sale!

## Mint an edition

An edition is a set of identical copies of a digital asset, each with a unique identifier, allowing multiple
ownership of the same item while maintaining individual authenticity.

To mint an edition on MintGarden, create a profile and then head over to https://mintgarden.io/mint

Select „Edition“.

![minting type selection](/img/web-minting/edition-1.png)

Select your newly created profile as the creator.

![minting profile selection](/img/web-minting/edition-2.png)

Specify the number of copies you want to mint as part of your edition.
You can mint up to 100 copies.

Also, fill in the name and description of your edition.


#### License URL

By assigning a license to the NFT, buyers of your NFTs will directly see what rights they will receive when owning your
NFTs.
The content of your license will largely depend on what you as the creator want to achieve.

Some licenses used by other projects:

* [Creative Commons licenses](https://creativecommons.org/2014/01/07/plaintext-versions-of-creative-commons-4-0-licenses/)
* [CantBeEvil licenses](https://github.com/a16z/a16z-contracts#cantbeevil-license)
* Custom licenses such as the [Marmotverse License](https://assets.marmotverse.io/spacemarmots/marmotverse_license.pdf)

When in doubt, consult a lawyer to pick the right license for your project. This is not legal advice.

Make sure to point to a plain text file or PDF file here.
Pointing to a website will only work if the content of the website never changes.

![minting collection selection](/img/web-minting/edition-3.png)

Upload the image or video you want to reference in each NFT of your edition.

![minting data selection](/img/web-minting/edition-4.png)

Finally, you can customize the rest of the metadata, such as a name and description of the individual NFTs, as well as the royalty percentage you want to enforce
on-chain.

Editions are currently offered as "Mint on Demand".
This means that the actual NFTs are not minted until it is purchased by a user.

You have to specifiy a sale price for which the individual NFTs will be offered.

All NFTs are being precommitted to the Chia blockchain using the Secure The Mint mechanism, so they can not be changed afterwards. 

Click “Mint NFT” and commit your NFTs to the blockchain!

![minting details](/img/web-minting/edition-5.png)

Your edition will now be uploaded, precommitted and awaited. After that, you can inspect the edition by clicking the preview!

![edition details](/img/web-minting/edition-6.png)

That’s it, you created an edition with just a few clicks and offered it to be minted on demand!
