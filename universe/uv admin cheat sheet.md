# Rocket UniVerse (U2) admin cheat sheet

## TOC

- [Licencing](#uvregen)

## Licencing

Install, configure, [60days...] authorise

## uvregen

Licence and configuration tool

uvregen &dash;_option [parameters [option parameters,...]]_
Run as super user

> sudo bin/uvregen &dash;s 12345678 &dash;e 11/28/2033 &dash;u 33 &dash;d 10 &dash;p AUDIT:1,PY:1,UVREP:1,CONNPL:2,EDA:1,SUBKEY:1,UVREP:1

| Option | Params | Description |
|-|-|-|
| &dash;A | auth_code | Sets  _Authorisation code_, provided by vendor, for the installation licence |
| &dash;c | | Displays the current configuration (same as CONFIG/ANALYZE.SHM -c from TCL or smat/analyze.shm -c from the DOS/UNIX shell) |
| &dash;C | | Displays the licencing _configuration_ code &mdash; Must be the only option in the command line |
| &dash;d | integer | Sets _device licensing_ number of connections per user [default: 10] |
| &dash;e | mm/dd/yyyy | Sets expiry date of the licence (NB. US (Un-Sortable) date format) [default: 1/1/2500] |
| &dash;h | | Displays usage help message |
| &dash;k | | Resets master encryption key [tbc] the MAXKEYSIZE value to 255 |
| &dash;m | params | Sets the master encryption key. Known admissable params: |
| | | SYSTEM &mdash; use system default master key |
| | | SYSGEN &mdash; use machine-specific random master key|
| | | PROMPT &mdash; let uvregen prompt for master key. PROMPT will accept the other options in a no-echo field |
| | | _text_ &mdash; use _text_ as master key (text starting with @ specifies a file containing the master key |
| | | &dash;P _password_ &mdash; Set master key password |
| | | &dash;O _password_ &mdash; Change master key password <br> &emsp;&emsp; _&dash;P or &dash;O can be specified up to 2 times<br>&emsp;&emsp; @text specifies a file containing the password<br>&emsp;&emsp; When changing the master key passwords, use -m CURRENT_ [tbc literal?] |
| | | &dash;M _key_ &mdash; specify current UniVerse master key |
| | | &dash;f &mdash; do not display warning message or prompt for input |
| | | &dash;o _file_ &mdash; store SYSGEN generated key in file _file_ [tbc UV or OS file] |
| &dash;p | code:_value_[,code:_value_,...] | Set licence package code and value &mdash; Format: UVNET:200,CONNPL:10,… Known package codes: |
| | | CONNPL &mdash; Connection pooling seats (CONNPLEP) [_integer_] |
| | | AUDIT &mdash; Audit logging [_enable/disable 1/0_] |
| | | EDA &mdash; External data access [_enable/disable 1/0_] |
| | | PY &mdash; Python package [_enable/disable 1/0_] |
| | | ~~ SBXA &mdash; SB/XA licences (n/a) ~~ |
| | | SUBKEY &mdash; Device licencing connections multi-tier [_enable/disable 1/0_] |
| | | UVNET  &mdash; UVNet [_enable/disable 1/0_] |
| | | UVREP &mdash; Replication [_enable/disable 1/0_] |
| | | UVRFS &mdash; Remote file system [_enable/disable 1/0_] |
| &dash;s | _serial_number_ | Sets install licence _serial_number_ [without -UV suffix] |
| &dash;t | | Displays the tunable values in shared memory (same as CONFIG/ANALYZE.SHM -t from TCL or smat/analyze.shm -t from the DOS/UNIX shell) |
| &dash;T | _fr_path to_path [&dash;E err_file]_ | Move master encryption key _from_path_ &mdash;> _to_path_, &dash;E output error messages to _err_file_path_ [from/to_path = old/new_uvhome] |
| &dash;u | _int_ | Sets the number of user database seats |
| &dash;z | | Displays the UniVerse licence information |

\* _deprecated options, no longer supported:_ &ndash;i, &ndash;I, &ndash;r, &ndash;x

## Using the license tool uvlictool

Use uvlictool to report on the current state of UniVerse licensing and to clean up current licensing. You must be a UniVerse Administrator to use uvlictool.

> Note: Starting at UniVerse 11.3.1, the IPv6 protocol is supported. IPv6 compatibility provides the ability to create more IP addresses, as IPv4 addresses are running out. In addition, IPv6 utilizes a more secure data package. However, UniVerse device licensing is not supported on IPv6 protocols at this time. If you are connected using an IPv6-only client, the uvlictool command displays 127.0.0.1 (localhost) as the IP address.

The **uvlictool** also does the following:

- Lists a report on license use at both the UniVerse and the package level.
- Identifies the process that owns the license, and lists package licenses it holds.
- Identifies the remote device holding the license. Applies to UniVerse 11.2.2 or earlier.
- On UNIX systems, uvlictool clean_lic -a cleans up the current licenses based on shared memory segments associated with dead processes. With this option, uvlictool scans the license table and releases any license associated with a pid that is not a valid UniVerse process. Applies to UniVerse 11.2.2 or earlier and 11.3.1 or later.
- On Windows platforms, uvlictool clean_lic -a cleans up the current licenses based on dead entries in the process table. With this option, uvlictool scans the license table and releases any license associated with a pid that is not a valid UniVerse process. Applies to UniVerse 11.2.2 or earlier and 11.3.1 or later.
- Recomputes license counts at the UniVerse, package, and seat levels. Applies to UniVerse 11.2.2 or earlier.

### Syntax

> uvlictool [check_acctlic] [list_acctlic] [ reload_acctlic] [report_lic [logical_account_name]] [clean_lic [-a]]

| Parameter | Description |
|-|-|
| check_acctlic | Checks the syntax of the $UVHOME/acct_licn.def file and reports any errors found.
| list_acctlic | Lists the current loaded account-based license and its usage.
| reload_acctlic | Reloads the $UVHOME/acct_licn.def file so that new definitions are applied.
| report_lic | Lists the current licensing state. Beginning at UniVerse 11.2.3, the report_lic parameter has been augmented with logical_account_name option. If the logical_account_name is specified, only the users in the specified logical group will be listed. |
| clean_lic | Cleans up the current licensing state. With this option, uvlictool scans the license table and releases any license associated with a pid that is not a valid UniVerse process. <br> `Note: This option was disabled at version 11.2.2, but is re-enabled starting at version 11.3.1. The uvcleanupd daemon performs the same function as the clean_lic option of uvlictool when it runs on its regularly scheduled interval.` |
| -a | Recomputes license counts at the UniVerse, package, and seat level. <br> `Note: This option was disabled at version 11.2.2, but is re-enabled starting at version 11.3.1. The uvcleanupd daemon performs the same function as the clean_lic option of uvlictool when it runs on its regularly scheduled interval.` |
