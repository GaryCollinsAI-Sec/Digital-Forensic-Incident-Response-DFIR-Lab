# Digital Forensic & Incident-Response (DFIR) Lab


<h2>Objective</h2>
<p>
The objective of this lab is to simulate a complete end-to-end cyberattack lifecycle and response within a controlled environment. By architecting a segmented network (Kali Linux, Windows 10, and SANS SIFT), I performed threat detection, live incident containment, memory acquisition, and deep-dive forensic analysis to reconstruct attacker timelines and identify Indicators of Compromise (IoCs).
</p>

<hr>

<h2>Skills Learned</h2>
<ul>
<li><strong>Environment Isolation:</strong> Configuring secure internal virtual networks for safe malware analysis.</li>
<li><strong>Incident Response (IR):</strong> Executing containment protocols and live system triage during an active breach.</li>
<li><strong>Evidence Integrity:</strong> Implementing bit-stream imaging and SHA-256 hashing for chain of custody.</li>
<li><strong>Memory Forensics:</strong> Extracting volatile data to identify malicious processes and network callbacks.</li>
<li><strong>Timeline Reconstruction:</strong> Mapping attacker activity via $MFT and Registry hive artifacts.</li>
</ul>

<hr>

<h2>Tools Used</h2>
<ul>
<li><strong>SANS SIFT:</strong> Primary forensic Linux workstation for post-mortem analysis.</li>
<li><strong>Volatility 3:</strong> Advanced framework for memory forensics and triage.</li>
<li><strong>Autopsy:</strong> Digital forensics platform for filesystem and artifact investigation.</li>
<li><strong>FTK Imager:</strong> Industry-standard disk imaging and live evidence acquisition.</li>
<li><strong>VirtualBox:</strong> Hypervisor for lab virtualization and network segmentation.</li>
</ul>

<hr>

<h2>Steps</h2>

<h3>Ref 1 – Architecture & Segmentation</h3>
<p>Deployed a segmented VirtualBox network (Kali, Windows 10, SIFT) isolated from the host and internet to ensure safe incident simulation and data integrity.</p>

<h3>Ref 2 – Attack Simulation & Detection</h3>
<p>Initiated a Metasploit reverse shell from Kali to Windows. Detected unauthorized activity including the creation of a backdoor user and a persistence mechanism via Scheduled Tasks.</p>

<h3>Ref 3 – Incident Response & Live Triage</h3>
<p>Identified the active compromise and performed "Live Response" by capturing volatile RAM via Magnet RAM Capture and performing logical disk imaging while the system was active to preserve the state of the breach.</p>

<h3>Ref 4 – Memory Analysis & Containment</h3>
<p>Used Volatility 3 within SIFT to analyze the RAM dump, successfully identifying the attacker's IP, malicious PIDs, and the command-line history used to escalate privileges.</p>

<h3>Ref 5 – Post-Mortem Forensic Investigation</h3>
<p>Utilized Autopsy to parse the $MFT and Registry hives, reconstructing a minute-by-minute timeline of the attacker's file modifications and account creation to finalize the forensic report.</p>
