# Policy

**Security > Cloud Access > Console User Guide > Policy**

In the **Policy** tab, you can manage ACL policies, which control traffic between externally connected agents and internal instances, and user policies, which apply policies such as authentication and endpoint settings to agents by group.

<br>

## Manage ACL Policies

### Add

* Add policies based on Source, Destination, and Destination Port.
    * Use pre-created objects to select source, destination, and destination port.
* Configure options such as policy status (enabled/disabled), action (allow/deny), schedule, and logging.

![acl_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/2025.07/10.png)

![acl_2.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/2025.07/8.png)

![acl_3.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/2025.07/9.png)

* ➊ Enter a policy name and configure the following:
    * Status: Enable or disable the policy
    * Action: Allow or Deny
    * Schedule: Time zone during which the policy is applied
    * Logging: Enable or disable log collection
* ➋ Select source and destination objects.
    * If no object exists, click **Add Object** to create a new one.
* ➌ Select a port object to allow or deny access.
    * If none exists, click **Add Object** to create one.

### Copy

* Click **Copy** to duplicate an ACL policy.
    * The copied policy is shown in a disabled state.

### Modify

Click **Modify** to modify an existing ACL policy.

### Move

Click **Move** to reorder policies.

![move.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/move.png)

### Delete

Click **Delete** to remove an ACL policy.

### Additional Features

* Upload Policy in Batch: Register multiple policies at once using a downloaded template file.
* Download Template: Download the template file required for bulk registration.
* Download Policy in Batch Download all ACL policies currently listed in the **ACL Policy** tab at once.

<br>

!!! tip "Note"
    * Copied ACL policies are disabled by default. Enable them using **Modify**.
    * Policies cannot be moved below the default-deny policy.

!!! danger "Caution"
    * Once an ACL policy is deleted, it cannot be recovered. Please proceed with caution when deleting.
    * The default-deny policy cannot be deleted.

<br>

## Manage User Policies

### Add

Add policies to apply to users via the agent.

![user_policy_add_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/user_policy_add_1.png)

* ➊ Enter required information:
    * User’ IP allocation range: Private IP range automatically assigned when the user connects the agent
    * Accessible IP Range: IP range of internal instances the user can access
        * (up to 3 ranges allowed)
* ➋ Set connection conditions:
    * You can configure the allowed operating systems, password reset on first login, and set the health check cycle.
* ➌ Set multi-factor authentication:
    * Supports up to 4 types. If all are selected, all must be verified:
        * TOTP
        * Mobile phone
        * Email
        * Biometrics
* ➍ Configure endpoint setting policies:
    * Block Internet: Restrict internet access after agent connection
    * Required Software: You can specify software that users must have installed. If the required program is not found, the connection will be blocked or reauthentication will be triggered.
        * Registration methods: Process, Registry (Windows), File Path
    * Blocked Software: You can register malware or unwanted software to block connection. If the required program is found, the connection will be blocked or reauthentication will be triggered.
        * Registration methods: Process, Registry (Windows), File Path
    * Antivirus Check: You can specify an antivirus program. Devices without the specified antivirus installed will be blocked from connecting or required to reauthenticate.

### Modify

Click **Modify** to modify a user policy.

### Delete

Click **Delete** to remove a user policy.

<br>

!!! tip "Note"
    * For antivirus checks, register the display name from Windows Security Center.
        * Display names can be found with PowerShell:
        * Command: Get-WmiObject -Namespace "root\SecurityCenter2" -Class AntiVirusProduct