# DDoS Visual Forensic Analysis: FiveM Server Attack

## Project Overview
This repository contains a comprehensive forensic analysis pipeline for investigating Distributed Denial of Service (DDoS) attacks using raw packet captures (`.pcapng`). Using a real-world dataset from a FiveM game server attack (August 2022), this project transforms millions of raw packets into an interactive, presentation-ready forensic dashboard.

### Key Features
- **High-Performance Parsing**: Stream-parsing of large PCAP files using `dpkt`.
- **Interactive Visualizations**: Dynamic charts for traffic pulses, protocol distribution, and port targeting using `Plotly`.
- **Geographical Intelligence**: Mapping attack origins using `MaxMind GeoLite2` and `Folium` heatmaps.
- **Automated Dashboard**: Generates a consolidated `index.html` report with presentation talking points for faculty reviews.

## Analysis Methodology
We follow a 4-stage forensic data engineering process:
1. **Extraction**: Decoding binary packet data to extract IP headers, TCP/UDP flags, and TTL values.
2. **Normalization**: Scaling raw timestamps into PPS (Packets Per Second) and Mbps (Megabits Per Second) metrics.
3. **Enrichment**: Augmenting source IP addresses with Geo-location (Country, City) and ASN (ISP) data.
4. **Synthesis**: Correlating packet behavior (like TTL variance) with geographical clusters to identify botnet footprints.

## Forensic Modules
- **Module 1: Attack Pulse**: Visualizes the start, peak, and duration of the attack.
- **Module 2: Protocol Sunburst**: Identifies the primary attack vector (e.g., UDP Flood on Port 1222).
- **Module 3: Global Heatmap**: Shows the physical distribution of the attacking botnet.
- **Module 4: TTL Fingerprinting**: Uses Time-to-Live values to detect IP spoofing and distance of attackers.

## Getting Started
1. **Data**: Place your `.pcapng` file in the designated path.
2. **Database**: Download the `GeoLite2-City.mmdb` from MaxMind.
3. **Run**: Execute the Jupyter/Colab notebook to generate the `charts/` and the final `index.html`.

## Visual Report Preview
The final output is an interactive dashboard that organizes all charts with built-in "Faculty Presentation Points" to assist in technical explanations.

---
*Note: This project is intended for educational and forensic research purposes.*
