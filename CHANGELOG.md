# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/).
This project was forked from Electrum v2.7.1 thus the first release is
labeled as 2.7.1. Subsequent releases will follow
[Semantic Versioning](http://semver.org/).

## [Unreleased]
### Security
  *
  *

### Fixed
  *
  *

### Deprecated
  *
  *

### Changed
  * `getvaluesforuri` now returns the claims in the reverse order(most recent first).
  * Moved Enumation and BCDataStream classes into their own files

### Added
  * Added additional fields(support_info, update_info, claim_info) in tx history to support tipping.
  * Added `get_transaction_fee` command
  * Added `fee` field to the response for `history`
  * Added optional `include_tip_info` argument to `history`

### Removed
  * Removed label from tx history
  *


## [3.1.6] - 2017-08-22
### Fixed
 * Fix race condition in create_new_address

### Changed
 * Bumped `lbryschema` requirement to 0.0.10 [see changelog](https://github.com/lbryio/lbryschema/blob/master/CHANGELOG.md#0010---2017-08-22)

## [3.1.5] - 2017-08-04
### Fixed
 * Fix amount formatting bugs caused by extra calls to format_amount_value (https://github.com/lbryio/lbryum/issues/142)

### Changed
 * Changed uri resolution to return the `claims_in_channel` count instead of the `claims_in_channel_pages` count

### Added
 * Added `sendwithsupport` to send a tip to the owner of a claim


## [3.1.4] - 2017-07-24
### Fixed
 * Fixed getclaimbyoutpoint to return error if claim does not exist


## [3.1.3] - 2017-07-06
### Fixed
 * Fix `lbryum daemon status`


## [3.1.2] - 2017-07-06
### Fixed
 * Fix `lbryum daemon start` on windows
 * Fix `version` command


## [3.1.1] - 2017-06-28
### Changed
 * Moved `blockchain_params` into constants.py

### Removed
 * Removed networks.py


## [3.1.0] - 2017-06-27
### Changed
 * Updated packaging to no longer use imp
 * Enable pylint

### Removed
 * Removed payment requests
 * Removed x509
 * Removed old mneumonic
 * Removed old wallet and account
 * Removed rsakey.py
 * Removed ripemd.py
 * Removed dnssec.py
 * Removed wizard
 * Removed i18n
 * Removed socket and raw_input patches


## [3.0.1] - 2017-06-21
### Changed
 * have gettransaction command return deserialized JSON instead of hex


## [3.0.0] - 2017-06-21
### Changed
 * Renamed LICENCE to LICENSE

### Removed
 * Removed lbryum gui
 * Removed plugins
 * Remove unused files and directories

### Fixed
 * set_default_subparser to `cmd` after https://github.com/lbryio/lbryum/pull/111


## [2.8.3] - 2017-06-15
### Added
 * added waitfortxinwallet command

### Changed
 * Change 'nothing to resolve' error to 'claim not found' used in other places
 * Move uri resolution logic to lbryum-server, validate response
 * Support batched uri resolution

### Fixed
 * Fixed abandon command
 * Fix `updateclaimsignature`
 * Fix changelog updates and release messages


## [2.7.22] - 2017-05-11
### Added
  * setup.py will install lbryum as a script
  * added functions for lbrynet in commands.py
  * add channel related commands:
    - `getclaimbynameinchannel`
    - `getdefaultcertificate`
    - `getvalueforuri`
    - `getsignaturebyid`
    - `getclaimbyoutpoint`
    - `getclaimssignedby`
    - `getclaimsinchannel`
    - `getclaimbyid`
    - `getnthclaimforname`
    - `getcertificateclaims`
    - `claimcertificate`
    - `updateclaimsignature`
    - `updatecertificate`
    - `cansignwithcertificate`
  * add `sendclaimtoaddress` command
      
### Changed
  * include claim address in return from getvalueforname
  * change `abandon` to take `claim_id` instead of `txid` and `nout`
  * change default `amount` in update to None, if `amount` is none use the existing claim amount
  * change `update` to determine (and not require) `claim_id`, `txid`, and `nout` from a given `name`
  * change `claim` to not make a second first-claim if a claim for the name already exists in the wallet unless specified
  * add `claim_sequence` and `claim_address` to claim responses
  * by default expect a hex encoded `val` for `claim` and `update`
  * automatically handle claim signing using default certificate (if one has been made) via `claim` and `update` commands
  * add `channel_name' to claim responses for signed claims
  
### Fixed
  * fix return amounts for claim list commands
  * return supports list for claim queries
  * fix bug verifying the claim value for a new certificate claim
  * fixed update command
  * fix bugs related to get_name_claims() returning supports
  * fix claim id double-encoding bug in `update`
  * fix switching between lbrycrd_main, lbrycrd_regtest, and lbrycrd_testnet in config

## [2.7.12] - 2017-03-10
### Changed
 * Make key names in dictionary outputs more consistent
 

## [2.7.8] - 2017-02-27
### Fixed
 * Make requests for individual headers after requesting chunks
 

## [2.7.6] - 2017-02-21
### Changed
 * Improve packaging of data files to support building with pyinstaller
 

## [2.7.5] - 2017-02-15
### Fixed
 * Fixed user's supports and updates being spendable by other transactions
