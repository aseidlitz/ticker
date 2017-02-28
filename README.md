Crypto Liquidity Integrator
===========================

Origins
-------

https://t.me/alkotrading

Features
--------

* L3 Order Book persistence
* Realtime WebSocket Connections
* Stream Recording and Replaying
* BitMEX, OKCoin, GDAX and other venues
* Reconnecting on stream failures
* Fast ETS storage as matching engine
* 150 LOC

Launch
------

```
$ brew install erlang
$ git clone git://github.com/spawnproc/ticker && cd ticker
$ ./mad dep com pla && ./mad rep
```

Text Log
--------

```
$ tail priv/gdax/order/2017-2-28/BTC-USD
10:40:60.772 -1094 0
10:40:60.791 -1094 0
10:40:60.808 -745 0
10:40:60.814 -745 0
10:40:60.828 -745 0
10:40:60.846 -745 0
10:40:60.850 -184 0
10:40:60.871 +762 1207.95 0.01
10:40:60.884 -1075 0
10:40:60.931 +176 1207.96 0.01
```

Commands
--------

## Obtain Supported Instruments

```
> book:instruments().
[btc_usd,btc_eur,btc_gpb,eth_btc,eth_usd]
```

## Book Print

```
> book:print(eth_usd).
  Id Price Size
---- ----- ----------
   7 15.15 -235.08011
  28 15.03 -90.77931
  18  15.0 -1.0
  25 14.98 -50.09
  26 14.97 -445.21
  27 14.96 -201.47
  19 14.94 -54.09
   4 14.92 -300.894
  22 14.86 -1.00641
  14 14.82 434.71422
  16 14.79 325.01467
   1 14.78 305.32
  17 14.77 711.95
   5 14.76 378.72
   6 14.75 318.78
   8 14.74 260.41
  11 14.62 451.0586
Depth: 17
Total: 1806.34766
ok
```

## Enable Console Log

```
> application:set_env(trade,log,show).
ok
>
bitmex:"XBTUSD":"Buy":10:55:23.433 -1130 0
bitmex:"XBTUSD":"Buy":10:55:23.438 +1045 1202.4 4000.0
gdax:"BTC-GBP":"buy":10:55:23.462 +291 960.71 0.09992562
bitmex:"XBTUSD":"Buy":10:55:23.470 -1045 0
bitmex:"XBTUSD":"Buy":10:55:23.474 +712 1201.9 1000.0
```

## Orders Table

```
> kvs:all(order).
[{order,"4fb397c0-2e45-4d98-8f76-06399e9f9cf5",30,eth_btc},
 {order,"f8a81058-06bd-435c-b1cb-9ac8464af9ce",260,btc_eur},
 {order,"71ffcb78-f036-467c-b1ea-12c0e3d98a99",326,btc_eur},
 {order,"ad325868-23cd-4177-bfba-ed06a11ab707",216,btc_gpb},
 {order,"f991aa88-1278-4464-8992-b958eb1e977b",139,btc_gpb},
 {order,"830e9767-6182-42a6-b320-424f1e9211ca",312,btc_eur},
 {order,[...],...},
 {order,...},
 {...}|...]
```

Credits
-------

* Maxim Sokhatsky
* Alexander Temerev

OM A HUM
