# Day 1: Linux User Setup with Non-Interactive Shell

## Objective(s)

Create a new user, `rose`, on the correct application server, ensuring the account has no interactive shell access.

## Skills Learned

- Reading a shared credentials/inventory page to identify the correct target host and user
- Creating Linux user accounts with `adduser`
- Restricting an account to a non-interactive shell for service/restricted-access accounts

## Steps Performed

1. A webpage listing all servers and their credentials was provided. Checking it showed the credentials for **App Server 2**, under user `steve`.

2. Used those credentials to SSH into App Server 2 (`stapp02`) as `steve`.

   ```bash
   ssh <user>@<ip>
   ```

   ![SSH login to stapp02](screenshots/02-ssh-login.png)

3. Created the `rose` user with `/sbin/nologin` as the shell, so the account exists but cannot be used for interactive logins.

   ```bash
   sudo adduser <user> -s /sbin/nologin
   ```

   ![Creating rose with a non-interactive shell](screenshots/03-create-nologin-user.png)

## Challenges Encountered

No significant challenges, the task was completed correctly on the first attempt once the right server and credentials were identified.

## Lessons Learned

The `-s` flag on `adduser`/`useradd` sets a user's login shell. Pointing it at `/sbin/nologin` blocks interactive shell access while still letting the account exist, the standard pattern for service or restricted accounts.

## Reference(s)

- [useradd(8) man page](https://man7.org/linux/man-pages/man8/useradd.8.html)
