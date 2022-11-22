# PRFAQ - AutoTx - a Metamask Snap

Team Members:
- David Ryan (Dcentralab, @davidryan59 on GitHub and Twitter, drcoder.eth)
- Alex (Portofino/HomeDAO, @alexcheema on GitHub)

## Summary

A new Metamask Snap **AutoTx** allows specific transaction profiles to be automatically signed and submitted to the blockchain, bypassing the Metamask pop-up window and allowing a smooth in-game experience.

## Problem
Every time a web3 game wants to do an in-game transaction, a Metamask window pops up to sign the transaction, which offers bad UX by breaking the flow of the game.

## Solution
Metamask Snaps can be used to sign transactions on the user's behalf in a secure execution environment.

To ensure user safety, **AutoTx** will clearly define which smart contract and function can be called, as well as the range of acceptable parameters.

## Getting Started
The snap prototype will consist of the following functionality:
* Specifying:
  * Smart contract address
  * Specific function being called on the contract
  * Some fixed inputs for the function (if needed)
  * If there are numeric inputs, narrow down ranges allowed, such as specifying 0 to 20 USDC to be spent, or a limit on game token to be spent
* Some simple use cases:
  * Press an in-game button ("Stroke the Pet" demo, or Claim! Withdraw! Pet Aavegotchi!) which has no parameters and can happen repeatedly
  * Pay for in-game item with tokens (parameter in the snap acts as an ERC-20 allowance, limiting how many tokens can be spent automatically)
  * Consume NFT as in-game item

## FAQ
**Who will use this?**
* Game developers who want users to be able to use an existing Metamask-generated wallet (Account 1, Account 2, etc) to pay for in-game items

**What problem does this really solve?**
* Annoying Metamask pop-up windows that break the game UX

**Is this just another walled garden designed to monetize something that's freely available?**
* **No.** The entire platform is open sourced. The code is on GitHub, and **AutoTx** Snap will be available as an `npm` module

**Ok.. then how do you make money?**
* For token send transactions, take a tiny cut (e.g. 0.1%) and send to team Gnosis Safe

**How do I know the contracts are secure?**
* Metamask Snaps must be published as `npm` modules. Code is open-source, and can be inspected by anyone. Code ought to be audited before opening up to users. When Metamask is ready to open up Snaps to end users, we expect Metamask will insist on audits.
* We assume that if the `npm` module gets upgraded then the Metamask Snap will still use the previous version of the `npm` module which has been audited.

### AutoTx Roadmap

- [x] AutoTx PRFAQ Live
- [x] AutoTx MVP released at end of Sozu Haus hacker house ("Stroke the Pet" game, both painful and smooth versions, where "painful" has Metamask prompts, and "smooth" bypasses the Metamask prompts using a Snap)
- [ ] Snap is generalised to more contracts and functions
- [ ] Ranges of allowable values (USDC, game tokens) can be specified
- [ ] Facility to log-out after 12 hours (or 1 week / month)
- [ ] First version of this Snap is released on NPM, and audited
- [ ] Snaps are live in main Metamask (as well as Metamask Flask)
- [ ] Promoting this Snap to game devs to smooth the UX for their users
