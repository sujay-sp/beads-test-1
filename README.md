This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Beads (bd) Issue Tracking

This project uses **bd** (beads) for issue tracking. The initial setup included: running `bd init`, creating two tasks, adding the bd remote origin, and running `bd dolt push` to sync the Dolt database to GitHub.

### Restoring tasks after a fresh clone

Delete the codebase locally and clone again, restore your tasks from the remote as follows:

1. **Clone the repo**

   ```bash
   git clone https://github.com/sujay-sp/beads-test-1.git
   cd beads-test-1
   ```

2. **Confirm the Dolt data exists on GitHub**

   ```bash
   git ls-remote origin 'refs/dolt/*'
   ```

3. **Create the local Dolt storage folder**

   ```bash
   mkdir -p .beads/dolt
   ```

4. **Clone the Dolt database from GitHub** into the exact DB name Beads expects

   ```bash
   dolt clone git+https://github.com/sujay-sp/beads-test-1.git .beads/dolt/beads_test_1
   ```

5. **Start the Beads Dolt server**

   ```bash
   bd dolt start
   ```

6. **Verify tasks are present**

   ```bash
   bd list
   ```
