# Tools Setup for the Mini Cooper
---
1. Create an XP Virtual Machine.
    - Follow the [Instructuctions Here](virtualBox.md#virtual-box-windowsxp-mode).
2. Download the gectko tools to the VM
    - Link to the GTecko distro: https://www.northamericanmotoring.com/forums/electrical/205937-ncsexpert-for-beginners.html
    - Install 7zip.
        - It's a dumb ass .rar file.
3. Follow all of the instructions in the two .pdf files.
    - Things I missed:
        - Grab the LADEN.BAT file from the R56 source Daten folder and put it in the R50 folder.
        - Run LADEN.BAT file in C:/NCSEXPERT/DATDEN/R50
        - Move the REVTOR.PFL profile to the C:/NCSEXPERT/PFL
        - Set my DCAN-K cable switch to the left
        - Create and empty FSW_PSW.MAN file.
        - Move the existing FSW_PSW.TRC file to an old file.
4. Download Revtor's NCSDummy.
    - https://www.bimmerforums.com/forum/showthread.php?1553779-NCS-Dummy-Taking-the-expert-out-of-NCS-Expert
    - The tools needs Microsoft .NET Framework 3.5 svc pack 1. So, grab the one that can install offline.
        - https://www.microsoft.com/en-us/download/confirmation.aspx?id=25150


