# Alfred 2 DNS control workflow

Manage the [discoveryd](http://www.manpagez.com/man/8/discoveryd/) process Mac OS X (10.10+) using [discoveryutil](http://www.manpagez.com/man/8/discoveryutil/).

## Usage

The `discoveryutil` utility requires administrator privileges for everything it does. No arguments to the keyword will prompt you for a user and password.

For convenience, you can also enter your password after the keyword (separated by a space). The workflow does not store or submit password data. If the password is incorrect, you will be prompted anyway.

Success or failure is reported through a notification.

![](https://raw.github.com/deekayen/dnscontrol/alfred2/screenshots/workflow.jpg)

### Keyword: `dns flush`

Flushing DNS is the only keyword that works for OS X 10.7+. It will flush entries for both multicast and unicast DNS.

![](https://raw.github.com/deekayen/dnscontrol/alfred2/screenshots/dns.jpg)

#### <=10.9

Command used (see [Apple Support](http://support.apple.com/kb/HT5343)): `sudo killall -HUP mDNSResponder`

#### >=10.10

`sudo discoveryutil udnsflushcaches`

### Keyword: `dns restart`

Forces mdns and udns questions and mdns registrations to restart.

#### Command

`discoveryutil mdnsrestartquestions;discoveryutil udnsrestartquestions;discoveryutil mdnsrestartregistrations;`

### Unicast DNS

![](https://raw.github.com/deekayen/dnscontrol/alfred2/screenshots/udns.jpg)

#### Keyword: `udns flush`

Flushes only the Unicast DNS cache.

#### Keyword: `udns stats`

Displays cache statistics for Unicast DNS.

##### Command

`discoveryutil udnscachestats  | grep 'UDNS Cache Stats: Cached' | head -1`

![](https://raw.github.com/deekayen/dnscontrol/alfred2/screenshots/udns_stats.jpg)

#### Keyword: `udns tcp`

Force udns queries to go over TCP instead of UDP.

##### Command

`discoveryutil udnsforcetcp yes`

#### Keyword: `udns udp`

Allow udns queries to go over UDP (reversing `udns tcp`).

##### Command

`discoveryutil udnsforcetcp no`

### Multicast DNS

![](https://raw.github.com/deekayen/dnscontrol/alfred2/screenshots/mdns.jpg)

#### Keyword: `mdns flush`

Flushes only the Multicast DNS cache

#### Keyword: `mdns stats`

Displays cache statistics for Multicast DNS.

##### Command

`discoveryutil mdnscachestats`
