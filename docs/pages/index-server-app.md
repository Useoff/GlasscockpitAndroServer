# Introduction
This DLL (Dynamic Link Library) app is an enhancement tool to be used to support [Glasscockpit for FSX](https://play.google.com/store/apps/details?id=com.donotspeak.GlassCockpitFSX). As a server application this DLL is used to transmit flight simulation data from FSX or P3D installed on host computers to android application ( [Glasscockpit for FSX](https://play.google.com/store/apps/details?id=com.donotspeak.GlassCockpitFSX) ).

# Requirement
- **FSX / P3D.**   
Flight Simulation application on the host side computer. More information can be found at [FSX](https://en.wikipedia.org/wiki/Microsoft_Flight_Simulator_X) and [P3D](https://en.wikipedia.org/wiki/Microsoft_Flight_Simulator#P3D_-_Lockheed_Martin_Prepar3D) wikipedia.
- **Simconnect SDK on the host computer.**   
Simconnect SDK version is depend on FSX and P3D version. You can find details information from [FSX Simconnect SDK](https://www.microsoft.com/Products/Games/FSInsider/downloads/Pages/FSXSDK-SP2Update.aspx) and [P3D Simconnect SDK](https://www.prepar3d.com/support/sdk/) website
- **[Glasscockpit for FSX](https://play.google.com/store/apps/details?id=com.donotspeak.GlassCockpitFSX) installed on android device.**   
Client application aircraft cockpit devices: PFD, EICAS, ECAM, etc.

# Installation
To download DLL (Dynamic link library), please select according to your FSX od P3D SSIMCONNECT SDK requirement
- **[AndroFSXServer_V4_P3D.SIMCONNECT.X64](../../release/x64/AndroFSXServer_V4_P3D.SIMCONNECT.X64.zip)** Use this DLL (Dynamic link library) if you meet below requirement:   
   - Using P3D v4 64 bit version
   - Using Simconnect P3D V4 64 bit version
- **[AndroFSXServer_V1_FSX.SIMCONNECT.X86](../../release/x86/AndroFSXServer_V1_FSX.SIMCONNECT.X86.zip)** Use this DLL (Dynamic link library) if you meet below requirement:   
   - Using Latest FSX 32 bit version.
   - Using Latest Simconnect build for FSX.
- **[AndroFSXServer_V4_P3D.SIMCONNECT.X86](../../release/x86/AndroFSXServer_V4_P3D.SIMCONNECT.X86.zip)** Use this DLL (Dynamic link library) if you meet below requirement:   
   - Using P3D v4 32 bit version
   - Using Simconnect P3D V4 32 bit version

After downloading DLL (Dynamic link library) now you have to configure and install manually with the following way;
- Create `<AndroFSXServer>` folder in `<%USERPROFILE%>` directory.   
![UserProfilePath](../res/img/installation/UserProfilePath.png) 
- Extract, then place `<AndroFSXServer.cfg>` and `<AndroFSXServer.dll>` inside `<%USERPROFILE%\AndroFSXServer>` folder   
![InstallTarget](../res/img/installation/InstallTarget.png) 
 
# Set up
After we're finish with installation step now we have to configure server (host computer side) according to client (android side) ip address configuration.
1. On server side / host computer side. Update simulator dll.xml configuration file :
   1. **FSX** users dll.xml configuration file can be found in this path `<%USERPROFILE%\AppData\Roaming\Microsoft\FSX>`
   1. **PREPAD3D v2** users dll.xml configuration file can be found in this path `<%USERPROFILE%\AppData\Roaming\Lockhead Martin\Prepar3D v2>`
   
   In dll.xml we need to add configuration code so FSX or P3D will know where the addon dll is placed. add below code to dll.xml   
   ```
   <Launch.Addon>
     <Name>Android FSX</Name>
     <Disabled>False</Disabled>
     <ManualLoad>False</ManualLoad>
     <Path>C:\Users\<USERNAME>\AndroFSXServer\AndroFSXServer.dll</Path>
   </Launch.Addon>
   ```   
1. Update Host computer configuration.
   1. Find yours smartphone or tablet ip address. Can be found in setup page, slide left to open menu page then tab on gear icon.   
   ![AndroidConfigStatus](../res/img/set%20up/AndroidConfigStatus.jpg)
   1. Update AndroFSXServer.cfg, add smartphone or tablet ip address to AndroFSXServer.cfg   
   ![ConfigEdit](../res/img/set%20up/ConfigEdit.png)
