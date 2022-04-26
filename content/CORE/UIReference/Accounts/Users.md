---
title: "Users"
weight: 20
---

{{< toc >}}

The **Users** screen lets you create and manage user accounts.

## Users List

![UIRefUsersList](/images/CORE/13.0/UIRefUsersList.png "Accounts Users List")

| Name | Description |
|------|------|
| Filter Users | Filters users by keyword. |
| COLUMNS | Lets users display/hide list columns. Username, UID, Builtin, and Full Name are default. |
| ADD | Opens the **User ID and Groups** form  |
| <i class="material-icons" aria-hidden="true" title="Settings"> | Displays/hides built-in users |
| Username | Descriptive name for the user. |
| UID | User ID number. |
| Builtin | Whether or not the user is built-in. |

## User Configuration

![UIRefUsersAdd](/images/CORE/13.0/UIRefUsersList.png "Accounts Users List")

### Identification

| Name | Description |
|------|------|
| Full Name | Descriptive name for the user. |
| Username | User login name. |
| Email | User email address. |
| Password | User login password. |
| Confirm Password | Reenter user password. |

### User ID and Groups

| Name | Description |
|------|------|
| User ID | A unique number used to identify a user. |
| New Primary Group | Creates a new group with the same name as the user. |
| Primary Group | Primary group to add the user to. |
| Auxiliary Groups | Additional groups to add the user to. |

### Directories and Permissions

| Name | Description |
|------|------|
| Home Directory | Path to the user home directory. |
| Home Directory Permissions | Default user home directory Unix permissions.  |

### Authentication

| Name | Description |
|------|------|
| SSH Public Key | Public SSH key for key-based authentication. |
| Disable Password | Enables/Disables passwrod field.  |
| Shell | The shell to use for local and SSH logins. |
| Lock User | Prevents user from logging in or using password-based services. |
| Permit Sudo | Lets user use `sudo`. |
| Microsoft Account | Allows Windows authentication methods. |
| Samba Authentication | Lets user suthenticate to Samba shares. |