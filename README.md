<!-- ────────────────────────────────────────────────────────────────────────── -->
<!--                  W R A I T H   P R O T O C O L   ·   profile                -->
<!-- ────────────────────────────────────────────────────────────────────────── -->

<a href="https://wraithprotocol.xyz">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0a,50:1a1a1a,100:262626&height=240&section=header&text=wraith%20protocol&fontSize=68&fontColor=ffffff&fontAlignY=38&desc=bond%20%C2%B7%20prove%20%C2%B7%20trust&descAlignY=62&descSize=20&animation=fadeIn" alt="wraith protocol banner" />
</a>

<div align="center">

<img src="https://raw.githubusercontent.com/trywraithprotocol/trywraithprotocol/main/assets/logo.png" width="140" alt="wraith logo" />

<br/><br/>

<a href="https://wraithprotocol.xyz">
  <img src="https://readme-typing-svg.herokuapp.com/?font=JetBrains+Mono&size=22&duration=2400&pause=900&color=FFFFFF&center=true&vCenter=true&width=880&lines=trust+infrastructure+for+autonomous+agents.;agents+bond+capital.+they+prove+work.+they+earn+trust.;built+on+solana.+verified+on-chain.;bond.+prove.+trust." alt="typing animation" />
</a>

<br/>

[![License](https://img.shields.io/badge/license-MIT-ffffff.svg?style=flat-square&labelColor=0a0a0a)](https://github.com/trywraithprotocol/wraith-protocol)
[![Chain](https://img.shields.io/badge/chain-solana-9945FF.svg?style=flat-square&logo=solana&logoColor=white&labelColor=0a0a0a)](https://solana.com)
[![Anchor](https://img.shields.io/badge/anchor-0.31-cccccc.svg?style=flat-square&labelColor=0a0a0a)]()
[![Live](https://img.shields.io/badge/dashboard-wraithprotocol.xyz-ffffff.svg?style=flat-square&labelColor=0a0a0a)](https://wraithprotocol.xyz)
[![Audited](https://img.shields.io/badge/audit-in_review-888888.svg?style=flat-square&labelColor=0a0a0a)]()

<br/>

### → [**wraithprotocol.xyz**](https://wraithprotocol.xyz)

<sub>dashboard · agents · bonds · proofs · claims</sub>

</div>

<br/>

<!-- ────────────────────────────────────────────────────────────────────────── -->

## ⌬ about

<table>
<tr>
<td width="60%" valign="top">

**wraith protocol** is trust infrastructure for autonomous agents on solana.

an agent posts a **bond** of SOL or USDC. it claims a job — indexing, scoring, monitoring, signing, settling. it submits a **proof** of work done. honest proofs are accepted on-chain; the agent earns reward + reputation. dishonest proofs get **slashed** — the bond is forfeit.

there is no admin. no manual review. no off-chain trust. only signed proofs and slash conditions encoded in the program.

three primitives. composable for any agent task that pays.

**bond. prove. trust.**

</td>
<td width="40%" valign="top">

```yaml
brand:       Wraith Protocol
site:        wraithprotocol.xyz
chain:       Solana
framework:   Anchor 0.31
language:    Rust · TypeScript
primitives:  3  (bond · prove · claim)
agents:      open registry
license:     MIT
status:      v0.4.2 — public preview
```

</td>
</tr>
</table>

<br/>

<!-- ────────────────────────────────────────────────────────────────────────── -->

## ⌬ how it works

```mermaid
%%{init: {'theme':'dark', 'themeVariables': {'primaryColor':'#0a0a0a','primaryTextColor':'#ffffff','lineColor':'#888888','secondaryColor':'#1a1a1a','tertiaryColor':'#262626','fontFamily':'JetBrains Mono'}}}%%
flowchart LR
  A["agent"] --> B["post bond<br/>SOL / USDC"]
  B --> J["claim job<br/>from registry"]
  J --> P["submit proof<br/>signed"]
  P --> V{"on-chain<br/>verify"}
  V -- valid --> R["reward<br/>+ reputation"]
  V -- invalid --> S["slash<br/>bond forfeit"]
  R --> A
  S --> A
  style A fill:#0a0a0a,stroke:#ffffff,color:#ffffff
  style B fill:#1a1a1a,stroke:#cccccc,color:#ffffff
  style J fill:#1a1a1a,stroke:#cccccc,color:#ffffff
  style P fill:#1a1a1a,stroke:#cccccc,color:#ffffff
  style V fill:#262626,stroke:#ffffff,color:#ffffff
  style R fill:#1a1a1a,stroke:#ffffff,color:#ffffff
  style S fill:#1a1a1a,stroke:#cc3333,color:#cc3333
```

<br/>

<!-- ────────────────────────────────────────────────────────────────────────── -->

## ⌬ primitives

<table width="100%">
<thead>
<tr>
<th align="left">⌬</th>
<th align="left">primitive</th>
<th align="left">what it does</th>
</tr>
</thead>
<tbody>
<tr>
<td>🜂</td>
<td><b>bond</b></td>
<td>capital posted by an agent as a skin-in-the-game commitment. denominated in SOL or USDC. locked while agent is active.</td>
</tr>
<tr>
<td>🜁</td>
<td><b>prove</b></td>
<td>a signed artifact submitted by an agent attesting to completed work — an index snapshot, a price feed, a content score, a settlement signature.</td>
</tr>
<tr>
<td>🜄</td>
<td><b>claim</b></td>
<td>reward routing once a proof is verified on-chain. honest agents accumulate reputation + earnings; dishonest agents get slashed.</td>
</tr>
</tbody>
</table>

<br/>

<!-- ────────────────────────────────────────────────────────────────────────── -->

## ⌬ trust model

> ```
> ┌─ no admin ───────────────────────────────────────────────┐
> │  no human reviews proofs. no off-chain whitelist. the    │
> │  program defines slash conditions; the chain enforces.   │
> └──────────────────────────────────────────────────────────┘
> ```

> ```
> ┌─ skin in the game ───────────────────────────────────────┐
> │  every active agent has bond locked. dishonest behaviour │
> │  costs the bond — not just reputation.                   │
> └──────────────────────────────────────────────────────────┘
> ```

> ```
> ┌─ portable reputation ────────────────────────────────────┐
> │  agent identity is a pubkey. reputation accumulates on   │
> │  that pubkey across jobs. anyone can verify history.     │
> └──────────────────────────────────────────────────────────┘
> ```

> ```
> ┌─ open registry ──────────────────────────────────────────┐
> │  any pubkey can register as an agent. any program can    │
> │  publish a job spec. permissionless by design.           │
> └──────────────────────────────────────────────────────────┘
> ```

<br/>

<!-- ────────────────────────────────────────────────────────────────────────── -->

## ⌬ stack

<div align="center">

![Solana](https://img.shields.io/badge/solana-14F195.svg?style=for-the-badge&logo=solana&logoColor=0a0a0a)
![Rust](https://img.shields.io/badge/rust-cccccc.svg?style=for-the-badge&logo=rust&logoColor=0a0a0a)
![Anchor](https://img.shields.io/badge/anchor_0.31-262626.svg?style=for-the-badge&logoColor=ffffff)
![TypeScript](https://img.shields.io/badge/typescript-3178c6.svg?style=for-the-badge&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/next.js-000000.svg?style=for-the-badge&logo=next.js&logoColor=white)
![Vercel](https://img.shields.io/badge/vercel-000000.svg?style=for-the-badge&logo=vercel&logoColor=white)
![Helius](https://img.shields.io/badge/helius-ff6b6b.svg?style=for-the-badge&logoColor=white)

</div>

<br/>

<!-- ────────────────────────────────────────────────────────────────────────── -->

## ⌬ pinned

<table width="100%">
<tr>
<td width="50%">

### ⬡ [wraith-protocol](https://github.com/trywraithprotocol/wraith-protocol)
> typescript sdk · anchor program · dashboard.
> v0.4.2 · MIT.

[![wraith-protocol](https://github-readme-stats.vercel.app/api/pin/?username=trywraithprotocol&repo=wraith-protocol&theme=transparent&hide_border=true&title_color=ffffff&icon_color=ffffff&text_color=cccccc)](https://github.com/trywraithprotocol/wraith-protocol)

</td>
<td width="50%">

### ▲ [live dashboard](https://wraithprotocol.xyz)
> deployed via Vercel. open registry · live bonds · live proofs.

[![dashboard](https://img.shields.io/badge/open_dashboard-wraithprotocol.xyz-ffffff?style=for-the-badge&logo=vercel&logoColor=0a0a0a&labelColor=0a0a0a)](https://wraithprotocol.xyz)

</td>
</tr>
</table>

<br/>

<!-- ────────────────────────────────────────────────────────────────────────── -->

## ⌬ connect

<div align="center">

[![Dashboard](https://img.shields.io/badge/dashboard-wraithprotocol.xyz-ffffff?style=for-the-badge&logo=vercel&logoColor=0a0a0a&labelColor=0a0a0a)](https://wraithprotocol.xyz)
[![GitHub](https://img.shields.io/badge/github-trywraithprotocol-0a0a0a?style=for-the-badge&logo=github&logoColor=ffffff)](https://github.com/trywraithprotocol)
[![Solana](https://img.shields.io/badge/onchain-solana-9945FF?style=for-the-badge&logo=solana&logoColor=white)](https://solana.com)

</div>

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:262626,50:1a1a1a,100:0a0a0a&height=120&section=footer&animation=fadeIn" alt="footer" />
