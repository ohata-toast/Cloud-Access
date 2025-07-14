# Policy

**Security > Cloud Access > Console User Guide > Policy**

In the **Policy** tab, you can manage:
* ACL Policies that control traffic between external agent connections and internal instances, and User Policies that apply authentication and endpoint rules to user groups.

<br>

## Managing ACL Policies

### Add

* Add policies based on Source, Destination, and Destination Port.
    * Use pre-created objects to select source, destination, and port.
* Configure options such as policy status (enabled/disabled), action (allow/deny), schedule, and logging.

![acl_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/acl_1.png)

![acl_2.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/acl_2.png)

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

### Edit

Click **Edit** to modify an existing ACL policy.

### Move

Click **Move** to reorder policies.

![move.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/move.png)

### Delete

Click **Delete** to remove an ACL policy.

### Additional Features

* Bulk Register Policies: Register multiple policies at once using a downloaded template file.
* Download Template: Download the template file required for bulk registration.
* Download All Policies: Download all ACL policies currently listed in the **ACL Policies** tab at once.

<br>

!!! tip "Note"
    * Copied ACL policies are disabled by default. Enable them using **Edit**.
    * Policies cannot be moved below the default-deny policy.

!!! danger "Caution"
    * Once an ACL policy is deleted, it cannot be recovered. Please proceed with caution when deleting.
    * The default-deny policy cannot be deleted.

<br>

## Managing User Policies

### Add

Add policies to apply to users via the agent.

![user_policy_add_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/user_policy_add_1.png)

* ➊ Enter required information:
    * User IP Range: Private IP range automatically assigned when the user connects the agent
    * Accessible IP Range: IP range of internal instances the user can access (up to 3 ranges)
* ➋ Set connection conditions:
    * OS access restrictions, password reset on first login, health check cycle
* ➌ Enable multi-factor authentication:
    * Supports up to 4 types. If all are selected, all must be verified:
        * TOTP
        * Mobile phone
        * Email
        * Biometrics
* ➍ Configure endpoint settings:
    * Block Internet: Restrict internet access after agent connection
    * Required Software: Specify required software; connection is blocked or reauthentication is required if missing
        * Supported types: Process, Registry (Windows), File Path
    * Blocked Software: Register malware or unwanted software to block connection or trigger reauthentication
        * Supported types: Process, Registry (Windows), File Path
    * Antivirus Check: Require specific antivirus software; connection is blocked or reauthentication required if missing

### Edit

Click **Edit** to modify a user policy.

### Delete

Click **Delete** to remove a user policy.

<br>

!!! tip "Note"
    * For antivirus checks, register the display name from Windows Security Center.
        * Display names can be found with PowerShell:
        * Command: Get-WmiObject -Namespace "root\SecurityCenter2" -Class AntiVirusProduct