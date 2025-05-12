# SOC Home Lab

## Objective

This home lab project was designed to simulate a Security Operations Center (SOC) by generating telemetry for security analysis and creating detection and response rules for real-world attack scenarios. This project consisted of weakening a Windows 10 machine's security, generating telemtry with Sysmon, deploying the robust Command and Control (C2) tool, Sliver, and utilizing LimaCharlie to detect and respond to threats. LimaCharlie is a SecOps platform with capablities of Endpoint Detection and Response (EDR), Automated Detection and Response (ADR), telemetry storage, and more.

### Skills Learned

- d
- d

## Steps

Starting this lab, I set-up and configured a Windows 10 machine, which will be the target and host for LimaCharlie and an Ubuntu server for C2. The first step is to completey disable Windows Defender. I turned off tamper protection as well as the rest of the virus & threat protection settings, then opened up Local Group Policy Editor with the command "gpedit.msc". Here, I turned off Microsoft Defender Antivirus. 

<img src="gpedit.png" alt="Windows Defender" width="350">

Next, I ran this command in cmd to permanently disable Defender via Registry.

<img src="windef.png" alt="Windef cmd" width="500">

I then boot the system into Safe Mode to disable all Defender services before accessing the registry.

<img src="safeMode.png" alt="Safe Mode" width="350">

Once in Safe Mode, I opened up Registry Editor and went to HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services to disable these services: Sense, WdBoot, WinDefend, WdNisDrv, WdNisSvc, and WdFilter. These are disable by setting the start value to 4.

<img src="regedit.png" alt="regedit" width="350">

Now that Windows Defender is completely disabled, we can start. 

<img src="timeout.png" alt="Timeout" width="350">
