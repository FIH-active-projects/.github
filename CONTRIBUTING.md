# Contributing to an FIH project

This is a live Frugal Innovation Hub project. You can't change it directly, but you can
**fork** it, experiment freely in your fork, and send a serious improvement back as a
**pull request**. FIH programmers review every pull request before it is merged.

## Quick start

1. **Fork** this repo once (the **Fork** button at the top of the page).
2. Before each new piece of work, click **Sync fork** on your fork's page.
3. Create a **new branch** from `main` and work only there. Never change `main` in your fork.
4. When the change is ready, click **Contribute > Open pull request**.
5. If FIH asks for changes or a check is red, fix it **on the same branch** and push. The pull
   request updates itself.

**One branch = one change = one pull request.** The rest of this page explains each step.

## 1. Fork it

Click **Fork** at the top of this page and choose your own account. Your fork is your
playground: nothing you do there affects the original.

## 2. Experiment

Work on **branches** in your fork, not on `main`, for example a `playground` branch for
experiments. Keep your fork's `main` identical to the original, so **Sync fork** always works
and every new branch starts from the latest FIH code.

## 3. Send a serious change back

1. On your fork's page, click **Sync fork** so you have the latest FIH code.
2. Create a new branch from `main`, for example `fix-login-error`.
3. Put **only** the change you want to contribute on that branch. If it came out of your
   experiments, copy just the finished part.
4. Click **Contribute > Open pull request**. The pull request should go from
   `your-account/<project>` (your branch) into the FIH project's `main`.
5. Fill in the template: what, why, and how you tested it.

## 4. While your pull request is open

- **Changes requested or a red check:** fix it on the same branch and push. Leave a short comment
  saying what you changed.
- **Another feature:** click **Sync fork**, create another new branch from `main`, and open a
  separate pull request. Don't touch the first pull request's branch.
- **"This branch has conflicts":** FIH changed the same lines meanwhile. Click **Resolve
  conflicts** in the pull request, or ask FIH for help in a comment.

When it's merged, you can delete the branch and click **Sync fork** to get your change into your
fork's `main`.

## 5. The FIH checks

Every pull request is checked automatically, after an FIH programmer allows the checks to run.
Fix anything that fails:

| Check | What it means | How to fix it |
|---|---|---|
| **Secrets** | You added a key, password or a file like `.env` or `serviceAccountKey.json` | Deleting it in a new commit is not enough, because it stays in the branch history. Close the pull request and open a new one from a fresh branch without it. Keys are shared with the team another way, never through git |
| **Clean repository** | You added `node_modules/`, a build folder, a virtual environment, or a file over 10 MB | Delete it from your branch and add the folder to `.gitignore`. These are re-created by the tools; large media and data belong somewhere else (ask FIH where) |
| **Protected files** | You changed something under `.github/` (checks, review rules, templates) | Remove that change. If you think the checks or templates should change, open an issue and explain why |
| **Code scan** | Your new code has a risky pattern (for example `eval`, SQL built from user input) | Read the message; it says which line and why. If it's a false alarm, explain it in the pull request |
| **Vulnerable libraries** | A dependency has a known security bug | Update it to the version the message suggests |
| **Build and tests** | The project doesn't build or a test fails | Run the tests locally and fix them. Add a test for your change when you can |

When all checks are green and an FIH programmer approves, they merge your pull request.
