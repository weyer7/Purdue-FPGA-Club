# Libero Setup for Windows

Follow the steps below to set up Libero on Windows.

_Linux setup instructions can be found [here](https://ww1.microchip.com/downloads/aemDocuments/documents/FPGA/core-docs/Libero/libero/linux_setup_libero_soc_ug.pdf)._

_If you plan to use WSL, it may be necessary to use [usbipd](https://learn.microsoft.com/en-us/windows/wsl/connect-usb#attach-a-usb-device) to connect WSL with an FPGA._

## Install Libero
1. Download the latest Libero SoC **Web Installer** for Windows from the [downloads page](https://www.microchip.com/en-us/products/fpgas-and-plds/fpga-and-soc-design-tools/fpga/libero-software-later-versions#Download-Software).

2. Open the installer and proceed with the installation using the default settings.

## Request License
3. Go to [microchip.com](https://www.microchip.com) and create an account if you don't already have one.

4. On the [downloads page](https://www.microchip.com/en-us/products/fpgas-and-plds/fpga-and-soc-design-tools/fpga/libero-software-later-versions#Download-Software), under "Request Free License and Manage Licenses", click "Learn More". Or, simply open [this page](https://www.microchipdirect.com/fpga-software-products).

5. Select **“Request Free License”**.

6. Register for the **“Libero Silver 1 Yr DiskID NL License”**.
    - The license is **NL (Node Locked)**, meaning it's tied to a specific device.

7. Enter your device's **DiskID** and request the license.
   - Finding DiskID: 
     - Press Win+R and enter `cmd` to open the command prompt
     - In the command prompt, enter `Vol C:`
     - You should see your DiskID in the format XXXX-XXXX

8. After a few minutes, you will receive an email containing `License.dat`. Store it in a safe location.

## Activate License
9. Once Libero has been installed, open **Microsemi License Utility**.

10. Click **“Add License File...”** and select `License.dat`.
    - If successful, the **Microsemi License Utility** table will populate with licensing information.

## Launch Libero SoC
11. You can now open **Libero SoC** and begin using it.
