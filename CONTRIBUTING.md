# Contributing to an FIH project

This is a live Frugal Innovation Hub project. You can't change it directly, but you can
**fork** it, experiment freely in your fork, and send a serious improvement back as a
**pull request**. FIH programmers review every pull request before it is merged.

## 1. Fork it

Click **Fork** at the top of this page and choose your own account. Your fork is your
playground: nothing you do there affects the original.

## 2. Experiment

Work on **branches** in your fork, not on `main`. Keep your fork's `main` identical to the
original so a clean pull request is always possible.

## 3. Send a serious change back

1. On your fork's page, click **Sync fork** so you have the latest FIH code.
2. Create a new branch from `main`, for example `fix-login-error`.
3. Put **only** the change you want to contribute on that branch.
4. Click **Contribute > Open pull request**. The pull request should go from
   `your-account/<project>` (your branch) into the FIH project's `main`.
5. Fill in the template: what, why, and how you tested it.

## 4. The FIH checks

Every pull request is checked automatically. The first time you contribute, an FIH
programmer has to approve the checks before they run. Fix anything that fails:

| Check | What it means | How to fix it |
|---|---|---|
| **Secrets** | You added a key, password or a file like `.env` or `serviceAccountKey.json` | Deleting it in a new commit is not enough, because it stays in the branch history. Close the pull request and open a new one from a fresh branch without it. Keys are shared with the team another way, never through git |
| **Clean repository** | You added `node_modules/`, a build folder, a virtual environment, or a file over 10 MB | Delete it from your branch and add the folder to `.gitignore`. These are re-created by the tools; large media and data belong somewhere else (ask FIH where) |
| **Protected files** | You changed something under `.github/` (checks, review rules, templates) | Remove that change. If you think the checks or templates should change, open an issue and explain why |
| **Code scan** | Your new code has a risky pattern (for example `eval`, SQL built from user input) | Read the message; it says which line and why. If it's a false alarm, explain it in the pull request |
| **Vulnerable libraries** | A dependency has a known security bug | Update it to the version the message suggests |
| **Build and tests** | The project doesn't build or a test fails | Run the tests locally and fix them. Add a test for your change when you can |

When all checks are green and an FIH programmer approves, they merge your pull request.
