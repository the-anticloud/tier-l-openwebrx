# Deploy Guide — L_OPENWEBRX
**Tier:** TIER_8_RF_MESH_DEFENSE | **Stack:** Python 3.11, openwebrx+ 1.x, RTL-SDR/HackRF, PAX 27B, AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, openwebrx+ 1.x, RTL-SDR or HackRF dongle. Passive receive only.

## Environment
RTL-SDR (RTL2832U) or HackRF. Antenna. 4GB RAM. Passive receive only — no transmit license needed.

## AIOSS Integration
```bash
aioss init --module L_OPENWEBRX --output ./l_openwebrx.aioss
aioss append --chain ./l_openwebrx.aioss --payload ./output.bin --module L_OPENWEBRX
aioss verify --chain ./l_openwebrx.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="L_OPENWEBRX",
    aioss_chain="./L_OPENWEBRX.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./L_OPENWEBRX.aioss --verbose
python -m L_OPENWEBRX.tests.smoke
```
