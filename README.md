# Vast

Vast is a minimal, IBC compatible blockchain framework that:

* supports MoveVM
* provides intefaces for pluggalbe contract languages
* introduces the concept of `compiler nodes`

It can be used to build proof of stake or proof of authority blockchains.  By default chains start as single node proof of authority chains, and scale into multi node proof of stake chains.

Developers using Vast as a framework are expected to develop applications largely using language models and generative AI, but of course manual software development is always permitted.  The small size and single repository nature of the Vast framework ensures that Vast is:

* easy for humans to grasp and audit
* easy for language models to understand

## Structure

Vast is a monorepo, and all critical compoennts exist in this repository.

## Components

* BFT Consensus with:
  * ABCI
  * BLS block signatures
  * a multi-chain p2p network that is segmented by chain and seeded by hard-coded public addresses in the style of Bitcoin
  * full finality

* Bootloader
  * the bootloader is a easy to configure "starting state" for a POA/POS infrastructure token
  * The bootloard provides interfaces so that immutable, non-contract logic can be implemented
  * Provides a native means of ERC20/CW20/SPL tokens

* Contracts
  * MoveVM
  * a pluggable set of contract interfaces, so that novel contract standards are easy to implement
  * a contract standard that is uploaded as source code

### Compiler Nodes

current contract standards have a single, shared, significant flaw:  they accept contract uploads in binary form, instead of source.  No matter the contract language, vast attempts to set a cultural standard, enforced by technology, that smart contracts become critical blockchain infrastructure and therfore should always be uploaded as source code.

In Vast terminology, a "compiler" is a type of node that serves the network by compiling contract source code into binaries.  Complier nodes allow the network to provide a unique certainty about exactly which source code maps to exactly which contract binary.

We believe that this may lead to entirely new types of contracts that may resemble more robust applications, but decline to speculate on what form these may take.

## ICP Canister Launch

We are studying the idea of making our initial launch as an ICP canister, because this will theoretically allow us to bootstrap more easily than we otherwise could.  

## Programming Language

Our intent is to provide for multiple implementations of Vast quite early on .  We feel that multi client is a necessity because multiclient networks are naturally more robust.

/ - readme and such
/rust - rust implementation
/v - vlang implementation
/zig - zig implementation

....If you wish to impelment a vast client, JFDI!  Make a new folder and a pull request.

## Vast P2P

Given that shared security:

* Seems to always fail
* likely does not exist due to natural conflicts of interest

....vast is a network of independent chains that don't depend on one another.  In order to ensure that user experience is excellent, every Vast node has addresses on every network.  Later, it will be possible for chain A to serve as one of chain B's validators (we think).  This should help single-node networks to be more secure.

## Licensing

Vast is BSL / MIT licensed.  An automatic, perpetual license is given to user communities who use the default economic template.

The default Vast economic template:

* Assigns 3% of staking token supply to "vast coordinating thingy"
* 1/3rd of this is given directly to tokenholders
* 2/3rd of this is given to "vast coordinating thingy" to pay for developkent and support of Vast

## Support

Developers and entrepeneurs pursuing projects in vast should expect:

* support in the ideation, design, and execution of technical features
* referral to a vast network of venture investors
* tooling to allow ICOs that resemble ethereum/eos
* a fantastic contributing experience

## Contribution

Vast contributrs earn from contributing.  Provided that our ideas work, there should be no concept of `unpaid contributor` in this, the vast core repository.

## Distribution

We intend to distribute Vast approximately 1:1 to holders of QCK.  We may distribute some vast to other communities.  Contributors to vast may recieve vast tokens.  No promise whatsoever is made:

* We may or may not complete vast
* Vast may fail catastrophically
* QCK holders may or may not recieve vast tokens
* OSMO holders may or may not recieve vast tokens
* uWu holders may or may not recieve vast tokens
  * vast may or may not occupy a uWu memoji slot
* Surely we would never give a single token to the remilia ecosystem

## BDFLs

For the sake of clarity and efficiency, Vast core has two BDFLs, Joe Bowman and Jacob Gadikian.  To prevent slavery, either BDFL may suspend their BDFLness at any time of their choosing, and reinstate their BDFLness at any time of their choosing.  There are no other BDFLs.

## Acknwoledgements

The ideas behind Vast come from about 30 years (combined) of experience building blockchain technology hands on.  Along the way, our team has had the opportunity to work with incredible builders:

* Osmosis Team
* Sunny King
* Dan Larimer
* Jae Kwon

Vast comes from turmoil, and we wish to thank the teams and individuals who invested in Quicksilver and delegated to Notional.  We believe that Vast addresses key issues in the design, launch, and maintenance of proof of stake blockchain networks and that lack of growth in Proof of Stake is due to lack of imagination and intellectual diversity.  

## FAQ: Frequently Asked Questions

### Why not just ship a single chain, instead of shipping a framework for others to build chains?

Our experince indicates that there is enormous value in allowing full consensus level customization of blockchains.  We believe that this will allow for the vast network to produce fundamentally better applications, and to allow for riskier products with safer failure modes.  Vast core will be the most conservative implementation of the stack, making it appropriate as a well-audited, hardened and well understood base for new applications.  

### But isn't Solana fucking awesome?

YES, and if Vast core doesn't achieve solana level performance with full finality, we aren't meeting our performance goals.  

### If solana is so fucking awesome why not just be a single chain?

Any time we work without full finality, full provabilty, the abilty to modify consensus, and more, we feel sad as developers.  We want a community of happy developers, so we wish to ensure that any developer working on or with Vast Core software can easily have total control and launch their own network.  

### If you love the devs so much why can't they use the Vast Core code without providing some % of supply to Vast Core?

We love the devs so much that we are taking the time to ensure that we're always well-positioned to provide more and better support than they'd get on Substrate, Cosmos-SDK, Hyperledger, a random geth fork, or any other blockchain framework.

### Did you say fuck?

Yes, and if that bothers you, please use another blockchain framework.
