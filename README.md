<div align="center">
  <a href="https://wizardsardine.com/liana" target="_blank">
    <img src="gui/ui/static/logos/liana-app-icon.svg" width="140px" />
  </a>

# Liana

*The missing safety net for your bitcoins*.

</div>


## About

Liana is a simple Bitcoin wallet. Simular to other Bitcoin wallets, you have a primary private key which can spend bitcoin from the wallet immediately. Additionally, unlike other wallets, Liana lets you specify additional recovery keys which can only transact after the wallet has been inactive for some time.

The primary key is associated with the primary spending path (always accessible). The recovery keys use conditional spending paths that are only available after a period of time (UTC/Blockheight) has elapsed. You may use more than one key in either the primary or recovery paths (multisig). You may also have more than one recovery path.

Here is an example of a Liana wallet configuration:
- Owner's key (can always spend)
- Any 2 keys from the owner's spouse and two kids (after 1 year)
- A third party, in case [all else failed](https://wizardsardine.com/liana/plans#section-safety-net)
  (after 1 year and 3 months)

The lockup period is enforced onchain by the Bitcoin Protocol. This is achieved by leveraging
timelock capabilities of Bitcoin smart contracts (Script).

Liana can be used for **trustless inheritance**, **loss protection** or **safer backups**. Visit
[our website](https://wizardsardine.com/liana) for more information.


## Usage

Liana is available on Windows, Mac and Linux. To install and start using it see
[`doc/USAGE.md`](doc/USAGE.md). A more accessible version of Liana is also available as a web
application [here](https://lianalite.com/).

If you just want to quickly try out Liana on Bitcoin Signet, see [`doc/TRY.md`](doc/TRY.md).


## Hacking on Liana

Liana is an open source project. It is [hosted at Github](https://github.com/wizardsardine/liana).
Contributions are very welcome. See [here](CONTRIBUTING.md) for guidelines. Most regular
contributors hang out on [our Discord](https://discord.gg/9rAqZHwkv6). Join us there if you have any
question about contributing.

Liana is separated in two main components: the daemon and the Graphical User Interface.

#### Liana daemon

The daemon contains the core logic of the wallet. It is both a library (a Rust crate) that exposes a
command interface and a standalone UNIX daemon that exposes a JSONRPC API through a Unix Domain
Socket.

The code for the daemon can be found in the [`src/`](src/) folder at the root of this repository.

#### Liana GUI

The GUI contains both an installer that guides a user through setting up a Liana wallet, as well as
a graphical interface to the daemon using the [`iced`](https://github.com/iced-rs/iced/) library.

The code for the GUI can be found in the [`gui/src/`](gui/src) folder.


## Security

See [`SECURITY.md`](SECURITY.md) for details about reporting a security vulnerability or any bug
that could potentially impact the security of users' funds.


## License

Released under the BSD 3-Clause Licence. See the [LICENCE](LICENCE) file.
