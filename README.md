smol - tokio


### smol

`Listening on http://127.0.0.1:8000`

```
cargo run --bin hello-smol --release
```

### tokio

`Listening on http://127.0.0.1:8001`

```
cargo run --bin hello-tokio --release
```

### benchmark

```
npm i autocannon -g
```

### smol
```
λ autocannon 127.0.0.1:8000
Running 10s test @ http://127.0.0.1:8000
10 connections

┌─────────┬──────┬──────┬───────┬──────┬─────────┬─────────┬─────────┐
│ Stat    │ 2.5% │ 50%  │ 97.5% │ 99%  │ Avg     │ Stdev   │ Max     │
├─────────┼──────┼──────┼───────┼──────┼─────────┼─────────┼─────────┤
│ Latency │ 0 ms │ 0 ms │ 0 ms  │ 0 ms │ 0.01 ms │ 0.05 ms │ 6.16 ms │
└─────────┴──────┴──────┴───────┴──────┴─────────┴─────────┴─────────┘
┌───────────┬────────┬────────┬─────────┬─────────┬──────────┬─────────┬────────┐
│ Stat      │ 1%     │ 2.5%   │ 50%     │ 97.5%   │ Avg      │ Stdev   │ Min    │
├───────────┼────────┼────────┼─────────┼─────────┼──────────┼─────────┼────────┤
│ Req/Sec   │ 53375  │ 53375  │ 70783   │ 71807   │ 67300.37 │ 6302.33 │ 53359  │
├───────────┼────────┼────────┼─────────┼─────────┼──────────┼─────────┼────────┤
│ Bytes/Sec │ 4.7 MB │ 4.7 MB │ 6.23 MB │ 6.32 MB │ 5.92 MB  │ 554 kB  │ 4.7 MB │
└───────────┴────────┴────────┴─────────┴─────────┴──────────┴─────────┴────────┘

Req/Bytes counts sampled once per second.

740k requests in 11.04s, 65.1 MB read
```

```
λ autocannon 127.0.0.1:8000
Running 10s test @ http://127.0.0.1:8000
10 connections

┌─────────┬──────┬──────┬───────┬──────┬─────────┬─────────┬─────────┐
│ Stat    │ 2.5% │ 50%  │ 97.5% │ 99%  │ Avg     │ Stdev   │ Max     │
├─────────┼──────┼──────┼───────┼──────┼─────────┼─────────┼─────────┤
│ Latency │ 0 ms │ 0 ms │ 0 ms  │ 0 ms │ 0.01 ms │ 0.04 ms │ 5.95 ms │
└─────────┴──────┴──────┴───────┴──────┴─────────┴─────────┴─────────┘
┌───────────┬─────────┬─────────┬─────────┬─────────┬──────────┬─────────┬─────────┐
│ Stat      │ 1%      │ 2.5%    │ 50%     │ 97.5%   │ Avg      │ Stdev   │ Min     │
├───────────┼─────────┼─────────┼─────────┼─────────┼──────────┼─────────┼─────────┤
│ Req/Sec   │ 53343   │ 53343   │ 71679   │ 72703   │ 68552.73 │ 6051.85 │ 53330   │
├───────────┼─────────┼─────────┼─────────┼─────────┼──────────┼─────────┼─────────┤
│ Bytes/Sec │ 4.69 MB │ 4.69 MB │ 6.31 MB │ 6.39 MB │ 6.03 MB  │ 533 kB  │ 4.69 MB │
└───────────┴─────────┴─────────┴─────────┴─────────┴──────────┴─────────┴─────────┘

Req/Bytes counts sampled once per second.

754k requests in 11.04s, 66.4 MB read
```

#### tokio

```
λ autocannon 127.0.0.1:8001
Running 10s test @ http://127.0.0.1:8001
10 connections

┌─────────┬──────┬──────┬───────┬──────┬─────────┬─────────┬─────────┐
│ Stat    │ 2.5% │ 50%  │ 97.5% │ 99%  │ Avg     │ Stdev   │ Max     │
├─────────┼──────┼──────┼───────┼──────┼─────────┼─────────┼─────────┤
│ Latency │ 0 ms │ 0 ms │ 0 ms  │ 0 ms │ 0.01 ms │ 0.05 ms │ 7.86 ms │
└─────────┴──────┴──────┴───────┴──────┴─────────┴─────────┴─────────┘
┌───────────┬─────────┬─────────┬─────────┬─────────┬──────────┬─────────┬─────────┐
│ Stat      │ 1%      │ 2.5%    │ 50%     │ 97.5%   │ Avg      │ Stdev   │ Min     │
├───────────┼─────────┼─────────┼─────────┼─────────┼──────────┼─────────┼─────────┤
│ Req/Sec   │ 66495   │ 66495   │ 73343   │ 74175   │ 71787.64 │ 2875.78 │ 66495   │
├───────────┼─────────┼─────────┼─────────┼─────────┼──────────┼─────────┼─────────┤
│ Bytes/Sec │ 5.85 MB │ 5.85 MB │ 6.46 MB │ 6.53 MB │ 6.32 MB  │ 253 kB  │ 5.85 MB │
└───────────┴─────────┴─────────┴─────────┴─────────┴──────────┴─────────┴─────────┘

Req/Bytes counts sampled once per second.

790k requests in 11.05s, 69.5 MB read
```

```
λ autocannon 127.0.0.1:8001
Running 10s test @ http://127.0.0.1:8001
10 connections

┌─────────┬──────┬──────┬───────┬──────┬─────────┬─────────┬─────────┐
│ Stat    │ 2.5% │ 50%  │ 97.5% │ 99%  │ Avg     │ Stdev   │ Max     │
├─────────┼──────┼──────┼───────┼──────┼─────────┼─────────┼─────────┤
│ Latency │ 0 ms │ 0 ms │ 0 ms  │ 0 ms │ 0.01 ms │ 0.04 ms │ 6.19 ms │
└─────────┴──────┴──────┴───────┴──────┴─────────┴─────────┴─────────┘
┌───────────┬─────────┬─────────┬─────────┬────────┬──────────┬────────┬─────────┐
│ Stat      │ 1%      │ 2.5%    │ 50%     │ 97.5%  │ Avg      │ Stdev  │ Min     │
├───────────┼─────────┼─────────┼─────────┼────────┼──────────┼────────┼─────────┤
│ Req/Sec   │ 65279   │ 65279   │ 73279   │ 73919  │ 72452.37 │ 2332.8 │ 65276   │
├───────────┼─────────┼─────────┼─────────┼────────┼──────────┼────────┼─────────┤
│ Bytes/Sec │ 5.75 MB │ 5.75 MB │ 6.45 MB │ 6.5 MB │ 6.38 MB  │ 205 kB │ 5.74 MB │
└───────────┴─────────┴─────────┴─────────┴────────┴──────────┴────────┴─────────┘

Req/Bytes counts sampled once per second.

797k requests in 11.04s, 70.1 MB read
```
