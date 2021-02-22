# piholeblocklist

This is a Pi-hole blocklist.
<br> It is derived from this [blocklist](https://codeberg.org/spootle/blocklist/raw/branch/master/blocklist.txt). All credits to [spootle](https://codeberg.org/spootle).
<br> It is derived from this [blocklist](https://download.dnscrypt.info/blocklists/domains/mybase.txt). All credits to [DNScrypt](https://dnscrypt.info).
<br> It is derived from this [blocklist](https://paulgb.github.io/BarbBlock/blacklists/domain-list.txt). All credits to [BarbBlock](https://paulgb.github.io/BarbBlock).

These blocklists contain some invalid domains. 
spootle's blocklist e.g. contains 3 invalid domains.
<br> This results in following error messages when updating Pi-hole ```pihole -g```:
<br>
```[i] Target: https://codeberg.org/spootle/blocklist/raw/branch/master/blocklist.txt
  [✓] Status: Retrieval successful
  [i] Received 113501 domains, 3 domains invalid!
      Sample of invalid domains:
      - <metaname="date"content="21.11.2020,22:47:56">
      - <metaproperty="og:site"content="gameindustry.eu">
      - [update21.11.2020,22:47:56]<br>
```
The ```blocklist-valid-domains```-file is merely a curated list that does not contain these invalid domains.
<br>
Method:
<br>
```wget -q -O- https://codeberg.org/spootle/blocklist/raw/branch/master/blocklist.txt |grep -v \< >> blocklist-valid-domains```
<br>```wget -q -O- https://download.dnscrypt.info/blocklists/domains/mybase.txt |grep -v ^*.|grep -v ^$|grep -v ^# >> blocklist-valid-domains```
<br>```wget -q -O- https://paulgb.github.io/BarbBlock/blacklists/domain-list.txt >> blocklist-valid-domains```
<br>
