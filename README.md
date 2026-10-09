# SONIC

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-search_engines-lightgrey)

> Anticloud-hardened packaging of the upstream project `SONIC` in category **SEARCH ENGINES**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** SEARCH ENGINES · **Upstream:** https://github.com/valeriansaliou/sonic · **Upstream pin:** `f7a75d25eb07d0e16456cb0a4098496dd8674c0e` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# Sonic

[![dependency status](https://deps.rs/project/github/valeriansaliou/sonic/status.svg)](https://deps.rs/project/github/valeriansaliou/sonic) [![Buy Me A Coffee](https://img.shields.io/badge/buy%20me%20a%20coffee-donate-yellow.svg)](https://www.buymeacoffee.com/valeriansaliou)

**Sonic is a fast, lightweight and schema-less search backend. It ingests search texts and identifier tuples that can then be queried against in a microsecond's time.**

Sonic can be used as a simple alternative to super-heavy and full-featured search backends such as Elasticsearch in some use-cases. It is capable of normalizing natural language search queries, auto-completing a search query and providing the most relevant results for a query. Sonic is an identifier index, rather than a document index; when queried, it returns IDs that can then be used to refer to the matched documents in an external database.

A strong attention to performance and code cleanliness has been given when designing Sonic. It aims at being crash-free, super-fast and puts minimum strain on server resources (our measurements have shown that Sonic - when under load - responds to search queries in the μs range, eats ~30MB RAM and has a low CPU footprint; [see our benchmarks](https://github.com/valeriansaliou/sonic#how-fast--lightweight-is-it)).

_Tested at Rust version: `rustc 1.98.0 (88d9e12ae 2026-08-18)`_

**🇫🇷 Crafted in Nantes, France.**

**📰 The Sonic project was initially announced in [a post on my personal journal](https://journal.valeriansaliou.name/announcing-sonic-a-super-light-alternative-to-elasticsearch/).**

![Sonic](https://valeriansaliou.github.io/sonic/images/banner.jpg)

> _« Sonic » is the mascot of the Sonic project. I drew it to look like a psychedelic hipster hedgehog._

## Who uses it?

<table>
<tr>
<td align="center"><a href="https://crisp.chat/"><img src="https://valeriansaliou.github.io/sonic/images/logo-crisp.png" width="64" alt="Crisp logo" /></a></td>
<td align="center"><a href="https://scrumpy.io/"><img src="https://valeriansaliou.github.io/sonic/images/logo-scrumpy.png" width="64" alt="Scrumpy logo" /></a></td>
</tr>
<tr>
<td align="center">Crisp</td>
<td align="center">Scrumpy</td>
</tr>
</table>

_👋 You use Sonic and you want to be listed there? [Contact me](https://valeriansaliou.name/)._

## Demo

Sonic is integrated in all Crisp search products on the [Crisp](https://crisp.chat/) platform. It is used to index half a billion objects on a $5/mth 1-vCPU SSD cloud server (as of 2019). Crisp users use it to search in their messages, conversations, contacts, helpdesk articles and more.

**You can test Sonic live on: [Crisp Helpdesk](https://help.crisp.chat/), and get an idea of the speed and relevance of Sonic search results. You can also test search suggestions from there: start typing at least 2 characters for a word, and get suggested a full word (press the tab key to expand suggestion). _Both search and suggestions are powered by Sonic._**

![Demo on Crisp Helpdesk search](https://valeriansaliou.github.io/sonic/images/crisp-search-demo.gif)

> _Sonic fuzzy search in helpdesk articles at its best. Lookup for any word or group of terms, get results instantly._

## Features

* **Search terms are stored in collections, organized in buckets**; you may use a single bucket, or a bucket per user on your platform if you need to search in separate indexes.
* **Search results return object identifiers**, that can be resolved from an external database if you need to enrich the search results. This makes Sonic a simple word index, that points to identifier results. Sonic doesn't store any direct textual data in its index, but it still holds a word graph for auto-completion and typo corrections.
* **Search query typos are corrected** if there are not enough exact-match results for a given word in a search query, Sonic tries to correct the word and tries against alternate words. You're allowed to make mistakes when searching.
* **Insert and remove items in the index**; index-altering operations are light and can be committed to the server while it is running. A background tasker handles the job of consolidating the index so that the entries you have pushed or popped are quickly made available for search.
* **Auto-complete any word** in real-time via the suggest operation. This helps build a snappy word suggestion feature in your end-user search interface.
* **Full Unicode compatibility** on 80+ most spoken languages in the world. Sonic removes useless stop words from any text (eg. 'the' in English), after guessing the text language. This ensures any searched or ingested text is clean before it hits the index; [see languages](https://github.com/valeriansaliou/sonic#which-text-languages-are-supported).
* **Simple protocol (Sonic Channel)**, that let you search your index, manage data ingestion (push in the index, pop from the index, flush a collection, flush a bucket, etc.) and perform administrative actions. Sonic Channel was designed to be lightweight on resources and simple to integrate with; [read protocol specification](https://github.com/valeriansaliou/sonic/blob/master/PROTOCOL.md).
* **Easy-to-use libraries**, that let you connect to Sonic from your apps; [see libraries](https://github.com/valeriansaliou/sonic#-sonic-channel-libraries).

## How to use it?

### Installation

Sonic is built in Rust. To install it, either download a version from the [Sonic releases](https://github.com/valeriansaliou/sonic/releases) page, use `cargo install` or pull the source code from `master`.

**👉 Install from packages:**

Sonic provides [pre-built packages](https://packagecloud.io/valeriansaliou/sonic) for Debian-based systems (Debian, Ubuntu, etc.).

**Important: Sonic only provides 64 bits packages targeting Debian 12 for now (codename: `bookworm`). You might still be able to use them on other Debian versions, as well as Ubuntu (although they rely on a specific `glibc` version that might not be available on older or newer syst

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Rust / Cargo** (manifests: Cargo.toml, Cargo.lock; scanned in UPSTREAM_CLONE)
- Top-level source layout: `client/`, `core/`, `packaging/`, `scripts/`, `server/`
- Snapshot size: **222 files**, **41005 lines of code** (measured; see Benchmarks)
- Primary languages: `.rs` (151), `.toml` (23), `.md` (15), `(none)` (11), `.sh` (8), `.yml` (5)
- Upstream commit pinned for this packaging: `f7a75d25eb07d0e16456cb0a4098496dd8674c0e`

---

## Installation

* **Full Unicode compatibility** on 80+ most spoken languages in the world. Sonic removes useless stop words from any text (eg. 'the' in English), after guessing the text language. This ensures any searched or ingested text is clean before it hits the index; [see languages](https://github.com/valeriansaliou/sonic#which-text-languages-are-supported).
* **Simple protocol (Sonic Channel)**, that let you search your index, manage data ingestion (push in the index, pop from the index, flush a collection, flush a bucket, etc.) and perform administrative actions. Sonic Channel was designed to be lightweight on resources and simple to integrate with; [read protocol specification](https://github.com/valeriansaliou/sonic/blob/master/PROTOCOL.md).
* **Easy-to-use libraries**, that let you connect to Sonic from your apps; [see libraries](https://github.com/valeriansaliou/sonic#-sonic-channel-libraries).

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

No usage section was found in the upstream readme. Entry points detected in this project directory:

```sh
cargo run --release
```

Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

* **Full Unicode compatibility** on 80+ most spoken languages in the world. Sonic removes useless stop words from any text (eg. 'the' in English), after guessing the text language. This ensures any searched or ingested text is clean before it hits the index; [see languages](https://github.com/valeriansaliou/sonic#which-text-languages-are-supported).
* **Simple protocol (Sonic Channel)**, that let you search your index, manage data ingestion (push in the index, pop from the index, flush a collection, flush a bucket, etc.) and perform administrative actions. Sonic Channel was designed to be lightweight on resources and simple to integrate with; [read protocol specification](https://github.com/valeriansaliou/sonic/blob/master/PROTOCOL.md).
* **Easy-to-use libraries**, that let you connect to Sonic from your apps; [see libraries](https://github.com/valeriansaliou/sonic#-sonic-channel-libraries).

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Rust / Cargo |
| Manifests detected | Cargo.toml, Cargo.lock |
| Files in snapshot | 222 |
| Lines of code | 41005 |
| Dependency references | 89 |
| Dependencies by ecosystem | cargo: 89 |
| Upstream license | AGPL-3.0 |
| Overlay license | Anticommons 0.1.0 |

Top dependency references recorded in the benchmark snapshot:

| Ecosystem | Name | Version | Source file |
|-----------|------|---------|-------------|
| cargo | resolver | 3 | Cargo.toml |
| cargo | license | MPL-2.0 | Cargo.toml |
| cargo | edition | 2024 | Cargo.toml |
| cargo | rust-version | 1.92.0 | Cargo.toml |
| cargo | homepage | https://github.com/valeriansaliou/sonic | Cargo.toml |
| cargo | project | https://github.com/valeriansaliou/sonic.git | Cargo.toml |
| cargo | panic | unwind | Cargo.toml |
| cargo | inherits | release | Cargo.toml |
| cargo | debug | line-tables-only | Cargo.toml |
| cargo | split-debuginfo | unpacked | Cargo.toml |
| cargo | inherits | release | Cargo.toml |
| cargo | lto | thin | Cargo.toml |
| cargo | inherits | dev | Cargo.toml |
| cargo | lto | off | Cargo.toml |
| cargo | panic | abort | Cargo.toml |
| ... | (74 more) | | |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

```bash
nano /etc/sonic.cfg
```

Finally, restart Sonic:

```bash
service sonic restart
```

**👉 Install from source:**

If you pulled the source code from Git, you can build it using `cargo`:

```bash
cargo build --locked --release
```

You can find the built binaries in the `./target/release` directory.

_Install `build-essential`, `clang`, `libclang-dev`, `libc6-dev`, `g++` and `llvm-dev` to be able to compile the required RocksDB dependency._

Note that the following optional features can be enabled upon building Sonic: `allocator-jemalloc`, `tokenizer-chinese` and `tokenizer-japanese` (some might be already enabled by default).

**👉 Install from Cargo:**

You can install Sonic directly with `cargo install`:

```bash
cargo install sonic-server
```

Ensure that your `$PATH` is properly configured to source the Crates binaries, and then run Sonic using the `sonic` command.

_Install `build-essential`, `clang`, `libclang-dev`, `libc6-dev`, `g++` and `llvm-dev` to be able to compile the required RocksDB dependency._

**👉 Install from Docker Hub:**

You might find it convenient to run Sonic via Docker. You can find the pre-built Sonic image on Docker Hub as [valeriansaliou/sonic](https://hub.docker.com/r/valeriansaliou/sonic/).

First, pull the `valeriansaliou/sonic` image:

```bash
docker pull valeriansaliou/sonic:v1.10.2
```

Then, seed it a configuration file and run it (replace `/path/to/your/sonic/config.cfg` with the path to your configuration file):

```bash
docker run -p 1491:1491 -v /path/to/your/sonic/config.cfg:/etc/sonic/config.toml -v /path/to/your/sonic/store/:/var/lib/sonic/store/ valeriansaliou/sonic:v1.4.9
```

In the configuration file, ensure that:

* `channel.inet` is set to `0.0.0.0:1491` (this lets Sonic be reached from outside the container)
* `store.kv.path` is set to `/var/lib/sonic/store/kv/` (this lets the external KV store directory be reached by Sonic)
* `store.fst.path` is set to `/var/lib/sonic/store/fst/` (this lets the external FST store directory be reached by Sonic)

Sonic will be reachable from `tcp://localhost:1491`.

**👉 Install from another source (non-official):**

Other installation sources are available:

* **Homebrew (macOS)**: `brew install sonic` ([see formula](https://formulae.brew.sh/formula/sonic))

_Note that those sources are non-official, meaning that they are not owned nor maintained by the Sonic project owners. The latest Sonic version available on those sources might be outdated, in comparison to the latest version available through the Sonic project._

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

*Excerpt from upstream `CONTRIBUTING.md`:*

# Sonic Contributing Guide

## Get Started

- First of all, fork and source this project;
- Install Rust and Cargo (to build and test Sonic);
- [Install Task](https://taskfile.dev/docs/installation) (for a better Developer Experience);

## Build Sonic

From the project root, run:

```sh
cargo build --locked
```

## Start Sonic

From the project root, run:

```sh
cargo run
```

## Run unit tests

From the project root, run:

```sh
task test
```

## Run end-to-end tests

From the project root, run:

```sh
task e2e-test
```

## Run all CI tests

```sh
task ci
```

## Update dependencies

```sh
task deps:update
```

This lints the supply chain after updating, and provides utility for easily validating changes in dependencies build scripts. **This is very important, please don’t use `cargo update` without `task deps:lint` and `task deps:validate-build-scripts`!**

## Report Issues & Request Features

**If you encounter an issue with Sonic, or would like to request a feature to be implemented, please do [open an issue](https://github.com/valeriansaliou/sonic/issues/new).**

Note that before opening an issue, you should always search for other similar issues as to avoid opening a duplicate issue. This makes the life of the project maintainer much easier.

When writing your issue title and command, make sure to be as precise as possible, giving away the maximum amount of details (even if you have a feeling some details are useless, they might make debugging or understanding easier for us).

## Submit Your Code

**If you would like to contribute directly by writing code, you should fork this project and edit it right away from your GitHub namespace.**

Once you are done with your work, run `cargo clippy --locked --no-deps` to ensure your code follows our formatting guidelines.

When this is done, you may open a Pull Request (PR), then explain your changes and their purpose precisely. We will finally accept or comment on your Pull Request, if we need more changes done on your code.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: AGPL-3.0** (evidence: `LICENSE.md` in the upstream snapshot).

License file excerpt:

```text
Mozilla Public License Version 2.0
==================================

1. Definitions
--------------

1.1. "Contributor"
    means each individual or legal entity that creates, contributes to
    the creation of, or owns Covered Software.

1.2. "Contributor Version"
    means the combination of the Contributions of others (if any) used
    by a Contributor and that particular Contributor's Contribution.

1.3. "Contribution"
    means Covered Software of a particular Contributor.

1.4. "Covered Software"
    means Source Code Form to which the initial Contributor has attached
    the notice in Exhibit A, the Executable Form of such Source Code
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original AGPL-3.0 terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `AGPL-3.0` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `SONIC` (category: SEARCH ENGINES)
- **Upstream URL:** https://github.com/valeriansaliou/sonic
- **Pinned commit (SHA):** `f7a75d25eb07d0e16456cb0a4098496dd8674c0e`
- **Branch:** master
- **Pin provenance:** resolved during the second documentation pass. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`816d776fc834e8e6c3b5aecfa6969b28eb6e6f944a564f74be863e4982b53d94`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| DANS (KNAW/NWO, Netherlands) | 10.17026/PT | EU-recognised archive |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe
and Mail, Business Insider, National Post, Financial Post, StreetInsider,
Digital Journal, Barchart, International Business Times, and Fox News.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

