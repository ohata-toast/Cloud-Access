# Object

**Security > Cloud Access > Console User Guide > Object**

In the **Object** tab, you can manage IPs and ports used when creating ACL policies.

<br>

## Manage IP

### Add

![object_add_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/object_add_1.png)

Create an object by entering the required information.

### Modify

Click **Modify** to modify the object.

### Delete

Click **Delete** to remove the object.

### Additional Features

* Add User Object: Add objects based on registered users.
* Download Template: Download a template file for bulk registration.
* Upload Object in Batch: Use the template to register multiple objects at once.
* Download Object in Batch: Download all IP objects currently registered in the **Object** tab at once.

<br>

!!! tip "Note"
    * When creating a group object, other group objects cannot be added (only single or range objects can be selected).
    * The type cannot be changed when modifying an IP object.
    * IP objects created during Cloud Access setup cannot be modified or deleted.

!!! danger "Caution"
    * If you delete an object currently used in a policy, it will be replaced with the "ALL" object. Proceed with caution.

<br>

## Manage Port

### Add

![object_add_2.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/object_add_2.png)

Create an object by entering the required information.

### Modify

Click **Modify** to modify the object.

### Delete

Click **Delete** to remove the object.

### Additional Features

* Download Template: Download a template file for bulk registration.
* Upload Object in Batch: Use the template to register multiple port objects at once.
* Download Object in Batch: Download all port objects currently registered in the Objects tab at once.

!!! tip "Note"
    * When creating a group object, other group objects cannot be added (only single or range objects can be selected).
    * The type cannot be changed when modifying a port object.
    * Port objects created during Cloud Access setup cannot be modified or deleted.

!!! danger "Caution"
    * If you delete an object currently used in a policy, it will be replaced with the "ALL" object. Proceed with caution.