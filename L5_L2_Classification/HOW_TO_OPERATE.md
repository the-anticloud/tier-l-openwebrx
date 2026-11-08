# How to Operate — L_OPENWEBRX
**Platform:** Anticloud | **IP:** USPTO pending 2026, Anticloud FZ LLE, 0-1.gg

## Module Overview
L_OPENWEBRX — OpenWebRX: web-based SDR receiver for Anticloud RF spectrum monitoring
Stack: Python 3.11, openwebrx+ 1.x, RTL-SDR/HackRF, PAX 27B, AIOSS_FORMAT

## Daily Operations
1. `aioss verify --chain ./l_openwebrx.aioss`
2. Check service health via api-oss-monitor
3. Review api-oss-logging for error-level events
4. Confirm PAX 27B is loaded and responding

## Incident Response
- Chain tamper: halt, notify compliance, restore from backup
- GPU OOM: reduce batch size, check memory leak
- High latency >2s P99: check queue depth, scale workers
- Compliance gap: run api-oss-compliance report

## Backup (nightly)
```bash
python -m api_oss_backup backup --sources ./l_openwebrx.aioss --output ./backups/
```
