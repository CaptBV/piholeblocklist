# piholeblocklist

This is a Pi-hole blocklist.
<br> It is derived from this [blocklist](https://codeberg.org/spootle/blocklist/raw/branch/master/blocklist.txt). All credits to [spootle](https://codeberg.org/spootle).

spootle's blocklist contains 3 invalid domains.
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
This list merely removes the 3 invalid domains.
<br>
Method:
<br>
```wget -q -O- https://codeberg.org/spootle/blocklist/raw/branch/master/blocklist.txt |grep -v \< > blocklist-valid-domains```
