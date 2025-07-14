# Objects

**Security > Cloud Access > Console User Guide > Objects**

In the **Objects** tab, you can manage IPs and ports used when creating ACL policies.

<br>

## Manage IP Objects

### Add

![object_add_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/object_add_1.png)

Create an object by entering the required information.

### Edit

Click **Edit** to modify the object.

### Delete

Click Delete to remove the object.

### Additional Features

* Add User Object: Add objects based on registered users.
* Download Template: Download a template file for bulk registration.
* Bulk Object Registration: Use the template to register multiple objects at once.
* Download All Objects: Download all IP objects currently registered in the Objects tab at once.

<br>

!!! tip "Note"
    * When creating a group object, other group objects cannot be added (only single or range objects can be selected).
    * The type of an IP object cannot be changed after creation.
    * IP objects created during the initial Cloud Access setup cannot be edited or deleted.

!!! danger "Caution"
    * If you delete an object currently used in a policy, it will be replaced with the "ALL" object. Please proceed with caution.

<br>

## Manage Port Objects

### Add

![object_add_2.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/object_add_2.png)

Create an object by entering the required information.

### Edit

Click **Edit** to modify the object.

### Delete

Click **Delete** to remove the object.

### Additional Features

* Download Template: Download a template file for bulk registration.
* Bulk Object Registration: Use the template to register multiple port objects at once.
* Download All Objects: Download all port objects currently registered in the Objects tab at once.

!!! tip "Note"
    * When creating a group object, other group objects cannot be added (only single or range objects can be selected).
    * The type of a port object cannot be changed after creation.
    * Port objects created during the initial Cloud Access setup cannot be edited or deleted.

!!! danger "Caution"
    * If you delete an object currently used in a policy, it will be replaced with the "ALL" object. Please proceed with caution.