# MQTT-SN Wireless Sensor Network - Timing & Throughput Research
A distributed IoT research project investigating the relationship betweem precision time synchronization and MQTT-SN message delivery performance across a constrained wireless sensor network.

## The Research Question
Does a custom adaptive message delivery algorithm improve MQTT-SN throughput and latency consistency compared to native MQTT-SN behavior across a chrony-synchronized ESP32 wireless sensor network?

## System Architecture
- 3x ESP32-WROOM-32 nodes connected via mobile hotspot
- MQTT-SN overUDP to minimize packet overhead
- chrony/NTP for microsecond-precision clock synchronization
- Python telemetry pipeline exporting performance data to CSV
- Stress tested to identify physical throughput limits

## What Was Tested
- Native MQTT-SN delivery (no algorithm, no synchronization) - baseline
- chrony-synchronized nodes with adaptive delivery algorithm - full system performance

## Findings
Three conditions were tested:
- baseline, where the WSN was local to the accesspoint
- weak, where the WSN and the accesspoint were separated by about a ~100 meters
- Burst where a node would send 3 messages one after another

Findings and data are presented in the MQTT-SN_over_WSN.pdf with data and charts

## Future Work
Programming with ESP-IDF and comparing to the prototyping Arduino script that was written
