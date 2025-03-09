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
```

# others

## Prerequisites
- Mention any prerequisites for wireless debugging to work, such as enabling developer options on the device and enabling USB debugging.
- **Developer options** must be enabled on your Android device.
    - Go to **Settings > About phone** and tap **Build number** seven times to enable Developer Options.
    - Go to **Settings > System > Developer options** and enable **USB debugging**.
- Ensure **ADB** is installed on your computer. You can check by running:
  
```bash
  adb version
```

If ADB isn't installed, follow the installation guide for your platform [here](https://developer.android.com/studio/command-line/adb).

### **Troubleshooting Tips**  
   - Add common troubleshooting tips for wireless debugging issues.

```markdown
## Troubleshooting

Here are some common troubleshooting steps in case you face issues:

- **Issue**: `adb connect <your-phone-ip>` fails to connect.
  - **Solution**: Ensure that both the Android device and your computer are on the **same Wi-Fi network**.
  - **Solution**: Check that your phone's IP address is correct by running `adb shell ip route` again.
  
- **Issue**: `adb tcpip 5555` doesn't work after disconnecting the USB.
  - **Solution**: Reconnect your phone via USB, and re-run `adb tcpip 5555`.

- **Issue**: ADB commands are not responsive.
  - **Solution**: Try restarting the ADB server:

  ```bash
    adb kill-server
  ```

  ```bash
    adb start-server
  ```

- **Issue**: Your device is still showing as offline.
- **Solution**: Restart both your computer and the Android device, and reconnect using the USB cable first, then try `adb tcpip 5555` again.

## Stop Wireless Debugging (Optional)
- A section explaining how to stop wireless debugging when done.

## Stop Wireless Debugging (Optional)

If you no longer need wireless debugging, you can disable it by running:

```bash
adb usb
```

This will switch ADB back to USB mode, and your device will no longer be accessible via Wi-Fi.


### **Security Considerations**
   - **Warning**: Since you're opening up ADB over Wi-Fi, it's important to understand the security risks.
   
## Security Considerations

When using ADB over Wi-Fi, ensure that you're connected to a trusted network. Do not leave ADB over Wi-Fi enabled when you're not actively using it, as it can be a security risk if your device becomes accessible over public networks.

## Enable ADB Wireless Debugging Automatically
- If a user wants to set up ADB wireless debugging permanently, you could explain how to make this process easier using Startup Scripts.

## Enable ADB Wireless Debugging Automatically (Optional)

If you want your device to automatically connect over Wi-Fi whenever ADB starts, you can write a simple script that runs the following commands when your computer starts:

```bash
adb connect <your-phone-ip>
```
This can be added to your startup scripts for macOS, Linux, or Windows to enable the connection automatically each time you log in.

- On macOS/Linux, add the command to your ~/.bash_profile or ~/.bashrc.
- On Windows, add the command to the Startup folder or use Task Scheduler to run it automatically.


### **Alternative Method for Wireless Debugging**  
   - If USB debugging is not working, some devices support **Wi-Fi Direct** to enable ADB over a local network, and you could explain how to enable this, if applicable.

## Alternative Method for Wireless Debugging

Some Android devices support **Wi-Fi Direct**, which can allow direct communication between the device and your computer without the need for a Wi-Fi network. To enable this:

1. Open your **Wi-Fi settings** on the Android device and enable **Wi-Fi Direct**.
2. On your computer, you can directly connect to the device's **Wi-Fi Direct** network, then use ADB as usual.

Note: This method may not be available on all devices and could require additional setup or software.

## Link to Official Documentation
- Provide a link to the official Android developer documentation for ADB, in case users need further details.

## Additional Resources

For more detailed information on ADB and wireless debugging, check the official Android documentation:

- [Android Debug Bridge (ADB)](https://developer.android.com/studio/command-line/adb)
- [Wireless Debugging Setup](https://developer.android.com/studio/command-line/adb#wireless)




