<p align="center">
  <img src="extension/icons/icon-128.png" width="96" alt="LeetCode Sync logo">
</p>

<h1 align="center">LeetCode Sync</h1>

<p align="center">
  A Chrome extension that saves every LeetCode problem you solve to your own GitHub repo,<br>
  sorted by topic, so you always know what you've solved, what's left, and when you did it.
</p>

<p align="center">
  <a href="https://github.com/subzzzzzzzzz/LeetCode-Sync/archive/refs/heads/main.zip">
    <img src="https://img.shields.io/badge/Download-ZIP-ffa116?style=for-the-badge" alt="Download ZIP">
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="License: MIT">
  </a>
</p>

- **Every accepted solution is saved** the moment LeetCode judges it.
- **One-click import** of your whole LeetCode history, including your code.
- **Cross-device solution recovery:** Access and restore your past solutions on any laptop or browser without needing LeetCode Premium.
- **Sorted by topic:** each problem goes in a folder for its main topic (Array, String,
  Dynamic Programming, ...). SQL problems go in **Database**.
- **A dashboard README** with your totals, problems you haven't solved yet, recent activity and
  progress by month.
- **No server, no cookies to copy.** The extension runs inside your logged-in LeetCode tab and
  talks only to leetcode.com and the GitHub API.

## What you get

A repo like [subzzzzzzzzz/LeetCode-submissions](https://github.com/subzzzzzzzzz/LeetCode-submissions), filled
in automatically:

<p align="center">
  <img width="1239" height="736" alt="solutions-repo" src="https://github.com/user-attachments/assets/918e1177-5ff9-4d2d-9616-20236f77c94c" />
</p>

```
README.md                      dashboard: totals, topics, not solved yet, activity, all problems
Array/
  README.md                    every Array problem, plus ones that also use Array
  0001-two-sum/
    README.md                  status, dates, your code per language, submission history, description
    solution.cpp
Database/                      SQL problems
  0183-customers-who-never-order/
    solution.sql
.leetcode-sync/state.json      data the READMEs are built from (don't edit by hand)
```

---

## Setup (about 5 minutes)

### Step 1. Create a repo for your solutions

On GitHub, [create a new repository](https://github.com/new), for example `LeetCode-submissions`. It
can be public or private, and it can be completely empty.

### Step 2. Install the extension

Works in Chrome, Edge, Brave and other Chromium browsers.

1. **Download** this repo with the button at the top of this page
   ([Download ZIP](https://github.com/subzzzzzzzzz/LeetCode-Sync/archive/refs/heads/main.zip)),
   then unzip it. Or, if you use git:

   ```bash
   git clone https://github.com/subzzzzzzzzz/LeetCode-Sync.git
   ```

2. Open `chrome://extensions` in a new tab.
3. Turn on **Developer mode** (top right), then click **Load unpacked** (top left):

   <img width="1795" height="115" alt="load-unpacked" src="https://github.com/user-attachments/assets/a0aefb7f-0f6d-40f6-8f2e-0404c3e8c0e9" />

4. Select the **`extension`** folder inside the download.

   > Pick `LeetCode-Sync-main/extension` (or `LeetCode-Sync/extension`), not the outer folder.
   > Choosing the outer folder gives the error "Manifest file is missing or unreadable".

5. Click the puzzle-piece icon in Chrome's toolbar and pin **LeetCode Sync** so it's easy to reach.

### Step 3. Make a GitHub token

The token lets the extension save files to your solutions repo, and nothing else.

1. Open [github.com/settings/personal-access-tokens/new](https://github.com/settings/personal-access-tokens/new).
2. **Token name:** anything, for example `LeetCode-sync`.
3. **Expiration:** pick one. "No expiration" is easiest; with a date, you'll make a new token
   when it runs out.
4. **Repository access:** choose **Only select repositories**.

   <img width="1157" height="965" alt="token-step-1" src="https://github.com/user-attachments/assets/e3370728-555c-4a66-bdfa-ff836f7e5533" />

5. Open **Select repositories** and pick your solutions repo (for example `LeetCode-submissions`).
6. **Permissions:** click **+ Add permissions**, type `Contents` and tick it. Then, next to
   **Contents**, change **Access: Read-only** to **Read and write** (the box highlighted below).
   GitHub adds **Metadata: Read-only** on its own; leave it.

   <img width="887" height="847" alt="token-step-2" src="https://github.com/user-attachments/assets/c09cf6ce-2437-4879-82b3-a12f0beadda1" />

   Don't add any other permissions. The extension doesn't need them.

7. Click **Generate token**. A box pops up to confirm. It should show exactly **Contents: Read
   and write** and **Metadata: Read-only**:

   <img width="636" height="334" alt="token-step-3" src="https://github.com/user-attachments/assets/ff2dc572-9c52-4476-8c85-25c1dda55b13" />

   If it does, click **Generate token** in the box.
8. **Copy the token now** with the copy button. GitHub shows it only once; if you lose it, just
   make a new one.

   <img width="778" height="280" alt="token-step-4" src="https://github.com/user-attachments/assets/69e8be08-d70a-469e-b8fc-8926c2c1b604" />

Keep the token private: paste it only into the extension, never into chats, screenshots or code.

### Step 4. Connect the extension

Click the extension icon > **Settings** and fill in:

| Field | What to enter |
|---|---|
| GitHub username | your GitHub username, for example `subzzzzzzzzz` |
| Repository | your solutions repo, for example `LeetCode-submissions` |
| Branch | leave blank |
| GitHub token | the token you just copied |

<img width="549" height="579" alt="extension-settings" src="https://github.com/user-attachments/assets/39e385e5-6176-4c3c-af16-c71698bc59a5" />

Click **Save**, then **Test connection**. You should see "Connected to ...".

### Step 5. Import your history

Log in to [leetcode.com](https://leetcode.com), then click the extension icon > **Import full
history**. A progress message appears in the bottom-right corner of the LeetCode page. A few
hundred submissions take about 5 to 10 minutes; keep the tab open until it says it's done.

You're all set.

---

## Daily use

There's nothing to do. Solve problems as usual:

- When your solution is Accepted, a message in the corner says **Saved to GitHub**. Click it to
  see the commit.
- Solved something on your phone or another computer? The next time you open LeetCode here, the
  extension catches up on its own. You can also click **Sync now** in the popup.
- Nothing is ever saved twice. Syncing again, or clicking **Import full history** again, only adds
  what's new.

The popup shows your recent saves. If one failed (for example, you were offline), click **Retry**.

## Retrieve your code on any laptop (No Premium needed)

### The Problem
If you don't have a paid **LeetCode Premium** subscription, LeetCode does **not** sync your in-editor submission history across different machines. It only saves submissions inside the local browser memory (storage) of the exact laptop you solved them on.

When you switch to a different laptop (e.g., between work and personal computers) and open a problem you previously solved, clicking the **"Retrieve last submitted code"** button (`{}`) in the LeetCode editor shows:

> *"You haven't submitted any code"*

<p align="center">
  <img width="416" height="154" alt="retrieve-last-submitted-code" src="https://github.com/user-attachments/assets/b0a96be9-f7e7-4199-a6a3-b9898062b32e" />
</p>

### How LeetCode Sync fixes this
With **LeetCode Sync**, you don't need a Premium subscription to keep your code accessible across computers:

1. **Install the extension** on your other laptop or new browser and connect your repository in Settings.
2. Log in to [leetcode.com](https://leetcode.com).
3. Click the extension icon and click **Import full history**.

<p align="center">
  <img width="690" height="360" alt="import-full-history" src="https://github.com/user-attachments/assets/1fbe1470-df50-4842-a8dc-96c8ab44ac63" />
</p>

4. All your submission history synced to GitHub is read and synced into your browser session.
5. Whenever you revisit any problem on that laptop, click the **Retrieve last submitted code** (`{}`) button in the editor toolbar, and your previously accepted solution will load right into the editor!

## Settings

| Setting | What it does |
|---|---|
| Catch up automatically when I open LeetCode | On by default. Checks for missed submissions at most every 30 minutes. |
| Branch | Leave blank to use the repo's default branch. |

## Updating the extension

Download the new version (or `git pull`), then go to `chrome://extensions` and click the reload
icon on **LeetCode Sync**. Your settings are kept.

## Troubleshooting

| Problem | Fix |
|---|---|
| "Manifest file is missing or unreadable" | You picked the wrong folder. Select the `extension` folder. |
| **Test connection** fails with 401 | The token is wrong or expired. Make a new one. |
| **Test connection** fails with 403 | The token can't write to the repo. Check it has **Contents: Read and write** for that repo. |
| **Test connection** fails with 404 | Check the username and repo name, and that the token has access to that repo. |
| Nothing happens after submitting | Reload the LeetCode tab (tabs opened before installing don't have the extension yet). |
| "Log in to LeetCode, then sync again" | Log in on leetcode.com in this browser, then click **Sync now**. |
| Import stopped halfway | Click **Import full history** again. It skips everything already saved. |
| Where are my SQL solutions? | In the **Database** folder; that's what LeetCode calls its SQL problems. |

## Privacy

Your GitHub token is stored only in this browser's extension storage. The extension talks only to
`leetcode.com` (to read your own submissions) and `api.github.com` (to save them to your repo).

## License

This project is licensed under the [MIT License](LICENSE).

Copyright (c) 2026 Subrahmanya Bhat. All rights reserved.
