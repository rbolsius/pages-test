# GitHub - deathau/markdownload

[deathau/markdownload](https://github.com/deathau/markdownload) is a Firefox
and Google Chrome extension to clip websites and download them into a readable
markdown file.

> ## 3.1.0
> 
>   - Firefox for Android (nightly) support
>   - Updated Readability and Turndown
>   - Added GitHub-flavoured Markdown (GFM) plugin to Turndown (adds some mardown table support)
>   - Added support for MathJax -> LaTeX (thanks @LeLocTai)
>   - Disallow slashes in title text replacements
>   - Suport for Open Graph meta tags as variables (which use `property` instead of `key`)
>   - Fixed an issue with regex characters like `|` in date formats
>   - Resolved an extra slash in file name causing images to fail to download in chromium browsers
>   - Added some support to parse pre elements as code blocks (supports syntax highlighting on GitHub, but not much else yet)
>   - Added option to enable or disable the context menus
>   - Added some extra keyboard shortcuts. These can be customised, depending on your browser
>       - Alt+Shift+M opens the popup (as it has in previous versions)
>       - Alt+Shift+D downloads the current tab as markdown, bypassing the popup
>       - Alt+Shift+C copies the current tab as markdown to the clipboard, bypassing the popup
>       - Alt+Shift+L copies the current tabs URL as a markdown link to the clipboard

## 3.1.0

  - Firefox for Android (nightly) support
  - Updated Readability and Turndown
  - Added GitHub-flavoured Markdown (GFM) plugin to Turndown (adds some mardown table support)
  - Added support for MathJax -> LaTeX (thanks @LeLocTai)
  - Disallow slashes in title text replacements
  - Suport for Open Graph meta tags as variables (which use `property` instead of `key`)
  - Fixed an issue with regex characters like `|` in date formats
  - Resolved an extra slash in file name causing images to fail to download in chromium browsers
  - Added some support to parse pre elements as code blocks (supports syntax highlighting on GitHub, but not much else yet)
  - Added option to enable or disable the context menus
  - Added some extra keyboard shortcuts. These can be customised, depending on your browser
      - `Alt+Shift+M` opens the popup (as it has in previous versions)
      - `Alt+Shift+D` downloads the current tab as markdown, bypassing the popup
      - `Alt+Shift+C` copies the current tab as markdown to the clipboard, bypassing the popup
      - `Alt+Shift+L` copies the current tabs URL as a markdown link to the clipboard
  - Added support for template variables having different casing using `:` followed by the casing type. For example, for an article titled "Different Types of Casing":
      - `{pageTitle:pascal}` — "DifferentTypesOfCasing"
      - `{pageTitle:camel}` — "differentTypesOfCasing"
      - `{pageTitle:kebab}` — "different-types-of-casing"
      - `{pageTitle:snake` — "different\_types\_of\_casing"
