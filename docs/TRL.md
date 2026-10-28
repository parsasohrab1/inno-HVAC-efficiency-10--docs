# TRL assessment (evidence-based)

**Level reached: TRL 4 for the individual components, on a SYNTHETIC single-zone model only.** TRL 5 is not claimed.

`pytest` (CI on every push) runs 8 tests:

| Component | Module | Validated against |
|---|---|---|
| Setpoint control: comfort band, peak-hour offset (FR-07), setback after a configurable empty delay (FR-12/14), pre-start recovery | `controller.py` | rule tests; comfort 22-24 C kept while occupied before the peak window |
| Demand response with authorisation, audit log and user priority (FR-25..FR-28) | `demand_response.py` | event sequence incl. rejection without authorisation and ignoring commands under user override |
| Energy and savings accounting (FR-15, FR-19) | `savings.py` | arithmetic |
| Single-zone RC model and closed-loop day simulation | `thermal.py`, `simulate.py` | in simulation the controller uses 24 % less electricity than a fixed 23.5 C setpoint (illustrative zone parameters) |

## Findings during validation
- The first controller version used night setback **without recovery** and the room was 27.6 C at the start of occupancy (comfort violated); an optimal-start window (`recovery_lead_h`) fixed it and is covered by a test.
- In this model the controller does **not lower the peak** electric demand (both cases reach the plant capacity right after the peak window); the test only checks that it is not higher.
- The 24 % saving is a property of the toy model, not an estimate for real buildings.

## Not done (and why)
- **No real building data** (sensors, meters, BMS), so no claim about real savings (TRL 5 needs a pilot building).
- No protocol layer (MQTT/Modbus/BACnet), mobile/web apps, load forecasting for peak shifting (FR-10), storage (FR-09), multi-building control, 2FA/RBAC, or scale tests (NFR-02: 10,000 devices; NFR-01 latency).

## Next steps toward TRL 5
1. Pilot in one building: meter and sensor data for 1-2 months, a baseline period and a control period (or A/B zones).
2. Calibrate the thermal model on that data and re-estimate savings with confidence intervals.
3. Add the protocol layer and measure command latency.
