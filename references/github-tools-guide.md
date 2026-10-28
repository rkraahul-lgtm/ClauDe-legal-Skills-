# GitHub tools guide (Rahul runs them on his own computer)

*Used by `/rahul-legal-india:judgment-source-fallback`. Written 28 October 2026. Read together with the safety note in `judgment-sources.md`.*

## Short version (Rahul's plain rule)

- **Default: do not run the tools.** Use the free AWS data and the court websites. Claude does the searching and reading.
- **Rahul does not need to know any technical steps.** If he is not comfortable with them, Claude gives no run steps. Claude offers the safe route, or suggests asking a trusted technical person to do it on a spare computer, using the safeguards below.
- **If Rahul still wants a tool,** Claude goes one small step at a time, in plain words, and stops at the first "no" or "not sure".

## Who runs what

- **Rahul runs these tools** on his own computer. This was Rahul's decision on 28 October 2026.
- **Claude does not run them.** Claude does not solve captchas or switch off security checks. Also, Claude's workspace is usually blocked from court portals.
- **Claude helps with:** explaining each step in plain words, reading the files the tool produces when Rahul attaches them, and checking the result against the court's own copy.

## Plain-word risks (read once)

1. **Certificate check is off in vanga's tool.** (A certificate check proves a website is really the one it says it is.) On public wifi or a cyber cafe, someone could swap a real judgment for a changed one. Run it only on your own home or office network. Never run it on public wifi.
2. **Captcha solving.** The court site may block your internet address if it sees too many requests. Keep the speed low. The repository itself asks users not to scrape fast. You are responsible for how you use the site.
3. **Unread code.** About 500 lines of `download.py` and the `src` folder (the captcha solver) were not read. The `ecourts` source files were not read either.
4. **Heavy install.** vanga's tool needs very large packages (torch, easyocr) and Python 3.13 or newer.
5. **Keep it separate.** Use a new, empty folder and a virtual environment (a private box for the tool's packages) so it never touches client files. Do not type passwords or AWS keys into either tool. Never give vanga's sync scripts keys: they can write to a public dataset.

## Tool 1: indian-supreme-court-judgments (vanga)

- Address: https://github.com/vanga/indian-supreme-court-judgments
- Steps from its README: install `uv`, run `uv sync`, run `source .venv/bin/activate`, run `python3 download.py`. Read its README again before you start, as steps can change.
- Output stays on your computer by default (local only). Do not turn on the S3 upload.
- You do not need this for ordinary research. The finished result of this work is already free as the AWS Supreme Court dataset (see `judgment-sources.md`, section C).

## Tool 2: ecourts (openjustice-in)

- Address: https://github.com/openjustice-in/ecourts
- Licence: GPL-3.0-or-later. If you share a changed copy, you must share the code too.
- It installs a command called `ecourts`. Follow its README for the exact commands. Claude has not tested them.
- It is for High Court and bench case information. Some query types are not finished.

## After the tool runs

- Rahul attaches the output file. Claude reads it and tags it `[GitHub tool output: file name - confirm in court copy]`.
- A tool copy can be wrong or old. Before citing, confirm in the court's own copy (eCourts or the Supreme Court website) or in the AWS dataset.
- Claude never calls a case confirmed from tool output alone.

## Safeguards (gate: Claude gives no run steps until Rahul says yes to every point)

**Before the run**
1. **Use the AWS data first.** If the AWS dataset can answer the need, do not run any tool. This is the lowest-risk route.
2. **Use a spare computer** or a separate user account on your computer. Do not use the machine that holds client files, bank logins or saved browser passwords.
3. **Back up** the computer first.
4. **Safe network only.** Your own home or office network. Never public wifi, a cyber cafe or a hotel network. This matters most for vanga's tool because it turns off the certificate check.
5. **Virtual environment only.** (A private box for the tool's packages.) Install in a new, empty folder. Never use `sudo` or "Run as administrator".
6. **No keys.** Do not set AWS keys or any password on that computer for this tool. Leave S3 upload off.
7. **Fix the version.** Write down the commit number (the version stamp) of the code you downloaded. Do not update it later without reading what changed.
8. **Antivirus on** and up to date.

**During the run**
9. **Small test first.** One short date range, one case. Slow speed. No bulk run until the test is clean.
10. **Stop at once** if the tool asks for a password, asks for admin rights, downloads anything you did not expect, opens a web page, or the court site starts blocking you.

**After the run**
11. **Open only the expected files:** PDF, JSON, Parquet, zip of PDFs. Delete anything else without opening it.
12. **Never open a file from the tool by double-clicking** an `.exe`, `.bat`, `.js`, `.vbs` or macro document.
13. **Scan the output folder** with antivirus before attaching anything to Claude.
14. **Confirm before citing.** Check each judgment against the court's own copy or the AWS dataset. This protects you from a changed or old copy.
15. **Keep a short log:** date, tool, version, what was fetched, what was checked. Save it in the output folder.

**What these safeguards cannot do**
- They lower the risk. They do not remove it. The unread parts of the code could still hold a problem.
- Nothing here fixes the switched-off certificate check inside vanga's tool. Only a safe network and checking against the court copy cover that.
- If Rahul feels the risk is too high at any point, the answer is: do not run the tool. Use the AWS data or the court portals by hand.

## Do not do

- Do not copy the tools' code into this plugin. It would mix GPL-3.0 code with the plugin's Apache-2.0 licence, and part of the code is unread.
- Do not let Claude run the tool in its cloud workspace.
