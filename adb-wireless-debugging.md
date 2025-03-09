# How to Run ADB via USB or Wireless Debugging on Android

Follow these steps to run Android Debug Bridge (ADB) over USB or wireless debugging.

## 1. Connect USB

- Plug in your Android device to your computer via USB.

## 2. Check Phone IP

Run the following command to check the IP of your phone:

```bash
adb shell ip route
```
You will get an IP address in the output. Copy this IP.

## 3. Enable ADB over TCP/IP

Run this command to enable ADB over Wi-Fi:

```bash
adb tcpip 5555
```
## 4. Connect via Wi-Fi

Now, run the following command to connect to your phone over Wi-Fi:

```bash
adb connect <your-phone-ip>
```
Replace <your-phone-ip> with the IP you copied earlier.

#

That's it! You should now be connected to your Android device via wireless debugging.

## Important Notes:

- **Both your Android device and computer need to be connected to the same Wi-Fi network.** If they are on different networks, ADB over Wi-Fi won't work.
- **If you're facing connection issues, try restarting the ADB server** with the following commands:

```bash
  adb kill-server
 ```

```bash
  adb start-server
