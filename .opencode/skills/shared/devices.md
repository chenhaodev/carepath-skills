# Approved Monitoring Devices

This reference catalogues approved remote patient monitoring devices used across Carepath care pathways. All devices transmit data to the care coordination platform for clinical review.

## Device Catalog by Category

### Continuous Telemetry Devices

#### VitalConnect VitalPatch
- **Manufacturer**: VitalConnect
- **Measurements**: Continuous HR, RR, skin temperature, ECG, activity, fall detection
- **Connectivity**: Wireless Bluetooth to smartphone/tablet
- **Used in Pathways**: 
  - CHF Acute* (optional)
  - Hypertension Acute* (optional)
  - Diabetes Acute* (optional)
  - DVT Acute* (optional)
- **Notes**: Wearable adhesive patch, 7-day battery life

#### Everion Armband (Biovotion)
- **Manufacturer**: Biovotion (Everion)
- **Measurements**: Continuous HR, RR, SpO2, skin temperature, activity levels
- **Connectivity**: Wireless to smartphone app
- **Used in Pathways**:
  - COPD Acute* (optional, can substitute pulse oximeter)
  - Pneumonia Acute* (optional)
  - COVID-19 Acute* (optional)
  - COPD Post-Acute (required)
  - Pneumonia Post-Acute (required)
  - COVID-19 Post-Acute (required)
- **Notes**: Rechargeable armband worn on upper arm

### Blood Pressure Cuffs

#### Welch Allyn RPM-1700 / Welch Allyn 1700
- **Manufacturer**: Welch Allyn (Hillrom)
- **Measurements**: Systolic BP, Diastolic BP, Pulse
- **Connectivity**: Cellular or Bluetooth
- **Used in Pathways**: All acute and post-acute pathways
- **Notes**: Automatic inflation, self-measuring

#### Omron BP7000 / Omron BP Series
- **Manufacturer**: Omron Healthcare
- **Measurements**: Systolic BP, Diastolic BP, Pulse
- **Connectivity**: Bluetooth to smartphone
- **Used in Pathways**: All acute and post-acute pathways (alternative to Welch Allyn)
- **Notes**: Consumer-grade option for post-acute monitoring

### Pulse Oximeters

#### Nonin 3230 (Fingertip Pulse Oximeter)
- **Manufacturer**: Nonin Medical
- **Measurements**: SpO2, Pulse Rate
- **Connectivity**: Bluetooth
- **Used in Pathways**:
  - CHF Acute* (optional)
  - COPD Acute (if not using Everion)
  - Pneumonia Acute (if not using Everion)
  - Hypertension Acute* (optional)
  - Diabetes Acute* (optional)
  - DVT Acute (required)
  - COVID-19 Acute (if not using Everion)
- **Notes**: Spot-check measurements

#### Nonin 3203 (Spot-Check Model)
- **Manufacturer**: Nonin Medical
- **Measurements**: SpO2, Pulse Rate
- **Connectivity**: Bluetooth
- **Used in Pathways**: DVT Post-Acute (spot checks, Q6hrs initially)
- **Notes**: Intermittent monitoring model

### Weight Scales

#### Welch Allyn RPM-SCALE100
- **Manufacturer**: Welch Allyn (Hillrom)
- **Measurements**: Body weight
- **Connectivity**: Cellular
- **Used in Pathways**:
  - CHF Acute (required)
  - CHF Post-Acute (required)
- **Notes**: Automatic transmission, 400 lb capacity

#### ForaCare W550 (Connected Scale)
- **Manufacturer**: ForaCare
- **Measurements**: Body weight
- **Connectivity**: Bluetooth
- **Used in Pathways**:
  - CHF Acute (alternative)
  - CHF Post-Acute (alternative)
- **Notes**: Consumer-grade alternative

### Glucometers

#### ForaCare Test N Go (TnG Go)
- **Manufacturer**: ForaCare
- **Measurements**: Blood glucose
- **Connectivity**: Bluetooth to smartphone
- **Used in Pathways**:
  - Diabetes Acute (required)
  - Diabetes Post-Acute (required)
- **Notes**: Includes test strips, lancets, and control solution

### Thermometers

#### Oral/Tympanic Thermometers
- **Manufacturer**: Various approved brands
- **Measurements**: Body temperature (oral, tympanic, or temporal artery)
- **Connectivity**: Manual entry or Bluetooth (model-dependent)
- **Used in Pathways**:
  - Pneumonia Acute (required if not using Everion)
  - Pneumonia Post-Acute (required)
  - Hypertension Acute* (optional)
  - DVT Acute* (optional)
  - COVID-19 Acute (required if not using Everion)
  - COVID-19 Post-Acute (required)
- **Notes**: Standard medical-grade thermometers; oral/tympanic preferred

## Pathway Usage Matrix

| Device Type | CHF | COPD | Pneumonia | HTN | Diabetes | DVT | COVID |
|-------------|-----|------|-----------|-----|----------|-----|-------|
| **VitalConnect VitalPatch** | Acute* | — | — | Acute* | Acute* | Acute* | — |
| **Everion Armband** | — | Both* | Both* | — | — | — | Both* |
| **BP Cuff (Welch Allyn/Omron)** | Both | Both | — | Both | Both | Both | Both |
| **Pulse Oximeter (Nonin)** | Acute* | Acute | Acute | Acute* | Acute* | Both | Acute |
| **Weight Scale** | Both | — | — | — | — | — | — |
| **Glucometer** | — | — | — | — | Both | — | — |
| **Thermometer** | — | — | Both | Acute* | — | Acute* | Both |

**Legend:**
- **Both**: Required in both acute and post-acute pathways
- **Acute**: Required in acute pathway only
- **Acute***: Optional in acute pathway (denoted by * in SOPs)
- **—**: Not used in this pathway

## Device Selection Guidelines

### Acute Care Pathways
- Prioritize continuous telemetry (VitalConnect/Everion) for real-time monitoring
- Multiple device types per patient (e.g., telemetry + BP cuff + pulse oximeter)
- Higher frequency measurements

### Post-Acute Care Pathways
- Lighter device footprint (typically 2-3 devices)
- Focus on self-measurement devices (BP cuff, scale, glucometer)
- Consumer-grade alternatives acceptable for stable patients

### Comorbidity Considerations
- **CHF + Diabetes**: Add glucometer to CHF device set
- **COPD + HTN**: Ensure BP cuff included with Everion armband
- **Multiple conditions**: Combine device requirements; avoid duplication

## Technical Requirements

### Connectivity
- All devices must integrate with care coordination platform
- Bluetooth devices require compatible smartphone/tablet
- Cellular devices operate independently
- Manual entry backup available for connectivity issues

### Patient Training
- Device setup and daily use instruction required
- Proper measurement technique critical for accuracy
- Troubleshooting guide provided for each device

### Data Transmission
- Measurements auto-transmit to clinical dashboard
- Manual sync available as backup
- Alerts generated based on thresholds (see `alert-thresholds.md`)

## Maintenance & Support

- Device replacement protocols for malfunction
- Battery/power supply monitoring
- Return shipping labels for post-program device collection
- 24/7 technical support hotline for patients

---

**Note**: Device models and manufacturers may be updated periodically. Always verify current approved device list with care coordination team before patient enrollment.
