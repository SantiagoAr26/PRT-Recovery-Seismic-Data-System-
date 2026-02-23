# PRT-Recovery-Seismic-Data-System-
PRT is a lightweight tool for recovering seismic data gaps in seismic-volcanic monitoring networks. The analysis is performed on real data obtained from the DataCenter and monitoring stations of the Geophysical Institute of the National Polytechnic School. IG-EPN, Ecuador.


As shown in the figure, a long single gap of SAG1 presents a continuous but extensive gap of 01d 09h 24m, resulting in Apre = 65.21%. The figure illustrates the pre-recovery waveform availability at SAG1 and visually identifies the start/end of the gap. For this station, the primary target streams for continuity correspond to the three-component velocity channels (HHZ/HHN/HHE) and the infrasound channel (BDF), which are relevant for event analysis and multi-parameter correlation during the selected window.

<p align="center">
  <img src="figures/Gap_saga_station.png" width="70%">
</p>


The workflow describes how incoming data streams are first validated for timestamps and sequences to ensure temporal continuity. When no discontinuities are detected, data are written to the archive continuously. If a temporal gap is identified, the system classifies the discontinuity and activates the -PRT- recovery mechanism upon reconnection. During this phase, buffered waveform segments stored at the station or datalogger level are retrieved and reintegrated into the archive. A synchronization and integrity validation step ensures that recovered records are chronologically consistent and free of duplication before updating the central archive. This design minimizes data loss while maintaining operational efficiency and archive consistency.

<p align="center">
  <img src="figures/workflow_PRT.png" width="70%">
</p>

