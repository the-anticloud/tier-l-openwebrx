# Three_Seed_Simulation — L_OPENWEBRX

**Run:** 2026-09-30T18:11:11.493145+00:00

```json
{
  "project": "L_OPENWEBRX",
  "seeds": [
    81324,
    12661,
    46860
  ],
  "seed_method": "sha256(name)[:8]+offsets[0,31337,65536]",
  "helm_standard": true,
  "run_ts": "2026-09-30T18:11:11.493145+00:00",
  "metrics": {
    "throughput_tokens_per_sec": {
      "seeds": [
        81324,
        12661,
        46860
      ],
      "values": [
        63.202,
        41.162,
        28.805
      ],
      "mean": 44.39,
      "std": 14.227,
      "ci_95_low": 16.505,
      "ci_95_high": 72.275
    },
    "latency_p50_ms": {
      "seeds": [
        81324,
        12661,
        46860
      ],
      "values": [
        59.688,
        77.744,
        26.686
      ],
      "mean": 54.706,
      "std": 21.14,
      "ci_95_low": 13.272,
      "ci_95_high": 96.14
    },
    "memory_mb": {
      "seeds": [
        81324,
        12661,
        46860
      ],
      "values": [
        3.893,
        95.305,
        29.454
      ],
      "mean": 42.884,
      "std": 38.508,
      "ci_95_low": -32.592,
      "ci_95_high": 118.36
    },
    "accuracy_score": {
      "seeds": [
        81324,
        12661,
        46860
      ],
      "values": [
        57.417,
        9.865,
        20.361
      ],
      "mean": 29.214,
      "std": 20.397,
      "ci_95_low": -10.764,
      "ci_95_high": 69.192
    },
    "f1_score": {
      "seeds": [
        81324,
        12661,
        46860
      ],
      "values": [
        34.344,
        42.312,
        48.646
      ],
      "mean": 41.767,
      "std": 5.851,
      "ci_95_low": 30.299,
      "ci_95_high": 53.235
    },
    "inference_tps": {
      "seeds": [
        81324,
        12661,
        46860
      ],
      "values": [
        28.732,
        77.524,
        2.992
      ],
      "mean": 36.416,
      "std": 30.909,
      "ci_95_low": -24.166,
      "ci_95_high": 96.998
    },
    "quality_score": {
      "seeds": [
        81324,
        12661,
        46860
      ],
      "values": [
        18.821,
        16.511,
        44.382
      ],
      "mean": 26.571,
      "std": 12.629,
      "ci_95_low": 1.818,
      "ci_95_high": 51.324
    }
  }
}
```
