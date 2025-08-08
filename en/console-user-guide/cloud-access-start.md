# Getting Started with Cloud Access

**Security > Cloud Access > Console User Guide > Getting Started with Cloud Access**

<br>

## Console Settings

After preparing the agent, configure the connection and routing settings to start using the Cloud Access service.

<br>

### Save Configuration Information

Enter and save the connection settings. Once saved, Cloud Access becomes available.

![setting_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/2025.07/setting_1.png)

* Select a VPC and subnet.
    * If you don't have a VPC or subnet, create them via the **VPC** and **Subnet** menus in the NHN Cloud console.
* Enter a customer name.
    * You can use KKorean and English letters, numbers, and some symbols (-, _, .).
* Select an encryption algorithm.
    * Supports AES-256 and ChaCha20 algorithms.

<br>

## Route Settings

Configure routing so users connected via agents can access internal instances.

### One VPC

* User IP assigned band: 10.0.0.0/24
* VPC: 172.16.0.0/12
* Subnet selected when creating Cloud Access: 172.16.0.0/24
* Accessible band: 172.16.100.0/24

When set as above, select the routing table to which the instance requiring connection belongs in **Network - Routing** and add the following rules to the **Route** tab.

* Destination CIDR: 10.0.0.0/24
* Gateway: NCAccess_INF_SUB_PORT_VIP of type Virtual_IP

### Two VPCs

* User IP assigned band: 10.0.0.0/24
* VPC1: 172.16.0.0/12
* VPC2: 192.168.0.0/16
* Subnet selected when creating Cloud Access: 172.16.0.0/24
* Accessible band: 192.168.0.0/24

When set as above, set peering between VPC1 (local) and VPC2 (peer). And select **Route** tab from **Peering Gateway - Peering** to add the local route rule.

* Destination CIDR: 10.0.0.0/24
* Gateway: NCAccess_INF_SUB_PORT_VIP of type Virtual_IP

### Other Projects

* User IP assigned band: 10.0.0.0/24
* Project 1 VPC: 172.16.0.0/12
* Project 2 VPC: 192.168.0.0/16
* Subnet selected when creating Cloud Access: 172.16.0.0/24
* Accessible band: 192.168.0.0/24

When set as above, set peering between project 1 (local) and project 2 (peer). And select **Route** tab from **[Peering Gateway - Project Peering]** to add the local route rule..

* Destination CIDR: 10.0.0.0/24
* Gateway: NCAccess_INF_SUB_PORT_VIP of type Virtual_IP

!!! danger "Caution"
    * Before saving the settings, make sure the selected VPC is connected to an internet gateway.
        * If not connected, Cloud Access will not work.
    * The user IP allocation range must not overlap with:
        * The selected subnet
        * The accessible network range

<br>

## Download the Agent

Download the agent to use Cloud Access. The service supports the following OS:

* Windows 10 1903 or later (32bit/64bit)
* Windows 11 (64bit)
* macOS 13.3 or later

| OS | Version| Download | Update date |
|--------|------|------|------|
| Windows(64bit)|1.0.0|[CloudAccess_Setup_x64](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_04c78c238ba54583bb1036b393ec6ae5/windows/installer/CloudAccess_Setup_x64.exe)|2025.08.12|
| Windows(32bit)|1.0.0|[CloudAccess_Setup_x86](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_04c78c238ba54583bb1036b393ec6ae5/windows/installer/CloudAccess_Setup_x86.exe)|2025.08.12|
|macOS|1.0.0|[CloudAccess_macOS](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_04c78c238ba54583bb1036b393ec6ae5/macos/CloudAccess%20Installer%20v0.9.0-5326.dmg)|2025.08.12|

<br>

## Add a Connection

### Add Connection

Add a connection item to access NHN Cloud resources via the agent.

![conncetion_add_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/2025.07/add_1.png)

Enter the ➊ Domain address, ➋ Customer key, and ➌ Secret key, provided by an administrator with NHN Cloud console permissions.

<br>

![conncetion_add_3.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/2025.07/add_2.png)

Click the ➍ **Validate** button. Once verified, the ➎ Customer name will be shown. Click **Add** to complete the connection.

### Delete Connection

Click a connection item to activate the **Delete Connection** button and remove the connection.

<br>

!!! tip "Note"
    * The required values for connection setup can be obtained from an administrator with NHN Cloud console permissions.
        * Once verification is completed, the customer name is automatically displayed as set by the administrator.
    * You can register multiple connections, but only one can be active at a time.

<br>

## Tunnel Connection via Authentication

Select the required connection and click **Connect** to proceed with authentication.

### Notice Settings

* Displays notices set by the administrator.  
    * Will not be shown if the option is disabled under **Settings > Notice Settings**.

### First Authentication (Account & Password)

![login_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/2025.07/6.png)

* Account Name: Enter the account received from the administrator.
* Password: Enter the temporary password sent to your registered email.

### Agree to collection and usage of personal information
* Personal information is collected to operate Cloud Access service.
    * Declining the agreement may restrict service use.

### Additional Authentication

* After the first authentication is completed, additional authentication is performed according to the policy configured by the administrator.
    * Four authentication methods are supported, as shown below.
        * Email
        * Mobile phone 
        * TOTP (time-based one-time password) 
        * Biometrics (Passkey)

### Change Initial Password

* Change the initial password.
    * Follow the password policy set by the administrator.

<br>

!!! tip "Note"
    * When an account is created, a temporary password is sent to the user’s registered email.
    * The personal information agreement is displayed only at the user's first login and is considered accepted only after a successful connection. If the process is canceled, the user must agree again.
    * The following password rules always apply, regardless of the admin’s policy:
        * 6–30 characters in length
        * Cannot be the same as the user account (ID)

<br>

## Agent Features

Overview of the agent tray icon features.

<br>

### Before Connecting to Agent
 * Open: Displays the connection screen.
 * Connect: Shows connection items.
 * Check Updates: Verifies agent version and updates if necessary.
* Version Info: Shows current version, open source licenses, and privacy policy.
 * Settings: Configure agent settings and language.
      * Cloud Environment Settings: Choose Private or Public Cloud
      * Language Settings: Korean, English, Japanese
 * Quit: Close the agent.

### After Connecting to Agent
Shows customer and account names.
* Open: Displays connection screen.
* Disconnect: Disconnects the agent.
* Notice: Displays announcements (if available).
* Version Info: Shows version and legal info.
* Quit: Close the agent.