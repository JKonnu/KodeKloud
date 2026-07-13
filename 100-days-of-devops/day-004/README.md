# Day 4: Script Execution Permissions

## Objective(s)

Make a script in `/tmp` on the correct application server executable.

## Skills Learned

- Linux file permission management with `chmod`
- Difference between symbolic (`+x`) and numeric (`755`) permission modes

## Steps Performed

1. Logged into App Server 3.

   ```bash
   ssh <user>@<ip>
   ```

   ![SSH login to App Server 3](screenshots/01-ssh-login.png)

2. Gave the `.sh` script execute permission:

   ```bash
   chmod +x /tmp/<script>.sh
   ```

   ![Adding execute permission](screenshots/02-chmod-x.png)

3. Set explicit `755` permissions so everyone can read/execute it while only the owner can edit it:

   ```bash
   chmod 755 /tmp/<script>.sh
   ```

   ![Setting 755 permissions](screenshots/03-chmod-755.png)

## Challenges Encountered

No significant challenges faced. The task was completed correctly on the first attempt.

## Lessons Learned

`chmod +x` only adds the execute bit on top of whatever permissions already exist. Setting an explicit mode like `755` is more predictable when you need a specific, known permission set (owner: read/write/execute, group & others: read/execute).

## Reference(s)

- [chmod(1) man page](https://man7.org/linux/man-pages/man1/chmod.1.html)
