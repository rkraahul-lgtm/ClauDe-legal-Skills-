# Judgment and order sources (backup list if Courrt is not available)

*Used by `/rahul-legal-india:judgment-source-fallback`. Every line below was checked on 28 October 2026 from the page named in "Checked from". Websites change. If a page looks different, tell Rahul and do not guess.*

## How to read this list

- **Official** means the court or the government runs it. Prefer these.
- **Open data** means a free public copy of judgments for bulk use. It is not live. It can be weeks or months behind.
- **Third party** means a private website. Good for finding leads. Always confirm in the court's own copy before citing.
- **Captcha** means the code you type to prove you are a person. Claude must not solve or bypass it. Rahul types it.

## A. Official court portals

| Source | Address | What it gives | Notes |
|---|---|---|---|
| eCourts High Court Services | https://hcservices.ecourts.gov.in/ | Case status (by CNR, case number, FIR, party, advocate, bar registration number, Act). Court Orders and Judgments (by case number, court number, party name, order date range, neutral citation). Cause list. Caveat search. Orders and judgments open as PDF. | Pick the High Court and bench first (for Rahul: Allahabad, and the right bench). Most searches need a 6-character captcha. The CNR search page does not mention one. The page does not list which High Courts are in the menu, so check the dropdown. |
| Supreme Court of India: Judgments | https://www.sci.gov.in/judgements-case-no/ | Judgments by case number. | Official. |
| Supreme Court of India: Daily Orders | https://www.sci.gov.in/daily-order-case-no/ | Daily orders by case number. | Official. |
| Supreme Court Verdict Finder | https://verdictfinder.sci.gov.in/ | Judgment search. | Official. |
| Supreme Court Neutral Citation | https://www.sci.gov.in/neutral-citation/ | Find a judgment by neutral citation (the court's own fixed reference number). | Official. |
| Supreme Court Reports (SCR) search | https://scr.sci.gov.in/scrsearch/ | Search the digital Supreme Court Reports. | Official. |
| Supreme Court case status | https://www.sci.gov.in/case-status-diary-no/ and the pages for case number, CNR, AOR code, party name, court | Status and later orders of a case. | Captcha on the party-name page. The page needs JavaScript. |
| Supreme Court cause list | https://www.sci.gov.in/cause-list/ | Cases listed for a day. | Official. |
| Allahabad High Court: ILR and AFR page | https://www2.allahabadhighcourt.in/ilr | ILR search (https://www2.allahabadhighcourt.in/ilr/search.jsp), latest AFR judgments (AFR means Allowed for Reporting), and a list of all AFR orders. Links to Central Acts, UP Acts and High Court Rules. | Gives reported and AFR judgments, not every order. For other orders use eCourts High Court Services. I did not check the court's main website search, so verify it before relying on it. |

## B. Statute sources

| Source | Address | Notes |
|---|---|---|
| India Code (Central Acts) | https://www.indiacode.nic.in | Linked from the Allahabad High Court page. Official. |
| UP legislation | https://upvidhai.gov.in | UP Acts, linked from the Allahabad High Court page. |
| Inka `bns_lookup` | Connected tool | BNS, BNSS and BSA sections and the IPC, CrPC and Evidence Act mapping. Costs 2 credits per call on the free plan. It never cites a judgment. |

## C. Open data (free bulk copies)

| Source | Address | What it holds | How to reach it |
|---|---|---|---|
| Indian High Court Judgments | https://registry.opendata.aws/indian-high-court-judgments/ | Judgments from 25 High Courts, taken from eCourts. PDFs, JSON and Parquet metadata, and tar archives. Licence CC-BY-4.0 (you may reuse it if you give credit). Updated every quarter. Managed by Dattam Labs. The page does not say which years or which courts. | Bucket `indian-high-court-judgments`, region `ap-south-1`. No AWS account needed. Example: `aws s3 ls --no-sign-request s3://indian-high-court-judgments/` |
| Indian Supreme Court Judgments | https://registry.opendata.aws/indian-supreme-court-judgments/ | Supreme Court judgments from 1950 to 2025, in English and regional languages. Zip archives, JSON and Parquet metadata. Licence CC-BY-4.0. Updated every two months. | Bucket `indian-supreme-court-judgments`, region `ap-south-1`. No AWS account needed. Example: `aws s3 ls --no-sign-request s3://indian-supreme-court-judgments/` |

Because these copies are not live, never use them alone for a very recent judgment. Check the court's own portal.

## D. GitHub tools (Rahul runs them on his own computer; full steps and risks in `github-tools-guide.md`)

| Tool | Address | What it does | Licence and cautions |
|---|---|---|---|
| indian-supreme-court-judgments | https://github.com/vanga/indian-supreme-court-judgments | Code that downloads Supreme Court judgments from the eCourts site. README steps: install `uv`, run `uv sync`, run `source .venv/bin/activate`, then `python3 download.py`. | Data is CC-BY-4.0. The README asks users not to scrape at high speed. |
| ecourts | https://github.com/openjustice-in/ecourts | Python toolkit to fetch case information from the eCourts service, for High Courts and their benches. Aimed at journalists and researchers. | GPL-3.0-or-later (if you share changed copies, you must share the code too). Last push was about 7 months before the page was captured. Some query types are not finished. |

**Safety check on 28 October 2026 (read online only, nothing was downloaded or run):**

- **indian-supreme-court-judgments.** Read: `pyproject.toml` in full and about 1,000 of the 1,508 lines of `download.py`. Not read: the `src` folder (which holds the captcha solver), `archive_manager`, `process_metadata`, the sync scripts and the `.github` folder (GitHub blocked those pages). In what was read there was no `subprocess`, `eval`, `exec`, `pickle` or `base64`, no reading of passwords or keys, and no upload to other servers. It contacts only `scr.sci.gov.in`. S3 upload is possible but the default is local-only. Concerns: it turns off certificate checking (`verify=False`), it presents itself as Chrome on a Mac, and it solves captchas automatically. It also needs very large packages (torch, easyocr, onnx) and Python 3.13 or newer. The sync scripts can write to the real public dataset bucket if given the owner's keys. **Claude does not run `download.py`. Rahul may run it himself on a safe network, as set out in `github-tools-guide.md`. The AWS data is the safer first choice.** The repository has an `AGENTS.md` file with rules for coding assistants. They are ordinary development notes and were not followed.
- **ecourts (openjustice-in).** Read: `pyproject.toml` and the README. Dependencies are ordinary (requests, beautifulsoup4, opencv-python, click, tabulate, tqdm, html5lib). It has a `ecourts` command, standard build steps and no install hooks. The README says it is single-threaded, asks users not to hammer the site, and says users are responsible for the legal effects of running it. Not read: the Python source (GitHub blocked the folder page), so what it does with captchas and with the network is unknown. Badges point to a `captn3m0` project, but the page does not say this repository is a fork.
- **Confidence:** medium that the parts read are not harmful. The parts not read could still hold problems. A deeper check needs the code on disk in an isolated folder, with Rahul's OK.

## E. Free third-party search

| Source | Address | What it gives | Notes |
|---|---|---|---|
| Indian Kanoon | https://indiankanoon.org (premium page: https://future.indiankanoon.org/premium) | Free search of Supreme Court, High Court and tribunal judgments and orders, a few district courts (Delhi and Bengaluru), Union and State laws, Lok Sabha debates and Law Commission reports. Over 3 crore documents. | Private website, not official. Use for leads. Confirm in the court's copy before citing. Its paid Premium adds research tools and lets a user download up to 1,000 original court copies a month. |

## F. Paid databases (Rahul uses his own login)

- **SCC Online** and **Manupatra**: paid subscriptions with case law, statutes, annotations and notes. Claude cannot log in for Rahul. Rahul can paste the text or attach the PDF.

## G. What Claude can and cannot do here

- Claude can search and read public web pages with its search and fetch tools.
- The Claude workspace shell can reach only a short list of sites, so it usually cannot open court portals or the AWS buckets. If a request is refused, say so. Do not try another command to get round it.
- Claude can drive Rahul's browser (the built-in browser or Claude in Chrome) when the desktop app is open. Rahul must type any captcha.
- Rahul can download a judgment PDF and attach it. Claude reads it and cites it as `[user provided]`.
- Claude must ask before downloading any file. Say the file name, the source and the size.

## H. Order to try when Courrt is not answering

1. **Know the case?** Use the CNR, case number or neutral citation on the court's official portal (section A).
2. **Know only the topic or the names?** Search Indian Kanoon for leads (section E). Then open the court's own copy (section A) or the dataset (section C).
3. **Need many judgments?** Use the open data (section C) or the GitHub tools (section D).
4. **Need a statute?** India Code or UP legislation (section B). For BNS, BNSS and BSA, use Inka.
5. **Still nothing?** Say "nothing reliable found". Ask Rahul to attach the judgment or paste the text.

## Checked from (28 October 2026)

- eCourts High Court Services home page (hcservices.ecourts.gov.in)
- Supreme Court of India case status page (sci.gov.in) and its menu links
- Allahabad High Court ILR page (www2.allahabadhighcourt.in/ilr)
- AWS Registry of Open Data pages for the High Court and Supreme Court datasets
- GitHub README of vanga/indian-supreme-court-judgments
- ecosyste.ms project page for openjustice-in/ecourts
- Indian Kanoon Premium page
- Kanakkupillai guide to Indian case law sources (for SCC Online and Manupatra being paid)
