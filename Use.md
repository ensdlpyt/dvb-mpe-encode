# Introduction #

The program can be used as part of a pipe to transport IP over DVB links (e.g. satellite).

# Details #

Example use:

In one terminal:

`mpe tun0 | sec2ts 430 | DtPlay 1000000`

In another Terminal:

`ifconfig tun0 10.0.0.1/24 up`

`route add -net 224.0.0.0 netmask 224.0.0.0 tun0`

This assumes you have a Dektec DVB card. DtPlay uses large output buffers, so make sure you have a high IP bit rate if you expect this to work.

I don't and had to write another application to get my data flushed to the card often enough.