# scihub-paper-downloader

Given a DOI, returns the PDF download URL from Sci-Hub. That's it.

Zero dependencies. Standard library only.

```
python3 scihub-paper-downloader.py 10.1038/nature12373
```

```json
{"doi": "10.1038/nature12373", "pdf_url": "https://...", "mirror": "https://sci-hub.st", "status": "found"}
```

## Install

**OpenClaw** (via [ClawHub](https://clawhub.ai/aukaukauk/scihub-paper-downloader)):

```
clawhub install aukaukauk/scihub-paper-downloader
```

**Claude Code**:

```
/plugin marketplace add aukaukauk/scihub-paper-downloader
/plugin install scihub-paper-downloader@aukaukauk-scihub
```
