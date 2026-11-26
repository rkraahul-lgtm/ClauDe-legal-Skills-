# rahul-legal-india


> **Licence.** Apache License 2.0 (see `LICENSE`). Built from Anthropic's `claude-for-legal` repository (see `LICENSE-NOTICE.md`), rewritten for Indian law. The skill `skills/dpdp-analyze` is by Mayank Dsouza under the MIT licence (see `skills/dpdp-analyze/LICENSE-MIT.txt`). This is a draft-help tool for an advocate. It is not legal advice.
A custom plugin for Rahul Kumar, built from Anthropic's open `claude-for-legal` repo (Apache-2.0) and rewritten for Indian law and Rahul's own rules.

## The main promise

- It asks before it acts. It does not assume.
- It never uses a case that did not come from a real source (the Courrt tool, or text Rahul pasted). Every case comes with name, court, year, citation and a link.
- It quotes a section only from a retrieved source. Otherwise it says `[section text not retrieved - verify]`.
- Everything is a draft for Rahul to check. It saves to `D:/Temp/Output`, asks before overwriting, and never deletes.

## Install

**Claude (Cowork / desktop app):** open Customize, then Plugins, and upload `rahul-legal-india.zip`.

**Claude Code:**
