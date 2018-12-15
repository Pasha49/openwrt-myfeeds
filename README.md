# openwrt-myfeeds

I'm a noob, but got to start somewhere..
This feed for openwrt contains jq. There is a patch included that strips `y0`,`y1`,`j0`,`j1` from `libm.h`. That means no bessel functions (i don't think i'll miss it).

If you've downloaded and setup a openwrt buildsystem. Add src-git myfeeds https://github.com/profOnno/openwrt-myfeeds.git to the feeds.conf.default. Do a `scripts/feeds update myfeeds` en then `scripts/feeds install jq` if you want to install jq. Then, when you do a `make menuconfig`, jq can be found in the utilities.
