Godot-Nebulas Sample project
=========

The following is a real barebones project with just the minimum required to use
Nebulas inside Godot-Nebulas fork.

Steps:
==

1. Create a new project (Skip to step 3 if cloning this repo)
![Create a project](/tutimg/001-create-project.png "Create a project")

2. Add the NebulasWalletSingleton in Project > Project settings > Autoload
![Add singleton](/tutimg/002-add-singleton.png "Add singleton")

3. Add a node below your root node (in this case a "Control" node)
![Add node](/tutimg/003-add-node.png "Add node")

4. Search for NebulasContractDeployer and click on "Create"
![Search contract deployer](/tutimg/004-contract-deployer.png "Search contract deployer")

5. Create a new wallet assigning a 6 character password (it gets created when you hit the 6 character minimum)
![Create wallet](/tutimg/005-set-password.png "Create wallet")

6. Change between nodes to let Godot update the properties on the inspector. Address should have your wallet's address. Your wallet private key is in your user-local directory (~/.local/share/godot on linux/mac, %appdata% on Windows), back it up securely as soon as possible to prevent fund loss. You should get some NAS in your wallet to issue contracts, tokens and do send operations. For testnet contracts you can use a testnet faucet (link at the end).
![Change nodes and get NAS into your wallet](/tutimg/006-change-backandforth-to-update.png "Change nodes and get NAS into your wallet")

7. Add a NebulasTransaction node as a child under your existing NebulasContractDeployer node.
![Add transaction node](/tutimg/007-add-transaction-object.png "Add transaction node")

8. **To create a NRC20 token** add a NebulasContractNRC20 as a child under your existing NebulasContractDeployer node.
![Add nrc20 contract](/tutimg/008-create-nrc20.png "Add nrc20 contract")

9. Configure your contract to your liking.
![Configure contract](/tutimg/009-setup-your-token.png "Configure contract")

10. Hit the "Deploy" checkbox and wait a bit, if there's no warning sign after some seconds (10 seconds tops) in your contract node, change back and forth between nodes to see the contract "Address" field updated with the new contract's address. You can check the deployment status on the Nebulas block explorer.
![Deploy contract](/tutimg/010-deploy-nrc20.png "Deploy contract")

11. Now you can send tokens to any address you want (on the same network) setting the "Send to Address" and "Send Amount" properties and hitting the "Send" checkbox. If there's no warning sign after some seconds (10 seconds tops) then you should check the operation on the block explorer.
![Send tokens](/tutimg/011-send-nrc20.png "Send tokens")

12. **To create a NRC721 token** add a NebulasContractNRC721 as a child under your existing NebulasContractDeployer node.
![Add nrc721 contract](/tutimg/012-create-nrc721.png "Add nrc721 contract")

13. Configure your contract to your liking and hit the deploy checkbox. If there's no warning sign after some seconds (10 seconds tops) your can change back and forth between nodes to check your new contract's address.
![Deploy nrc721](/tutimg/013-deploy-nrc721.png "Deploy nrc721")

14. To use NRC721 you need to add NFT nodes as a child to your NebulasContractNRC721.
![Add NFTs](/tutimg/014-add-nfts.png "Add NFTs")

15. Configure the "Asset title" and "Asset description" of your NFT. Hit the "Mint token" checkbox. If there's no warning sign after some seconds (10 seconds tops) you can change back and forth between nodes to see your generated "Token ID". You can associate an "Ingame Asset" scene and a "Wallet Asset" scene to each NFT so the token is associated with in-game and wallet assets that can be shown to the user. These can be changed without needing to re-mint the token again.
![Mint NFT](/tutimg/015-mint-nfts.png "Mint NFT")

16. Now you can transfer the newly minted to a "live" wallet so you use them in testing or distribute to a seed user in production.
![Transfer NFT](/tutimg/016-transfer-nfts.png "Transfer NFT")

Links:
==

- Testnet faucet https://testnet.nebulas.io/claim/

License:
==

MIT licensed
