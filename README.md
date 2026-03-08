# scihub-paper-downloader

Resolve a DOI to a direct PDF URL through the current `Sci-Hub -> Sci-Net` flow.

Zero dependencies. Python standard library only.

## Usage

```bash
python3 scihub-paper-downloader.py <DOI>
```

Output:

- success: prints only the final PDF URL
- invalid input: prints only `INVALID_INPUT`
- paper unavailable: prints only `NOT_FOUND`
- mirror or anti-bot failure: prints only `MIRROR_ERROR`

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
- PDF verification before returning a link

## Notes

- By default the script tries `sci-hub.st`, `sci-hub.ru`, and `sci-hub.se`.
- Override mirrors with `SCIHUB_MIRRORS`, using a comma-separated list.

Example:

```bash
SCIHUB_MIRRORS="https://sci-hub.st,https://sci-hub.ru" python3 scihub-paper-downloader.py 10.1038/s41586-020-2649-2
```
