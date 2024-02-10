# Satoshe Core
This is official repository for **Satoshe Network [SOSHE]**, featuring source code for our **Litecoin** (LTC) fork, wallet software, and builds. This repository serves as a hub for developers and users to access the core components necessary to interact with the Satoshe Network ecosystem. 

## What is Satoshe [SOSHE]?
**SOSHE** - is an innovative coin developed by enterprising young girls seeking to conquer the crypto-world. This coin transforms the usual concept of a decentralized network into a charitable and accessible platform open to anyone interested in mining, investing and using cryptocurrencies.

**SOSHE** is not just a cryptocurrency, but also a powerful tool for emancipation and women’s interaction with technology on a much deeper level. It demonstrates that cryptocurrency is not only a men’s space and that a successful future in this field is possible for everyone, regardless of gender.

## Blockchain Specification:

- **Network Name**: `SATOSHE Network`
- **Coin Ticker**: `SOSHE`
- **Consensus Mechanism**: `PoW + PoS`
- **Hashing Algorithm**: `Scrypt`
- **Block Time**: `1 min.`
- **PoW Block Reward**: `10`
- **PoS Block Reward**: `4`
- **Total Supply**: `30,000,000 PoW + Unlimited PoS`

## Quick Start

Select the section you need, using the menu below, for quick access to the documentation you need. 

- [Linux node + wallet installation](/install-node-linux.md)
- [Windows wallet installation](install-wallet-windows.md)
- [Linux compiling](/compile-source-linux.md)
- [Windows compiling](/compile-source-windows.md)

## Information

- Website - https://shesatoshi.org/
- Roadmap - https://shesatoshi.org/roadmap
- Whitepaper - https://shesatoshi.org/whitepaper
- Official GitHub - https://github.com/SatosheNetwork

## Social Media

- Official Twitter - https://x.com/SATOSHEcoin?s=20
- Official Discord - https://discord.com/invite/SBez3DxgUa

## Bounty Programs

Satoshe network cannot at this time commit to bounty payments ahead of time. However, we will use our best judgement and do intend on rewarding those who provide valuable disclosures (with a strong emphasis on easy to read and reproduce disclosures).
In addition to personal funding, there are 10% of PoS block reward allocated for this goal.

## License
Satoshe is released under the terms of the MIT license. See [MIT-LICENSE](/MIT-LICENSE) for more information or see http://opensource.org/licenses/MIT.

Development Process
-------------------

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/SatosheNetwork/tags) are created
regularly to indicate new official, stable release versions of SATOSHE.

Change log can be found in [CHANGELOG.md](CHANGELOG.md).

The contribution workflow is described in [CONTRIBUTING.md](CONTRIBUTING.md).


Testing
-------

Testing and code review might be the bottleneck for development. Please help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write [unit tests](/doc/unit-tests.md) for new code, and to
submit new unit tests for old code. Unit tests can be compiled and run
(assuming they weren't disabled in configure) with: `make check`

There are also [regression and integration tests](/qa) of the RPC interface, written
in Python, that are run automatically on the build server.
These tests can be run (if the [test dependencies](/qa) are installed) with: `qa/pull-tester/rpc-tests.py`

The Travis CI system makes sure that every pull request is built for Windows, Linux, and OS X, and that unit/sanity tests are run automatically.

### Manual Quality Assurance (QA) Testing

Changes should be tested by somebody other than the developer who wrote the
code. This is especially important for large or high-risk changes. It is useful
to add a test plan to the pull request description if testing the changes is
not straightforward.
