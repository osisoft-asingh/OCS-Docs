---
uid: streams-manage-stream-permissions
---

# Manage stream permissions

If you are assigned the **Manage Permissions** access right, then you can configure stream permissions for other user roles in your tenant. You can granularly assign individual stream permissions to each user role in your tenant.

## Prerequisites

To manage data stream permissions, your user role must be assigned the **Manage Permissions** access right.

## Manage permissions for streams

To manage permissions for a single data stream, complete the following steps:

1. From the left pane, select **Data Management** > **Sequential Data Store**.

1. Select one or more stream that you want to manage permissions for.

1. Select **Manage Permissions**.

    **Tip:** If you are only managing permissions for a single stream, select **More options** ![More options icon](../../../_icons/default/dots-vertical.svg) > **Manage Permissions** instead.

1. Use the `Manage Permissions` to edit stream permissions for each user role. For more information, see [Manage Permissions for Streams window](#manage-permissions-for-streams-window).

1. Select **Save**.

## Manage default permissions for new streams

You can edit the default user roles and permissions added to stream when it is created. Editing these default roles and permissions speeds up creation of new data streams by minimizing permission edits.

1. From the left pane, select **Data Management** > **Sequential Data Store**.

1. Select **More options** ![More options icon](../../../_icons/default/dots-vertical.svg) > **Manage Default Permissions**.

1. Use the `Manage Default Permissions` window to edit default edit stream permissions.

1. (Optional) To update all existing data streams within the namespace with your selected default settings, select **Apply to all existing streams in the Namespace**.

	**Warning!** Use of this option applies your updated permission settings to *all* streams in the namespace using a patch operation. Use this option with care, as it will overwrite existing permission settings.

1. Select **Save**.

## Manage Permissions for Streams window

Regardless of what context you are editing stream permissions, all edits are performed using the **Manage Permissions for Streams** dialog. This dialog lists a matrix of roles that have permissions for the selected streams, along with the setting for each individual each permission. Use this matrix to add new roles that have permissions for the streams or update individual permissions.

![Manage permissions](../../../communities/images/manage-permissions-for-streams.png)

### To add roles

Add roles that have permissions for the selected streams by selecting **Add Role** > **Plus** ![Plus](../../../_icons/branded/plus.svg).

<details>
	<summary><strong>Add roles</strong></summary>
	<img src="../images/manage-stream-permissions-add-roles.gif"/>
</details>

### To remove roles

Remove newly added roles by selecting the **Delete** ![Delete](../../../_icons/branded/trash-can.svg).

<details>
	<summary><strong>Remove roles</strong></summary>
	<img src="../images/manage-stream-permissions-remove-role.gif"/>
</details>

### To edit permissions

Read, write, delete, manage permissions, and share permissions can be edited for each user role that has permissions on the stream. Mouse over the **Information** ![Information](../../../_icons/default/information.svg) icon for more information about each permission.

- To allow a permission, select ![Allow](../../../_icons/custom/check-circle.svg) **Allow**.

    <details>
		<summary><strong>Allow permissions</strong></summary>
		<img src="../images/manage-stream-permissions-allow-permissions.gif"/>
	</details>

- To explicitly deny a permission, select ![Deny](../../../_icons/custom/cancel.svg) **Deny**. Permissions that have a value of `-` are equivalent ![Deny](../../../_icons/custom/cancel.svg) **Deny**.

    <details>
		<summary><strong>Deny permissions</strong></summary>
		<img src="../images/manage-stream-permissions-deny-permissions.gif"/>
	</details>

Roles that are highlighted indicate a *dirty* state—one of more of its permissions settings have been modified. You can restore the original settings by selecting Cancel.

**Dirty roles**
![Dirty roles](../images/highlighted-roles.png)

### To clear permissions for a role
    
Clear the permissions applied to a role by selecting **Backspace** ![Backspace](../../../_icons/branded/backspace.svg). 

<details>
	<summary><strong>Clear permissions</strong></summary>
	<img src="../images/manage-stream-permissions-clear-permissions.gif"/>
</details>

**Notes:**

- Allow Manage Permissions access is required on at least one role.

- Roles that have no permissions assigned will not be listed the next time that you manage stream permissions.