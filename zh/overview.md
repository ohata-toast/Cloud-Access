# Cloud Access Overview

**Security > Cloud Access > Overview**

Cloud Access is a service that enables secure access to NHN Cloud resources based on a Zero Trust security model.

Using a dedicated agent, users can access resources easily without complex configurations. At the same time, administrators can efficiently manage the service through the NHN Cloud console, with features such as user and continuous authentication, real-time logging, and monitoring.

<br>

## Main Features

* Customized Account Management
    * Administrators can assign customized access permissions and policies to each user. Beyond simple allow/block rules, they can define which resources a user can access, during which time frames, and from which devices.
    * Users can be grouped based on the customer’s environment, enabling consistent policy enforcement even in complex user configurations.
* Continuous Device Verification
    * When accessing resources, users’ devices are continuously verified based on defined policies — including checks for IP and MAC addresses, OS, running processes, registry settings, antivirus status, and more.
* Real-time Monitoring and Logging
    * The system collects and stores real-time activity logs such as connection attempts, authentication history, and policy violations.
        * Administrators can quickly identify who is connected to which resources and detect any anomalies.
    * Collected logs are automatically stored in NHN Cloud’s Object Storage (OBS) or integrated with the Log & Crash Search service, based on the customer’s security requirements. This supports long-term log retention, regulatory compliance, and helps customers build a more structured and secure operating environment.

    
<br>

## Configuration & how it works

The administrator set up the user policy on the policy decision point (PDP) with the NHN Cloud console. If a user attempts to access the internal resource with sign-in afterwards, it will be allowed or denied by performing the real-time policy verification with Cloud Access service, which is a policy enforcement point (PEP).

![conncetion_Architecture_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/2025.07/architecture_3.png)

!!! tip "Important"

    * Cloud Access can be configured in various ways. For details about how to configure, refer to [Console Guide - Get Started](https://docs.nhncloud.com/en/Security/Cloud%20Access/en/console-user-guide/cloud-access-start/).