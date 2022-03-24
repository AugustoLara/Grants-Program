# W3F Grant Proposal

- **Project Name:** Afloat's Tax Infraestructure Polkadot Integration
- **Team Name:** Afloat Inc.
- **Payment Address:** BTC Louise to provide a BTC address
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2


## Overview

[Afloat](https://stayafloat.io/#/) is one of the first real use-cases of blockchain technology in the accounting industry. It enables the fractional buying and selling of tax credits that historically have been inefficient, opaque and centralized. It has already processed tax credits ranging in orders from $2K -$70k USD.

It was built on a private Ethereum clone but due to Polkadot technology and identity management, it’s applying for a grant to migrate.

## Project Details
### Context

A common tax credit is for land preservation. The inhabitants of a geographic area recognize that their shared quality of life may be positively impacted if more land was preserved rather than developed. If the owner of land property in that area agrees to preserve land, they may be eligible to receive a tax credit in an amount associated with the value of the land property.

A tax credit only reduces the tax liability for the holder of the tax credit, and they expire at various durations. A common scenario is for a taxpayer to earn tax credits well beyond their tax liability over the effective lifespan of a credit. However, some owners of tax credits do not have enough tax liability to take full advantage of the reward. Because of this, a number of states allow credits to be transferred. State transferable tax credits are typically bought and sold at a discount.

Historically, the tax credit industry’s transfer process has been opaque. Due to a lack of trust between buyers and sellers, accountants and lawyers act as middlemen. This added financial and procedural cost creates a barrier for the majority of taxpayers to enter the tax credit market. What remains is a tight-knit group of wealthy buyers, sellers, and policymakers.

## Product

Afloat uses blockchain technology to add trust and liquidity to the market, allowing smaller fractionable shares of tax credits to be transferred. So far, Afloat has facilitated the transfer of $145,000 worth of tax credits between multiple buyers and sellers, 90% with whom Afloat anticipates an ongoing relationship. One of the platform’s sellers is an international company with over 10,000 employees, and the value of tax credits purchased per buyer has so far ranged between less than $2,000 and over $70,000.

Afloat has a total of 108 active users. Many of these are CPAs (public accountants) and represent a network of taxpayers (credit buyers and sellers). We purposefully haven't had any marketing campaigns, and have been cautious with growth so far. We had a large batch of users enroll in December 2021 (end of tax year) and material increase (4x) year over year."

Having started in the US, Afloat, Inc., a Wyoming company, is compliant with existing federal, state, and local regulations and takes care of the entire transfer process with the following functions:

- Uploading proof of tax credit ownership
<p align="center">
  <img width="700" src="https://user-images.githubusercontent.com/7217054/159963378-b850c316-aa28-46ea-9a87-2e184de57a0d.png">
</p>
<br />

- Linking a US bank account
<p align="center">
  <img width="700" src="https://user-images.githubusercontent.com/7217054/159963375-a06565dc-9f19-4aa9-8e31-a6223aa2cef8.png">
</p>
<br />

- Fiat integration using Dwolla, a third party company
- Placing buy and sell limit orders on blockchain
<p align="center">
  <img width="700" src="https://user-images.githubusercontent.com/7217054/159963749-d7e2ef89-fac0-4f4c-a823-9dd3a4e9d263.png">
</p>
<br />

- Algorithmic matching overlapping full or partial orders in a ”pending” status while waiting for government approval
<p align="center">
  <img width="700" src="https://user-images.githubusercontent.com/7217054/159963752-dc5f9323-1d07-4bc5-b309-ab2147ff71b8.png">
</p>
<br />

- Autopopulate tax forms with blockchain data (Afloat supports five of thirty-six US tax forms)
- Completion of government paperwork and money transfer after government approval

### Migration & Deployment

Initially we will be run on a standalone chain as a pallet. This provides the most latitude and flexibility. The initial phase is primarily focused on function, usability, and ensuring the core asset type design is secure and composable. It also includes existing user and asset migration. We will have a one-time process per user to teleport their account and assets. Most likely, we will not teleport any orders or redemptions currently in process. They would close out on the old platform, and users would create new ones after they migrate.

We did not include any scope or fund request in the proposal related to the migration work. The scope of the w3f proposal is focused on building the open source components. These will be available for the community, and Afloat will be an implementation of them. Making the pallets and tooling as general purpose as possible should help with reusability, for us and other projects.

To handle fractional tax credits in Substrate we are using "fruniques". That is our name for *FRactional UNIQUES*. It'll be compatible with the Uniques pallet and eventually with RMRK as well. It allows the user to spawn a new NFT from an existing NFT, repeatedly, while specifying an associated amount. The integrity of the total quantity must remain intact, along with metadata, but each of these NFTs can be priced, transferred, and redeemed individually.

An earlier implementation of this used a fungible token to represent the parts of the tax credit, but we've found that fractional NFTs fit the mental model a bit better and also fits more ergonomically in existing tools. A user is buying a "thing", see that thing in their wallet, where they may hold 7 of them. Holding various quantities of 7 different fungible tokens seemed to increase the complexity more than necessary. This is a design element we frequently brainstorm on though. In a future release, it may be useful to have fruniques support both use cases.


### Project Details

We expect the teams to already have a solid idea about your project's expected final state. Therefore, we ask the teams to submit (where relevant):

- Mockups/designs of any UI components
- Data models / API specifications of the core functionality
- An overview of the technology stack to be used
- Documentation of core components, protocols, architecture, etc. to be deployed
- PoC/MVP or other relevant prior work or research on the topic
- What your project is _not_ or will _not_ provide or implement
  - This is a place for you to manage expectations and to clarify any limitations that might not be obvious

## Ecosystem Fit

Help us locate your project in the Polkadot/Substrate/Kusama landscape and what problems it tries to solve by answering each of these questions:

- Where and how does your project fit into the ecosystem?
- Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?
- What need(s) does your project meet?
- Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?
  - If so, how is your project different?
  - If not, are there similar projects in related ecosystems?

The benefit for our users, besides the security, would be compatibility for liquidity. Tax Credits trade with a heavy discount to face value, and Polkadot participants will likely want to hold them during that lifespan even if they aren't the final redeemer.  If a 5-year expiration credit is priced at $0.60-to-the-dollar by its impatient originator, it could be purchased via a more patient market maker to perhaps be sold at $0.90 in year 3 or 4, just as an example.

## Community

As the perfect technology for record-keeping, blockchain makes a lot of sense for accountants. Afloat not only wants to bring its infrastructure to Polkadot but also bring Polkadot into the accounting community with the following:

#### Continuing Education for CPAs
Afloat’s founder and current CEO [Louise Reed](https://www.linkedin.com/in/louisewreed/) has given talks at a number of CPE conferences, where CPAs receive continuing education credits to maintain their licenses each year. Introducing her to Web 3 infrastructure would allow her to speak about it at CPA conferences, especially to other CPAs looking for classes covering new and interesting topics and ideas.

#### Blockchain/Crypto Clients

Working in a historically conservative industry, CPAs are starting to feel the push from blockchain/crypto clients to accept the new technology and are now being forced to help with risk mitigation (alongside lawyers).

#### Sellers

Typically, sellers of tax credits are large international businesses, which are usually slow with internal changes. However, familiarity with the tax credit market paves the way for an easier introduction to a new technology.

#### Buyers
Introducing programming/blockchain/crypto taxpayers to tax savings by way tax credits would bring new customers to a marketplace that has a strong history of centralization, opacity, and insularity.

#### Bridging Communities
Afloat would naturally bridge two opposing communities: accounting, one of the most trusted and conservative industries, and blockchain, one of the most innovative industries. By association with such a trusted industry, blockchain would receive credibility in the eyes of the general public while also modernizing accounting with new and better processes.

#### Natural Use Case

There is a huge educational and technological divide in the learning curve for accountants when it comes to blockchain, but Afloat adds an easy and natural way to learn.  Most people, including CPAs and businesses, tend to understand only what they can see and experience, and Afloat brings tangibility to an otherwise intangible industry.


## Team :busts_in_silhouette:

### Team members

- Name of team leader
- Names of team members

### Contact

- **Contact Name:** Full name of the contact person in your team
- **Contact Email:** Contact email (e.g. john@duo.com)
- **Website:**

### Legal Structure

- **Registered Address:** Address of your registered legal entity, if available. Please keep it in a single line. (e.g. High Street 1, London LK1 234, UK)
- **Registered Legal Entity:** Name of your registered legal entity, if available. (e.g. Duo Ltd.)

### Team's experience

Please describe the team's relevant experience. If your project involves development work, we would appreciate it if you singled out a few interesting projects or contributions made by team members in the past. For research-related grants, references to past publications and projects in a related domain are helpful.

If anyone on your team has applied for a grant at the Web3 Foundation previously, please list the name of the project and legal entity here.

### Team Code Repos

- https://github.com/<your_organisation>
- https://github.com/<your_organisation>/<project_1>
- https://github.com/<your_organisation>/<project_2>

Please also provide the GitHub accounts of all team members. If they contain no activity, references to projects hosted elsewhere or live are also fine.

- https://github.com/<team_member_1>
- https://github.com/<team_member_2>

### Team LinkedIn Profiles (if available)

- https://www.linkedin.com/<person_1>
- https://www.linkedin.com/<person_2>

## Development Status :open_book:

If you've already started implementing your project or it is part of a larger repository, please provide a link and a description of the code here. In any case, please provide some documentation on the research and other work you have conducted before applying. This could be:

- links to improvement proposals or [RFPs](https://github.com/w3f/Grants-Program/tree/master/rfp-proposal) (requests for proposal),
- academic publications relevant to the problem,
- links to your research diary, blog posts, articles, forum discussions or open GitHub issues,
- references to conversations you might have had related to this project with anyone from the Web3 Foundation,
- previous interface iterations, such as mock-ups and wireframes.

## Development Roadmap :nut_and_bolt:

This section should break the development roadmap down into milestones and deliverables. To assist you in defining it, we have created a document with examples for some grant categories [here](../docs/grant_guidelines_per_category.md). Since these will be part of the agreement, it helps to describe _the functionality we should expect in as much detail as possible_, plus how we can verify and test that functionality. Whenever milestones are delivered, we refer to this document to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions, it should be clear how your project is related to Substrate, Kusama or Polkadot. We _recommend_ that teams structure their roadmap as 1 milestone ≈ 1 month.

For each milestone,

- make sure to include a specification of your software. _Treat it as a contract_; the level of detail must be enough to later verify that the software meets the specification.
- include the amount of funding requested _per milestone_.
- include documentation (tutorials, API specifications, architecture diagrams, whatever is appropriate) in each milestone. This ensures that the code can be widely used by the community.
- provide a test suite, comprising unit and integration tests, along with a guide on how to set up and run them.
- commit to providing Dockerfiles for the delivery of your project.
- indicate milestone duration as well as number of full-time employees working on each milestone.
- **Deliverables 0a-0d are mandatory for all milestones**, and deliverable 0e at least for the last one. If you do not intend to deliver one of these, please state a reason in its specification (e.g. Milestone X is research oriented and as such there is no code to test).

> :zap: If any of your deliverables is based on somebody else's work, make sure you work and publish _under the terms of the license_ of the respective project and that you **highlight this fact in your milestone documentation** and in the source code if applicable! **Teams that submit others' work without attributing it will be immediately terminated.**

### Overview

- **Total Estimated Duration:** Duration of the whole project (e.g. 2 months)
- **Full-Time Equivalent (FTE):**  Average number of full-time employees working on the project throughout its duration (see [Wikipedia](https://en.wikipedia.org/wiki/Full-time_equivalent), e.g. 2 FTE)
- **Total Costs:** Requested amount in USD for the whole project (e.g. 12,000 USD). Note that the acceptance criteria and additional benefits vary depending on the [level](../README.md#level_slider-levels) of funding requested. This and the costs for each milestone need to be provided in USD; if the grant is paid out in Bitcoin, the amount will be calculated according to the exchange rate at the time of payment.

### Milestone 1 Example — Implement Substrate Modules

- **Estimated duration:** 1 month
- **FTE:**  2
- **Costs:** 8,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| 0c. | Testing Guide | Core functions will be fully covered by unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)
| 1. | Substrate module: X | We will create a Substrate module that will... (Please list the functionality that will be implemented for the first milestone) |  
| 2. | Substrate module: Y | We will create a Substrate module that will... |  
| 3. | Substrate module: Z | We will create a Substrate module that will... |  
| 4. | Substrate chain | Modules X, Y & Z of our custom chain will interact in such a way... (Please describe the deliverable here as detailed as possible) |  


### Milestone 2 Example — Additional features

- **Estimated Duration:** 1 month
- **FTE:**  1
- **Costs:** 4,000 USD

...


## Future Plans

Please include here

- how you intend to use, enhance, promote and support your project in the short term, and
- the team's long-term plans and intentions in relation to it.

Once operational, we will start the Polkadot integration. Most of our current users, in comparison to most Defi projects, are high dollar volume yet relatively low count of orders. Without a need for high frequency (every block), we don't see it as a good fit for a parachain. A parathread may be a good fit. XCM may also be a good fit, but I haven't explored how to use that yet. Maybe an option is to deploy a smart contract to a parachain and teleport assets there (or Statemint?). Centrifuge has infrastructure for somewhat similar IRL assets. We would look to collaborate with similar projects and adopt or help build an integration pattern that is the most composable for the asset type.


## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Web3 Foundation Website / Medium / Twitter / Element / Announcement by another team / personal recommendation / etc.

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:

- Work you have already done.
- If there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.
