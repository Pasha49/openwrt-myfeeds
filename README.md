# openwrt-myfeeds

If you've downloaded and setup a openwrt buildsystem. Add src-git myfeeds https://github.com/kiwina/openwrt-myfeeds.git to the feeds.conf.default. Do a `scripts/feeds update myfeeds` en then `scripts/feeds install jq` if you want to install jq. Then, when you do a `make menuconfig`, jq can be found in the utilities.
