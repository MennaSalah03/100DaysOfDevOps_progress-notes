A developer named rose has been assigned Nautilus project temporarily as a backup resource. As a temporary resource for this project, we need a temporary user for rose. It’s a good idea to create a user with an expiration date so that the user won't be able to access servers beyond that point.

Therefore, create a user named **rose** on the **App Server 1** in Stratos Datacenter. Set expiry date to **2021-01-28**. Make sure the user is created as per standard and is in lowercase.

---
This task only needs one command it's like the previous day with a different flag `e` to indicate the expiration of user
```bash
useradd -e 2021-01-28 rose
```