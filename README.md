# Alfred for macOS DNS control workflow

[![license](https://img.shields.io/badge/license-MIT%20License-blue.svg)]() [![Project Status: Inactive – The project has reached a stable, usable state but is no longer being actively developed; support/maintenance will be provided as time allows.](https://www.repostatus.org/badges/latest/inactive.svg)](https://www.repostatus.org/#inactive)

Manage the [discoveryd](http://www.manpagez.com/man/8/discoveryd/) process Mac OS X 10.10 using [discoveryutil](http://www.manpagez.com/man/8/discoveryutil/).

Restart the mDNSResponder in other versions of macOS.

## Usage

Flushing the DNS cache requires administrator privileges. No arguments to the keyword will prompt you for a user and password.

For convenience, you can also enter your password after the keyword (separated by a space). The workflow does not store or submit password data. If the password is incorrect, you will be prompted anyway.

Success or failure is reported through a notification.

![](https://raw.github.com/deekayen/dnscontrol/alfred3/screenshots/workflow.png)

### Keyword: `dns flush`

Flushing DNS is the only keyword that works for OS X 10.7+. It will flush entries for both multicast and unicast DNS.

![](https://raw.github.com/deekayen/dnscontrol/alfred3/screenshots/dns.png)

#### <=10.9

Command used (see [Apple Support](http://support.apple.com/kb/HT5343)): `sudo killall -HUP mDNSResponder`

#### 10.10

`sudo discoveryutil udnsflushcaches`

#### 10.11+

`killall -HUP mDNSResponder`
