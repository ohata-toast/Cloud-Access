
# Cloud Access Troubleshooting Guide

**Security > Cloud Access > Troubleshooting Guide**

<br>

## Connected agent, but cannot access the instance

To access the instance after logging in, please configure the following settings:

* Route Settings
    * For details, refer to [Console User Guide - Getting Started](https://docs.nhncloud.com/ko/Security/Cloud%20Access/ko/console-guide/cloud-access-start/)
* ACL Policy Settings
    * This is an access control policy applied when accessing internal instances. You must allow the IP in the **ACL Policy** tab.
* Security Groups Settings
    * You must allow the source IP in the instance's security group settings.

<br>

## I'm a Windows user, but biometric authentication is not working

Cloud Access biometric authentication is only available on devices that support fingerprint or facial recognition.
If your device does not support biometric authentication, you can set up a PIN from Account > Sign-in options and use it as an alternative.

<br>

## The user account is created, but nothing appears when clicking the Add User Object button

In the following cases, the user object will not appear in the list:

* Right after account creation, before authentication is complete
    * IP confirmation is only possible after authentication.
* If the account is created with a dynamic IP type

<br>

## Password policy is enabled, but login is possible with an invalid password

Even if the password policy is enabled and saved, it will not apply to existing users or users who have already changed their password.
The policy only applies to newly created users when the Force Initial Password Change option is enabled.
In this case, reset the password of the user account and prompt the user to use a password that complies with the policy. 

<br>

## Force Initial Password Change is enabled, but the change screen does not appear on login

This option only applies to **new user accounts created** after enabling it.
It does not apply to existing accounts even if the setting is changed afterward.
Please reset the password for the user account and proceed with the password change.

<br>

## Clicking the Link Account button shows a popup saying no activated services

If the Cloud Access service is not active, account linking is not possible.
Please activate the service before linking again or delete unnecessary connections.

<br>

## After activating services in both Pangyo and Pyeongchon regions, you cannot deactivate only one region

Currently, service deactivation is applied across all regions simultaneously.
Deactivating a specific region individually is not supported.
To use the service in only one region, deactivate the service first, then reactivate it only in the desired region.
(Support for deleting specific regions is planned for a future update.)

<br>

!!! tip "If your issue is still not resolved"
    If you followed the troubleshooting guide and your issue persists, please contact the NHN Cloud Customer Center.
    * [Go to 1:1 Online Inquiry](https://www.nhncloud.com/kr/support/inquiry?alias=tab16_15)
    * Customer Service: 1588-7967 (Business hours: Mon–Fri 10:00–19:00)