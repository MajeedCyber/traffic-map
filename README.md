# Network Traffic Geolocation Visualizer

## Overview
This project demonstrates a method to visualize network traffic geolocation by analyzing a Wireshark packet capture (PCAP) file, converting the data into a KML (Keyhole Markup Language) format using Python, and mapping the results on Google Maps. The final output is a geographical map showing the source and destination IP connections as lines across the globe, with an example visualization spanning from the United States to Spain over the North Atlantic Ocean.

## Features
- **Packet Analysis**: Extracts source and destination IP addresses from a Wireshark PCAP file using the `dpkt` library.
- **Geolocation Mapping**: Converts IP addresses to geographical coordinates (latitude and longitude) using the `pygeoip` library with the GeoLiteCity database.
- **KML Generation**: Creates a KML file with placemarks and lines representing network connections, styled for visualization.
- **Google Maps Integration**: The generated KML file is imported into Google Maps to display the network traffic paths on a world map.

## Technologies Used
- **Python Libraries**:
  - `dpkt`: For parsing PCAP files and extracting IP data.
  - `pygeoip`: For geolocating IP addresses using the GeoLiteCity database.
  - `socket`: For converting binary IP addresses to human-readable format.
- **Wireshark**: To capture network traffic and export it as a PCAP file.
- **Google Maps**: To visualize the KML output on a geographical map.

## How It Works
1. **Input**: A PCAP file (`wire.pcap`) containing network traffic data is read using `dpkt`.
2. **IP Extraction**: Source and destination IP addresses are extracted from each packet.
3. **Geolocation**: The `pygeoip` library maps the IPs to their geographical coordinates (latitude and longitude).
4. **KML Creation**: A KML file is generated, where each network connection is represented as a line between the source and destination coordinates.
5. **Output**: The KML file (`output.kml`) is saved and can be imported into Google Maps for visualization.
6. **Visualization**: The final map (as shown below) displays the network paths, with lines connecting locations like the United States and Spain.

## Results
The output KML file was successfully visualized on Google Maps, showing network connections as red lines across the globe. In the example visualization, multiple connections are mapped between the eastern United States and Spain, with a consistent distance of 172,271.14 km, indicating the approximate path length over the North Atlantic Ocean.

### Visualization
Below is a screenshot of the network traffic paths visualized on Google Maps:

![Network Traffic Map](images/map.png)

## Usage
1. Ensure the GeoLiteCity database (`GeoLiteCity.dat`) is available for geolocation.
2. Capture network traffic using Wireshark and save it as a PCAP file.
3. Run the Python script to generate the KML file:
   ```bash
   python script.py
