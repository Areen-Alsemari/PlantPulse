# PlantPulse

**A Pulse Ahead of Failure.**

Affordable, context-aware Industrial IoT monitoring with offline Edge AI.

## Overview

One unexpected equipment failure can interrupt an entire production line. Yet fixed-threshold monitoring can generate false alarms when operating conditions change, while early signs of deterioration may go unnoticed.

PlantPulse is a proposed plug-and-play Industrial IoT solution that turns existing industrial equipment into connected, self-monitoring assets. By combining sensor measurements, operating context and local AI inference, it aims to detect developing faults earlier, reduce unnecessary alerts and make predictive maintenance more accessible.

The initial application focuses on industrial pumps, with a design intended to expand to motors, compressors and other rotating machinery.

## The Problem

Industrial facilities face several challenges:

- Unplanned downtime and emergency repair costs
- False alarms caused by fixed monitoring thresholds
- Early faults that may be missed under changing operating conditions
- High costs and complexity of retrofitting advanced monitoring systems
- Dependence on network connectivity for some remote monitoring functions

## Proposed Solution

PlantPulse combines affordable sensing hardware, operating-context data and edge-based anomaly detection.

### Key Capabilities

**1. Plug-and-play monitoring**
A retrofit device using vibration, temperature and acoustic sensors to monitor existing equipment.

**2. Context-aware detection**
Sensor readings are interpreted alongside operating conditions such as speed and load to distinguish expected behavior from potential faults.

**3. Equipment health score**
A proposed 0–100 score summarizes equipment condition and supports monitoring of changes over time.

**4. Offline Edge AI**
Lightweight anomaly detection runs locally, allowing monitoring to continue during temporary network disruptions. Remote notifications and dashboard synchronization require connectivity.

**5. PLC data consistency checks**
Sensor measurements can be compared with PLC-reported operating information to flag potential inconsistencies for investigation.

**6. Maintenance alerts**
A dashboard presents equipment health, trends and warnings, with planned notifications to maintenance personnel.

## Proposed Architecture

```text
Industrial Equipment
        |
        v
Vibration / Temperature / Acoustic Sensors
        |
        v
ESP32 Edge Device
        |
        +--> Local Signal Processing
        |           |
        |           v
        |     Edge AI Anomaly Detection
        |
        +--> Sensor Data Transmission
                    |
                    v
           Node-RED / Data Integration
                    ^
                    |
              PLC via OPC UA
                    |
                    v
          Context-Aware Analysis
                    |
                    v
       Health Score and Alert Logic
                    |
                    v
       Monitoring Dashboard / Alerts
```

This architecture is preliminary and may change during prototyping. Local detection is intended to operate without continuous connectivity, while remote functions depend on an available communication path.

## Proposed Technology Stack

| Component | Proposed Technology |
|---|---|
| Edge hardware | ESP32 |
| Sensors | Vibration, temperature and acoustic sensors |
| Edge intelligence | Lightweight anomaly detection, potentially using Edge Impulse |
| Industrial integration | PLC and OPC UA |
| Data integration | Node-RED |
| Visualization | Web dashboard |
| Notifications | Mobile-accessible alerts |

## Initial Prototype Scope

The first prototype will focus on:

1. Collecting vibration, temperature and acoustic measurements from a pump test setup
2. Incorporating operating-state information from a PLC or simulated PLC source
3. Establishing baseline behavior under different operating conditions
4. Detecting deviations from expected behavior
5. Presenting a health score and alerts on a dashboard
6. Demonstrating local anomaly detection during a network interruption

## Planned Validation

The prototype will be evaluated using measures such as:

- Anomaly detection performance
- False alarm rate across different operating conditions
- Local inference latency
- Behavior during network interruptions
- Feasibility and cost of the retrofit hardware

Performance claims will be reported after testing.

## Development Status

**Stage: Concept / Hackathon Submission**

PlantPulse is currently a proposed solution for IoThon 2026 in the Smart Industry (IIoT) track. Hardware integration, model development and system validation are planned for the prototyping stage.

## Vision

Start with pumps. Expand across the plant.

PlantPulse aims to make condition monitoring accessible to more industrial facilities without requiring complete equipment replacement.
