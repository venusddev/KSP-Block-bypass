# KSP Brave Compatibility

KSP currently returns HTTP 403 when Brave identifies itself in the
`Sec-CH-UA` request header. This unpacked Manifest V3 extension removes the
brand-bearing User-Agent Client Hint headers only for `ksp.co.il`.

It does not read page contents, run page scripts, collect browsing history, or
modify requests to other sites.

## Install in Brave

1. Open `brave://extensions`.
2. Turn on **Developer mode**.
3. Click **Load unpacked**.
4. Select the `path\to\source code folder` folder.
5. Reload `https://ksp.co.il/web/`.

Keep this folder in place while the extension is installed. To remove the
workaround, remove **KSP Brave Compatibility** from `brave://extensions`.

## Why a filter rule is insufficient

Brave content filters can block or hide web resources and elements, but they
do not provide a user-facing rule syntax for rewriting `Sec-CH-UA`. Brave has a
built-in `brave-checks.txt` compatibility list that performs similar spoofing
for selected domains, but `ksp.co.il` is not currently listed.
