# scihub-paper-downloader

Resolve a DOI to a direct PDF URL through the current `Sci-Hub -> Sci-Net` flow.

Zero dependencies. Python standard library only.

## Usage

```bash
python3 scihub-paper-downloader.py <DOI>
```

## Install

For Claude Code, Codex, OpenCode, and other tools using the skills CLI:

```bash
npx skills add aukaukauk/scihub-paper-downloader
```

For OpenClaw via ClawHub:

```bash
clawhub install scihub-paper-downloader
```

Output:

- success: prints only the final PDF URL
- invalid input: prints only `INVALID_INPUT`
- paper unavailable: prints `NOT_FOUND`
- if the Sci-Hub not-found page includes an OA link, the script prints `OA_LINK <url>` on the next line
- upstream resolution inconclusive: prints only `MIRROR_ERROR`

Examples:

```bash
python3 scihub-paper-downloader.py 10.1038/s41586-020-2649-2
python3 scihub-paper-downloader.py 10.1145/3641289
```

## What It Handles

- DOI normalization
- Sci-Hub mirror retries
- ALTCHA verification when Sci-Hub shows the anti-bot page
- redirects from Sci-Hub to Sci-Net
- extraction of OA links that Sci-Hub itself shows on not-found pages
- PDF verification before returning a link

## Notes

- By default the script tries `sci-hub.st`, `sci-hub.ru`, and `sci-hub.se`.
- Override mirrors with `SCIHUB_MIRRORS`, using a comma-separated list.

Example:

```bash
SCIHUB_MIRRORS="https://sci-hub.st,https://sci-hub.ru" python3 scihub-paper-downloader.py 10.1038/s41586-020-2649-2
```
