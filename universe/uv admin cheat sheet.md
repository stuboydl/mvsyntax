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
| &dash;C | | Displays the licencing _configuration_ code – Must be the only option in the command line |
| &dash;d | integer | Sets _device licensing_ number of connections per user [default: 10] |
| &dash;e | mm/dd/yyyy | Sets expiry date of the licence (NB. US (Un-Sortable) date format) [default: 1/1/2500] |
| &dash;h | | Displays usage help message |
| &dash;k | | Resets master encryption key [tbc] the MAXKEYSIZE value to 255 |
| &dash;m | params | Sets the master encryption key. Known admissable params: |
| | | SYSTEM &mdash; use system default master key |
| | | SYSGEN &mdash; use machine-specific random master key|
| | | PROMPT &mdash; let uvregen prompt for master key - PROMPT will accept the other options in a no-echo field |
| | | _text_ &mdash; use _text_ as master key (text starting with @ specifies a file containing the master key |
| | | &dash;P _password_ &mdash; Set master key password |
| | | &dash;O _password_ &mdash; Change master key password <br> &emsp;&emsp; _&dash;P or &dash;O can be specified up to 2 times<br>&emsp;&emsp; @text specifies a file containing the password<br>&emsp;&emsp; When changing the master key passwords, use -m CURRENT_ [tbc literal?] |
| | | &dash;M _key_ &mdash; specify current UniVerse master key |
| | | &dash;f &mdash; do not display warning message or prompt for input |
| | | &dash;o _file_ &mdash; store SYSGEN generated key in file _file_ [tbc UV or OS file] |
| &dash;p | code:_int_[,code:_int_,...] | Sets the licence package code and user count – Format: UVNET:200,CONNPL:10,… Known package codes: |
| | | CONNPL &mdash; Connection pooling seats (CONNPLEP) |
| | | AUDIT &mdash; Audit logging [enable/disable 1/0] |
| | | EDA &mdash; External data access [enable/disable 1/0] |
| | | PY &mdash; Python package [enable/disable 1/0] |
| | | ~~ SBXA &mdash; SB/XA licences (n/a) ~~ |
| | | SUBKEY &mdash; sub key package [enable/disable 1/0] |
| | | UVNET  &mdash; UVNet [enable/disable 1/0] |
| | | UVREP &mdash; Replication [enable/disable 1/0] |
| | | UVRFS &mdash; Remote file system [enable/disable 1/0] |
| &dash;s | _serial_number_ | Sets install licence _serial_number_ [without -UV suffix] |
| &dash;t | | Displays the tunable values in shared memory (same as CONFIG/ANALYZE.SHM -t from TCL or smat/analyze.shm -t from the DOS/UNIX shell) |
| &dash;T | _fr_path to_path [&dash;E err_file]_ | Move master encryption key _from_path_ &mdash;> _to_path_, &dash;E output error messages to _err_file_path_ [from/to_path = old/new_uvhome] |
| &dash;u | _int_ | Sets the number of user database seats |
| &dash;z | | Displays the UniVerse licence information |

\* _deprecated options, no longer supported:_ &ndash;i, &ndash;I, &ndash;r, &ndash;x
