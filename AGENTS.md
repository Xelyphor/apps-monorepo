https://immunefi.com/bug-bounty/ens/information/#top
Program Structure
This program contains two independent reward tracks. Each track has its own severity classifications and reward ranges. A vulnerability shall be classified under one track only.

Track A: Smart Contract Vulnerabilities
Track B: Websites and Applications Vulnerabilities
Cross-Track Classification: Where a vulnerability involves both smart contract and web/application components, it shall be classified under the track corresponding to the root cause of the vulnerability. For example, a signature verification flaw in a smart contract is a Track A vulnerability even if its effects are visible through a web interface.

Definitions & Calculations
Impact Assessment
For many ENS vulnerabilities, the primary impact is to name ownership or resolution integrity rather than direct theft of funds. ENS therefore uses a two-part framework to assess impact: (1) the scope of names affected, and (2) a financial calculation where applicable.

Part 1: Impact Scope
The scope of a vulnerability is assessed according to the following tiers:

Tier 1 — Systemic: The vulnerability affects all ENS names, or all names of a major type (e.g., all .eth 2LDs, all names using a particular resolver). Tier 1 vulnerabilities will generally be assessed at the upper end of the applicable severity range.

Tier 2 — Class-wide: The vulnerability affects a significant class of names (e.g., all DNS-imported names, all names registered through a specific registrar). Tier 2 vulnerabilities will generally be assessed at the mid-to-upper range.

Tier 3 — Conditional: The vulnerability affects a subset of names defined by external conditions (e.g., names under TLDs with weak DNSSEC keys, names using a deprecated resolver version). Tier 3 vulnerabilities will generally be assessed at the mid range, subject to the External Dependency Discount where applicable.

Tier 4 — Narrow: The vulnerability affects fewer than 50 individual names or accounts. Tier 4 vulnerabilities will generally be assessed at the lower end of the applicable severity range.

Within each tier, ENS will consider the categories of names affected. Not all names carry equal value or risk:

.eth 2LDs — highest value (primary ENS namespace, active secondary market, significant transaction volume)
DNS-imported names — moderate value (tied to external DNS ownership)
Subdomains — variable (depends on parent name usage and configuration)
Testnet names — lowest value (no real funds at risk)
Part 2: Financial Calculation
Where a vulnerability involves direct theft or misdirection of funds (e.g., draining ETH from a contract, redirecting payments), "funds directly affected" means the aggregate on-chain value that could be misappropriated, misdirected, locked, or destroyed through exploitation of the vulnerability at the time of report submission.

For Tier 4 (narrow) vulnerabilities affecting name ownership or resolution, the following supplementary methodology may be used:

The value of affected names may be calculated based on the most recent secondary market sale price or, if no sale has occurred, the annualized registration/renewal cost.

Potential misdirection of funds (e.g., payments sent to a wrong address due to hijacked resolution) may be calculated based on the trailing 90-day transaction volume to addresses resolved through the affected names.

Speculative or theoretical future losses are excluded from all calculations.

General Provisions
The following sections apply to all vulnerabilities reported.

Primacy of Impact vs. Primacy of Rules

Primacy of Impact means that the impact is prioritized rather than a specific asset. This encourages security researchers to report on all bugs with an in-scope impact, even if the affected assets are not in scope. For more information, please see Best Practices: Primacy of Impact.

Primacy of Impact submissions remain subject to the program’s reward calculation methodology, including impact-based scaling, the External Dependency Discount, and discretionary adjustment.

Feasibility Limitations
The project may be receiving reports that are valid (the bug and attack vector are real) and cite assets and impacts that are in scope, but there may be obstacles or barriers to executing the attack in the real world. In other words, there is a question about how feasible the attack really is. Conversely, there may also be mitigation measures that projects can take to prevent the impact of the bug, which are not feasible or would require unconventional action and hence, should not be used as reasons for downgrading a bug’s severity.

Therefore, Immunefi has developed a set of feasibility limitation standards which by default states what security researchers, as well as projects, can or cannot cite when reviewing a bug report.

Severity Assessment for XSS Reports
Injection of malicious content into app.ens.domains to initiate a malicious transaction without requiring unusual user interaction will be considered Critical.
Injection of malicious scripts into other ENS subdomains (besides app.ens.domains) that offer web3 wallet connections will be considered High for stored XSS and Medium for reflected XSS.
XSS on static ENS websites like metadata.ens.domains, which do not offer web3 functionality, will be considered low.


ENS
The Ethereum Name Service (ENS) is a distributed, open, and extensible naming system based on the Ethereum blockchain.

ENS's job is to map human-readable names like 'alice.eth' to machine-readable identifiers such as Ethereum addresses, other cryptocurrency addresses, content hashes, and metadata. ENS also supports 'reverse resolution', making it possible to associate metadata such as canonical names or interface descriptions with Ethereum addresses. ENS has similar goals to DNS, the Internet's Domain Name Service, but has significantly different architecture due to the capabilities and constraints provided by the Ethereum blockchain. Like DNS, ENS operates on a system of dot-separated hierarchical names called domains, with the owner of a domain having full control over subdomains.

Top-level domains, like '.eth' and '.test', are owned by smart contracts called registrars, which specify rules governing the allocation of their subdomains. Anyone may, by following the rules imposed by these registrar contracts, obtain ownership of a domain for their own use. ENS also supports importing in DNS names already owned by the user for use on ENS.

Because of the hierarchical nature of ENS, anyone who owns a domain at any level may configure subdomains — for themselves or others — as desired. For instance, if Alice owns 'alice.eth', she can create 'pay.alice.eth' and configure it as she wishes.

ENS is deployed on the Ethereum main network and on several test networks. If you use a library such as the ensjs Javascript library, or an end-user application, it will automatically detect the network you are interacting with and use the ENS deployment on that network.

For more information about ENS, please visit ens.domains

ENS provides rewards in USDC, denominated in USD. For more details about the payment process, please view the Reward Payment Terms section below.

Immunefi Vault Program

The ENS bug bounty program includes a public Immunefi Vault that transparently displays the funds allocated for bug bounty rewards. The vault is deployed on Ethereum and holds assets designated exclusively for vulnerability payouts.

Immunefi Standard Badge

By adhering to Immunefi’s best practice recommendations, ENS has satisfied the requirements for the Immunefi Standard Badge.
