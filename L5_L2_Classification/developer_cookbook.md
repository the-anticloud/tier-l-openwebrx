# Developer Cookbook — L_OPENWEBRX
**Stack:** Python 3.11, openwebrx+ 1.x, RTL-SDR/HackRF, PAX 27B, AIOSS_FORMAT
**Domain:** OpenWebRX: web-based SDR receiver for Anticloud RF spectrum monitoring

## Start spectrum monitor
```python
from l_openwebrx import OpenWebRXMonitor

monitor = OpenWebRXMonitor(
    sdr_device="rtlsdr",
    center_freq_hz=433_920_000,
    sample_rate=2_400_000,
    pax_model="./pax-27b-q4.gguf",
    aioss_chain="./openwebrx.aioss"
)

monitor.start()
for event in monitor.spectrum_events():
    if event.anomaly_score > 0.75:
        print(f"Anomaly at {event.freq_hz/1e6:.3f}MHz: {event.description}")
        print(f"PAX: {monitor.pax_assess(event)}")
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
