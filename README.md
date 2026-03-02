# scihub-paper-downloader

Given a DOI, returns the PDF download URL from Sci-Hub. That's it.

Zero dependencies. Python standard library only.

## Usage

```
python3 scihub-paper-downloader.py <DOI>
```

Returns JSON:

```json
{"doi": "10.1038/nature12373", "pdf_url": "https://...", "mirror": "https://sci-hub.st", "status": "found"}
```

`status` is `found` or `not_found`. Download the PDF with `curl -L -o paper.pdf "<pdf_url>"`.

## Install

**OpenClaw**:

```
clawhub install scihub-paper-downloader
```

**Other agents** (Claude Code, Codex, OpenCode, etc.):

Clone this repo into your skills/tools directory. The `SKILL.md` file describes the skill for your agent.
