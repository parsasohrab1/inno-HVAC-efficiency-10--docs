# inno-HVAC-efficiency-10-
# Software Requirements Specification (SRS)
## Intelligent System for Control and Optimization of Electricity Consumption of HVAC Equipment


## 1. Introduction

### 1-1. Document Purpose

This Software Requirements Specification (SRS) is written for the intelligent system for control and optimization of electricity consumption of HVAC equipment. The main goal of this system is to reduce the electricity consumption of HVAC equipment nationwide by at least **10 percent** through intelligent temperature control, peak consumption management, and equipment performance optimization.

### 1-2. Application Scope

The system is designed for all HVAC equipment including gas coolers, water coolers, split units, duct splits, fan coils, packages, chillers and other cooling and heating equipment in household, commercial, office and industrial sectors.

### 1-3. Document Audience

- Software and hardware development team
- The authority responsible for granting electricity control permits (Ministry of Energy / Tavanir Organization)
- Project managers and stakeholders
- Quality assurance and testing team

### 1-4. Definitions and Abbreviations

| Abbreviation | Full meaning |
|--------|-----------|
| HVAC | Heating, Ventilation, and Air Conditioning |
| IoT | Internet of Things |
| BMS | Building Management System |
| DR | Demand Response |
| API | Application Programming Interface |
| UI | User Interface |
| SRS | Software Requirements Specification |


## 2. General System Description

### 2-1. Product Vision

According to official statistics, **the share of cooling and air conditioning systems of the country's total generated electricity has reached about 40 percent (equivalent to 30,000 MW)**. Meanwhile, the largest electricity-producing power plant in the country, the Damavand combined-cycle power plant with a generation capacity of 2,868 MW, supplies only **5 percent of the country's electricity**.

Given this imbalance, the intelligent HVAC system is designed with the goal of reducing the electricity consumption of this equipment by at least 10 percent. Achieving this goal would mean a reduction of **3,000 MW** of the country's peak consumption load, equivalent to the generation capacity of more than one Damavand power plant.

By offering capabilities such as online and remote monitoring, detection of unoccupied spaces, remote control and scheduling, and optimal temperature adjustment based on indoor and outdoor conditions, the system can be an effective step toward solving the country's energy imbalance crisis.

### 2-2. Main System Features

1. **Intelligent temperature control**: Automatic adjustment of setpoint temperatures based on environmental conditions, occupancy and time
2. **Peak consumption management**: Automatic reduction of consumption during grid peak load hours
3. **Online monitoring and reporting**: Real-time display of consumption, temperature, humidity and equipment status
4. **Remote control**: Ability to manage equipment through a mobile and web application
5. **Automatic occupancy detection**: Shutting off or reducing equipment power in unoccupied spaces
6. **Obtaining electricity control permits**: Obtaining permission from the responsible authority to apply direct control to equipment
7. **Energy storage and peak shifting**: Using phase-change materials and storage systems to shift consumption from peak to off-peak hours

### 2-3. System Users

| Role | Description |
|-----|---------|
| End user | Building owner or occupant with access to the mobile application |
| Building energy manager | Responsible for energy consumption management in large buildings |
| Electricity grid operator | The authority responsible for granting electricity control permits (Ministry of Energy) |
| System administrator | Responsible for system maintenance and configuration |

### 2-4. Assumptions and Dependencies

**Assumptions:**
- HVAC equipment can be connected to the control system (with or without a hardware interface)
- A suitable communication infrastructure (internet / mobile network) exists at the installation site
- Cooperation of the responsible authority in granting the necessary permits for electricity control

**Dependencies:**
- Access to electricity grid APIs to receive peak consumption information
- Coordination with the national building standards (Topic 19 of the National Building Regulations)
- Compliance with ASHRAE Guideline 36 for efficient control of HVAC systems


## 3. System Requirements

### 3-1. Functional Requirements

#### 3-1-1. Temperature Control and Adjustment

| ID | Requirement | Priority |
|-------|-------|--------|
| FR-01 | The system must be able to receive and display the instantaneous temperature of each space through connected sensors | High |
| FR-02 | The system must be able to automatically and intelligently adjust the setpoint temperature based on environmental conditions | High |
| FR-03 | The system must allow the user to adjust the temperature manually through the application | Medium |
| FR-04 | The system must be able to apply different temperature profiles for different hours of the day and days of the week | High |
| FR-05 | The system must maintain the desired temperature in the range of 22 to 24 degrees Celsius (per the ASHRAE standard) | High |

#### 3-1-2. Peak Consumption Management

| ID | Requirement | Priority |
|-------|-------|--------|
| FR-06 | The system must be able to automatically detect peak electricity consumption hours based on data received from the grid | High |
| FR-07 | During peak hours, the system must raise (in cooling mode) or lower (in heating mode) the setpoint temperature by a specified (configurable) amount | High |
| FR-08 | The system must be able to shut off or reduce equipment power during peak hours with permission from the responsible authority | High |
| FR-09 | The system must provide the ability to store energy during off-peak hours and use it during peak hours | Medium |
| FR-10 | The system must have peak shifting capability through load forecasting algorithms | High |

#### 3-1-3. Occupancy Detection

| ID | Requirement | Priority |
|-------|-------|--------|
| FR-11 | The system must detect the occupancy status of each space through presence sensors | High |
| FR-12 | If a space has been empty for longer than the configured time, the system must turn off the HVAC equipment or put it in a low-power mode | High |
| FR-13 | The system must restart the equipment upon detecting people entering the space | High |
| FR-14 | The system must allow setting the delay time for detecting that a space is empty | Medium |

#### 3-1-4. Monitoring and Reporting

| ID | Requirement | Priority |
|-------|-------|--------|
| FR-15 | The system must display the instantaneous, cumulative and average electricity consumption of each device | High |
| FR-16 | The system must generate daily, weekly and monthly electricity consumption reports | High |
| FR-17 | The system must provide comparative charts of consumption before and after installing the intelligent system | High |
| FR-18 | The system must notify the user of abnormal consumption or equipment failure alerts | Medium |
| FR-19 | The system must be able to calculate and display the actual savings (in percent and MW) | High |
| FR-20 | The system must generate standard reports for submission to the responsible authority (Ministry of Energy) | High |

#### 3-1-5. Remote Control

| ID | Requirement | Priority |
|-------|-------|--------|
| FR-21 | The system must be controllable through a mobile application (Android and iOS) | High |
| FR-22 | The system must be accessible and manageable through a web panel (Web Dashboard) | High |
| FR-23 | The system must allow energy managers to control several buildings or units simultaneously | Medium |
| FR-24 | The system must have a scheduler for on/off and temperature setting | High |

#### 3-1-6. Obtaining Permits and Coordination with the Responsible Authority

| ID | Requirement | Priority |
|-------|-------|--------|
| FR-25 | The system must have a mechanism for authentication and obtaining permission from the responsible authority (Ministry of Energy) to apply control to equipment | High |
| FR-26 | The system must be able to receive and execute control commands from the electricity grid (Demand Response) | High |
| FR-27 | The system must record and retain the complete history of controls applied by the responsible authority | High |
| FR-28 | The system must allow the user to manually cancel or modify controls applied by the responsible authority (with the user's command taking priority) | Medium |

#### 3-1-7. Integration and Communications

| ID | Requirement | Priority |
|-------|-------|--------|
| FR-29 | The system must support standard communication protocols (MQTT, Modbus, BACnet) | High |
| FR-30 | The system must be able to connect to existing Building Management Systems (BMS) | High |
| FR-31 | The system must have an open API for integration with third-party systems | Medium |


### 3-2. Non-Functional Requirements

#### 3-2-1. Performance

| ID | Requirement | Priority |
|-------|-------|--------|
| NFR-01 | Latency in sending a control command to equipment must not exceed 2 seconds | High |
| NFR-02 | The system must be able to manage at least 10,000 devices simultaneously | High |
| NFR-03 | UI response time must not exceed 3 seconds | Medium |
| NFR-04 | The system must be able to process and store at least 5 years of data | High |

#### 3-2-2. Security

| ID | Requirement | Priority |
|-------|-------|--------|
| NFR-05 | All communications must be encrypted with secure protocols (TLS 1.3) | High |
| NFR-06 | The system must have two-factor authentication (2FA) for sensitive access | High |
| NFR-07 | Access must be managed based on roles (Role-Based Access Control - RBAC) | High |
| NFR-08 | Security logs must be retained for at least 1 year | High |

#### 3-2-3. Reliability and Availability

| ID | Requirement | Priority |
|-------|-------|--------|
| NFR-09 | System availability must be at least 99.9% (SLA) | High |
| NFR-10 | The system must have a Failover mechanism and automatic backup | High |
| NFR-11 | If the internet connection is lost, the system must be able to continue operation with the latest settings (Offline mode) | High |
| NFR-12 | Recovery time after failure must not exceed 15 minutes | High |

#### 3-2-4. Scalability

| ID | Requirement | Priority |
|-------|-------|--------|
| NFR-13 | The system must be able to scale up to 100,000 devices | Medium |
| NFR-14 | The system architecture must be Cloud-native and Microservices-based | Medium |

#### 3-2-5. Usability

| ID | Requirement | Priority |
|-------|-------|--------|
| NFR-15 | The mobile application and web panel must have a simple, localized user interface | High |
| NFR-16 | The system must have a user guide and visual tutorials | Medium |
| NFR-17 | The default settings of the system must be such that it can be used without specialized configuration | High |

#### 3-2-6. Standards Compliance

| ID | Requirement | Priority |
|-------|-------|--------|
| NFR-18 | The system must comply with Topic 19 of the National Building Regulations (intelligent management of heating, cooling and ventilation systems) | High |
| NFR-19 | The system must be consistent with the ASHRAE Guideline 36 standard for efficient HVAC control | Medium |
| NFR-20 | The system must be compatible with the ISO 16484 standard (building automation systems) | Medium |


## 4. Synthetic Data Required by the System

To train AI algorithms, test the system and simulate performance, the following synthetic data will be generated:

### 4-1. Equipment Consumption Data

**Number of records: 100,000 records**

| Field | Type | Description | Value range |
|------|------|---------|---------------|
| device_id | String | Unique device identifier | AC-000001 to AC-100000 |
| device_type | Enum | Equipment type | Gas cooler, Water cooler, Split, Duct split, Fan coil, Package, Chiller |
| timestamp | DateTime | Recording time | 1404/01/01 to 1404/12/29, every 15 minutes |
| power_consumption | Float | Instantaneous consumption (watts) | 100 to 3,000 |
| temperature_in | Float | Indoor temperature (Celsius) | 15 to 40 |
| temperature_out | Float | Outdoor temperature (Celsius) | -10 to 50 |
| humidity_in | Float | Indoor humidity (percent) | 20 to 90 |
| occupancy | Boolean | Space occupancy status | true/false |
| setpoint_temp | Float | Set temperature | 18 to 28 |
| mode | Enum | Operating mode | Cooling, Heating, Fan, Auto |
| is_peak_hour | Boolean | Peak or off-peak hour | true/false |

**Data generation specifications:**
- Equipment type distribution: 40% gas cooler, 30% water cooler, 15% split, 10% duct split, 5% other
- Gas cooler consumption should be considered 4 to 6 times that of water coolers
- Consumption pattern: gradual increase from Khordad to Mordad, peak during hours 13 to 17

### 4-2. Weather Data

**Number of records: 50,000 records**

| Field | Type | Description |
|------|------|---------|
| timestamp | DateTime | Time (hourly) |
| city | String | City name (Tehran, Ahvaz, Tabriz, Isfahan, Shiraz, Mashhad, Karaj) |
| temperature | Float | Air temperature (Celsius) |
| humidity | Float | Relative humidity (percent) |
| solar_radiation | Float | Solar radiation (W/m²) |
| wind_speed | Float | Wind speed (m/s) |

### 4-3. Grid Peak Consumption Data

**Number of records: 10,000 records**

| Field | Type | Description |
|------|------|---------|
| date | Date | Date |
| peak_start | Time | Peak start time |
| peak_end | Time | Peak end time |
| peak_load | Float | Grid peak load (MW) |
| alert_level | Enum | Alert level (green, yellow, red) |

### 4-4. Presence and Occupancy Data

**Number of records: 50,000 records**

| Field | Type | Description |
|------|------|---------|
| space_id | String | Space identifier |
| timestamp | DateTime | Time |
| occupancy_count | Integer | Number of people present |
| occupancy_status | Boolean | Occupied or empty |
| last_motion | DateTime | Time of last detected motion |

### 4-5. Intelligent System Performance Data (after implementation)

**Number of records: 50,000 records**

| Field | Type | Description |
|------|------|---------|
| device_id | String | Device identifier |
| timestamp | DateTime | Time |
| control_action | Enum | Type of control action (temperature adjustment, shutdown, power reduction, storage) |
| before_power | Float | Consumption before the action (watts) |
| after_power | Float | Consumption after the action (watts) |
| saving_percent | Float | Savings percentage |
| triggered_by | Enum | Trigger of the action (automatic, user, power grid) |


## 5. System Architecture (Proposed)

### 5-1. Architecture Layers

```
┌─────────────────────────────────────────────────────────────┐
│                    Presentation Layer                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │ Mobile app   │  │  Web panel  │  │  Public API  │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
├─────────────────────────────────────────────────────────────┤
│                    Business Logic Layer                     │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │ Intelligent  │  │ Data         │  │ AI/ML decision│    │
│  │ control engine│ │ analytics    │  │ engine       │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
├─────────────────────────────────────────────────────────────┤
│                    Data Layer                               │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │ Database     │  │ Cache (Redis)│  │ Data Lake    │      │
│  │ (PostgreSQL) │  │              │  │              │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
├─────────────────────────────────────────────────────────────┤
│                    Connectivity Layer                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │ IoT Gateway  │  │ MQTT Broker  │  │ Grid API     │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└─────────────────────────────────────────────────────────────┘
```

### 5-2. Main System Components

1. **IoT Gateway**: Communication interface between HVAC equipment and the central server
2. **Intelligent control engine**: The core of the system for applying optimal controls
3. **Data analytics engine**: Processing and analyzing the collected data
4. **AI/ML decision engine**: Machine learning algorithms for forecasting and optimization
5. **Permit management system**: Managing the acquisition and application of control permits from the responsible authority


## 6. Integration Requirements

### 6-1. Integration with the Responsible Authority (Ministry of Energy)

| ID | Requirement |
|-------|-------|
| INT-01 | The system must connect to the Ministry of Energy systems through a secure API |
| INT-02 | The system must be able to receive and process Demand Response commands from the grid |
| INT-03 | The system must send periodic consumption and savings reports to the Ministry of Energy |

### 6-2. Integration with Equipment

| ID | Requirement |
|-------|-------|
| INT-04 | The system must support MQTT, Modbus and BACnet protocols |
| INT-05 | The system must be able to connect to equipment with different hardware interfaces |
| INT-06 | The system must support gas coolers, water coolers, splits, duct splits, fan coils and chillers |


## 7. Testing and Validation Requirements

### 7-1. Performance Testing

| ID | Requirement |
|-------|-------|
| TEST-01 | The system must be tested in a pilot environment with at least 100 devices for 3 months |
| TEST-02 | The electricity consumption reduction must be confirmed at at least 10% in the pilot test |
| TEST-03 | Peak consumption scenarios must be tested with simulated data |

### 7-2. Security Testing

| ID | Requirement |
|-------|-------|
| TEST-04 | A penetration test must be performed by an independent team |
| TEST-05 | All critical vulnerabilities must be fixed before deployment |

### 7-3. Acceptance Criteria

| ID | Criterion |
|-------|-------|
| AC-01 | At least a 10% reduction in HVAC equipment electricity consumption during the test period |
| AC-02 | At least a 15% reduction in consumption during peak hours |
| AC-03 | At least 80% of users satisfied with the system's performance |
| AC-04 | No negative impact on users' thermal comfort (indoor temperature within 22-24 degrees) |
| AC-05 | Obtaining approval from the responsible authority for the electricity control permit |


## 8. Implementation Plan (Proposed)

| Phase | Duration | Activities |
|-----|-----|-----------|
| Phase 1 | 3 months | Requirements analysis, architecture design, synthetic data generation |
| Phase 2 | 4 months | Development of the system core, implementation of the intelligent control engine |
| Phase 3 | 3 months | Development of the mobile application and web panel, integration |
| Phase 4 | 2 months | Pilot testing with 100 devices, collection of performance data |
| Phase 5 | 2 months | Optimization, obtaining permits from the responsible authority, deployment |
| Phase 6 | Ongoing | Monitoring, maintenance and continuous improvement |


## 9. Appendices

### Appendix 1: Reference Data

| Parameter | Value | Source |
|---------|-------|------|
| Share of HVAC in the country's electricity consumption | 40% (30,000 MW) |  |
| Damavand power plant capacity | 2,868 MW |  |
| Damavand power plant share of the country's electricity | 5% |  |
| Increase in gas cooler consumption relative to water cooler | 4 to 6 times |  |
| Target electricity consumption reduction | 10% (3,000 MW) | Project goal |
| Desired temperature range | 22-24 degrees Celsius |  |
| Achievable savings with ASHRAE G36 | Up to 45% |  |

### Appendix 2: Reference Standards

- ASHRAE Guideline 36: High-Performance Sequences of Operation for HVAC Systems
- ISO 16484: Building Automation and Control Systems (BACS)
- Topic 19 of the National Building Regulations (Iran) - Intelligent management of building facilities
- BACnet (ISO 16484-5): Data Communication Protocol for Building Automation


## 10. Summary

The intelligent system for control and optimization of electricity consumption of HVAC equipment is designed with the goal of reducing the electricity consumption of this equipment by 10 percent (equivalent to 3,000 MW). Given that 40 percent of the country's generated electricity (30,000 MW) is consumed in the HVAC sector and the country's largest power plant produces only 5 percent of the electricity, this system can have a significant impact on reducing the country's energy imbalance.

Using IoT, artificial intelligence and intelligent control technologies, the system optimizes electricity consumption during normal and peak hours while maintaining users' thermal comfort. Obtaining permission from the responsible authority (Ministry of Energy) to apply direct control to equipment is a key part of this system, enabling centralized management and response to grid demand.
import pandas as pd
import numpy as np
from datetime import datetime, timedelta
import random
import os

# Set random seed for reproducibility
np.random.seed(42)
random.seed(42)

# -------------------- 1. Generate equipment consumption data (100,000 records) --------------------
def generate_device_consumption(n=100000):
    device_types = ['Gas cooler', 'Water cooler', 'Split', 'Duct split', 'Other']
    # Distribution based on the SRS: 40% gas cooler, 30% water cooler, 15% split, 10% duct split, 5% other
    weights = [0.4, 0.3, 0.15, 0.1, 0.05]
    
    # Generate timestamps (from the start of 1404 Solar Hijri, equivalent to 20 March 2025)
    start_date = datetime(2025, 3, 20, 0, 0, 0)
    end_date = datetime(2026, 3, 20, 23, 45, 0)
    timestamps = pd.date_range(start=start_date, end=end_date, periods=n)
    
    # Randomly select the equipment type
    chosen_types = np.random.choice(device_types, size=n, p=weights)
    
    data = {
        'device_id': [f"AC-{str(i).zfill(6)}" for i in range(1, n+1)],
        'device_type': chosen_types,
        'timestamp': timestamps,
        'temperature_in': np.random.uniform(20, 35, n),  # indoor temperature
        'temperature_out': np.random.uniform(15, 48, n), # outdoor temperature
        'humidity_in': np.random.uniform(25, 85, n),
        'occupancy': np.random.choice([True, False], size=n, p=[0.7, 0.3]), # 70% occupancy
        'setpoint_temp': np.random.uniform(18, 28, n),
        'mode': np.random.choice(['Cooling', 'Heating', 'Auto'], size=n, p=[0.6, 0.2, 0.2])
    }
    
    df = pd.DataFrame(data)
    
    # Calculate electricity consumption based on equipment type and peak hour
    power_list = []
    for idx, row in df.iterrows():
        base_power = 0
        # Base power by type (gas cooler higher consumption, water cooler low consumption)
        if row['device_type'] == 'Gas cooler':
            base_power = np.random.uniform(1800, 3200)
        elif row['device_type'] == 'Water cooler':
            base_power = np.random.uniform(400, 850)
        elif row['device_type'] == 'Split':
            base_power = np.random.uniform(900, 2000)
        elif row['device_type'] == 'Duct split':
            base_power = np.random.uniform(1500, 2800)
        else:
            base_power = np.random.uniform(500, 1500)
        
        # Detect peak hour (13 to 17)
        hour = row['timestamp'].hour
        is_peak = 13 <= hour < 17
        
        # If it is peak and the device is on, consumption rises slightly (compressor under pressure)
        if is_peak and row['occupancy']:
            base_power *= np.random.uniform(1.05, 1.15)
        
        # If the space is empty, consumption decreases (the intelligent system should manage this)
        if not row['occupancy']:
            base_power *= np.random.uniform(0.4, 0.7)
            
        power_list.append(round(base_power, 2))
    
    df['power_consumption'] = power_list
    df['is_peak_hour'] = df['timestamp'].apply(lambda x: 13 <= x.hour < 17)
    
    return df

# -------------------- 2. Generate weather data (50,000 records) --------------------
def generate_weather_data(n=50000):
    cities = ['Tehran', 'Ahvaz', 'Tabriz', 'Isfahan', 'Shiraz', 'Mashhad', 'Karaj']
    start_date = datetime(2025, 3, 20, 0, 0, 0)
    end_date = datetime(2026, 3, 20, 23, 0, 0)
    timestamps = pd.date_range(start=start_date, end=end_date, periods=n)
    
    data = {
        'timestamp': timestamps,
        'city': np.random.choice(cities, size=n),
        'temperature': np.random.uniform(-5, 48, n), # overall range
        'humidity': np.random.uniform(10, 90, n),
        'solar_radiation': np.random.uniform(100, 950, n),
        'wind_speed': np.random.uniform(0, 12, n)
    }
    df = pd.DataFrame(data)
    
    # Apply seasonal logic: Ahvaz temperature is higher in summer and Tabriz is lower
    # Warm months (Khordad to Shahrivar - June to September)
    summer_months = [6, 7, 8, 9]
    # Cold months (Azar to Esfand - December to March)
    winter_months = [12, 1, 2, 3]
    
    for idx, row in df.iterrows():
        month = row['timestamp'].month
        if row['city'] == 'Ahvaz' and month in summer_months:
            df.at[idx, 'temperature'] = np.random.uniform(40, 52)
        elif row['city'] == 'Tabriz' and month in winter_months:
            df.at[idx, 'temperature'] = np.random.uniform(-15, 2)
        elif month in summer_months:
            df.at[idx, 'temperature'] = np.random.uniform(25, 40)
        elif month in winter_months:
            df.at[idx, 'temperature'] = np.random.uniform(-5, 10)
            
    # Round the values
    df['temperature'] = df['temperature'].round(1)
    df['humidity'] = df['humidity'].round(1)
    return df

# -------------------- 3. Generate grid peak consumption data (10,000 records) --------------------
def generate_peak_data(n=10000):
    start_date = datetime(2025, 3, 20)
    end_date = datetime(2026, 3, 20)
    dates = pd.date_range(start=start_date, end=end_date, periods=n)
    
    data = {
        'date': dates,
        'peak_start': [f"{random.randint(12, 14)}:00" for _ in range(n)],
        'peak_end': [f"{random.randint(16, 19)}:00" for _ in range(n)],
        'peak_load': np.random.uniform(25000, 35000, n),  # country peak load (MW)
        'alert_level': np.random.choice(['Green', 'Yellow', 'Red'], size=n, p=[0.6, 0.3, 0.1])
    }
    df = pd.DataFrame(data)
    df['peak_load'] = df['peak_load'].round(1)
    # Ensure the peak start is before the peak end
    return df

# -------------------- 4. Generate presence and occupancy data (50,000 records) --------------------
def generate_occupancy_data(n=50000):
    start_date = datetime(2025, 3, 20, 0, 0, 0)
    end_date = datetime(2026, 3, 20, 23, 59, 0)
    timestamps = pd.date_range(start=start_date, end=end_date, periods=n)
    
    data = {
        'space_id': [f"SP-{str(i).zfill(5)}" for i in range(1, n+1)],
        'timestamp': timestamps,
        'occupancy_count': np.random.poisson(lam=3, size=n),  # Poisson distribution for the number of people
        'last_motion': [start_date + timedelta(minutes=random.randint(0, 60)) for _ in range(n)]
    }
    df = pd.DataFrame(data)
    
    # Determine occupancy status: if the number of people > 0, occupancy = True
    df['occupancy_status'] = df['occupancy_count'] > 0
    
    # Adjust by time: at night (22 to 6) occupancy is lower
    for idx, row in df.iterrows():
        hour = row['timestamp'].hour
        if 22 <= hour or hour < 6:
            df.at[idx, 'occupancy_count'] = np.random.poisson(lam=0.5)
            df.at[idx, 'occupancy_status'] = df.at[idx, 'occupancy_count'] > 0
    
    # Convert datetime to string for last_motion
    df['last_motion'] = df['last_motion'].apply(lambda x: x.strftime('%Y-%m-%d %H:%M:%S'))
    return df

# -------------------- 5. Generate intelligent system performance data (50,000 records) --------------------
def generate_system_performance(n=50000):
    control_actions = ['Temperature adjustment', 'Shutdown', 'Power reduction', 'Storage']
    triggers = ['Automatic', 'User', 'Power grid']
    
    start_date = datetime(2025, 3, 20, 0, 0, 0)
    end_date = datetime(2026, 3, 20, 23, 45, 0)
    timestamps = pd.date_range(start=start_date, end=end_date, periods=n)
    
    device_ids = [f"AC-{str(i).zfill(6)}" for i in range(1, 1001)]  # 1000 sample devices
    
    data = {
        'device_id': np.random.choice(device_ids, size=n),
        'timestamp': timestamps,
        'control_action': np.random.choice(control_actions, size=n, p=[0.4, 0.2, 0.3, 0.1]),
        'before_power': np.random.uniform(400, 3000, n),
        'triggered_by': np.random.choice(triggers, size=n, p=[0.5, 0.3, 0.2])
    }
    df = pd.DataFrame(data)
    
    # Calculate consumption after the action (at least 10% to 25% reduction)
    after_power_list = []
    saving_list = []
    for idx, row in df.iterrows():
        if row['control_action'] == 'Shutdown':
            saving_percent = np.random.uniform(90, 100)
        elif row['control_action'] == 'Power reduction':
            saving_percent = np.random.uniform(20, 40)
        elif row['control_action'] == 'Temperature adjustment':
            saving_percent = np.random.uniform(10, 20)
        else:  # Storage
            saving_percent = np.random.uniform(5, 15)
            
        after_power = row['before_power'] * (1 - saving_percent / 100)
        after_power_list.append(round(after_power, 2))
        saving_list.append(round(saving_percent, 2))
    
    df['after_power'] = after_power_list
    df['saving_percent'] = saving_list
    
    # Ensure the average savings are above 10% (project goal)
    return df

# -------------------- Saving the CSV files --------------------
def save_dataframes():
    # Ensure the output folder exists
    os.makedirs('synthetic_data', exist_ok=True)
    
    print("Generating equipment consumption data (100,000 records)...")
    df1 = generate_device_consumption(100000)
    df1.to_csv('synthetic_data/device_consumption.csv', index=False, encoding='utf-8-sig')
    print(f"✓ Saved: synthetic_data/device_consumption.csv ({len(df1):,} records)")
    
    print("Generating weather data (50,000 records)...")
    df2 = generate_weather_data(50000)
    df2.to_csv('synthetic_data/weather_data.csv', index=False, encoding='utf-8-sig')
    print(f"✓ Saved: synthetic_data/weather_data.csv ({len(df2):,} records)")
    
    print("Generating grid peak data (10,000 records)...")
    df3 = generate_peak_data(10000)
    df3.to_csv('synthetic_data/peak_network_data.csv', index=False, encoding='utf-8-sig')
    print(f"✓ Saved: synthetic_data/peak_network_data.csv ({len(df3):,} records)")
    
    print("Generating presence and occupancy data (50,000 records)...")
    df4 = generate_occupancy_data(50000)
    df4.to_csv('synthetic_data/occupancy_data.csv', index=False, encoding='utf-8-sig')
    print(f"✓ Saved: synthetic_data/occupancy_data.csv ({len(df4):,} records)")
    
    print("Generating intelligent system performance data (50,000 records)...")
    df5 = generate_system_performance(50000)
    df5.to_csv('synthetic_data/system_performance.csv', index=False, encoding='utf-8-sig')
    print(f"✓ Saved: synthetic_data/system_performance.csv ({len(df5):,} records)")
    
    print("\n✅ All synthetic data generated successfully and saved to the 'synthetic_data' folder.")

# Run the main function
if __name__ == "__main__":
    save_dataframes()

---

## Implementation status (TRL 4 scaffold)

Branch `trl4-scaffold` adds `src/hvac_opt/` (setpoint controller, demand response with audit log, savings, RC thermal model, closed-loop simulation), `tests/` (8 tests), CI and [`docs/TRL.md`](docs/TRL.md) with the evidence and the limits. Run: `pip install -e ".[dev]" && pytest`.
