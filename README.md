# Credits

A collection of tools, examples and anything else necessary to handle the Credits information in a Jupyter Book. This project is driven by the need to automate and customize the way metadata is expressed in the book itself, the repository and with third party tools and websites. Development is (initially) driven by the MUDE Textbook use case.

- Metadata is summarized in a `_credits.yml` file.
- Content in the book is automatically generated (e.g., the formatted text to be inserted into specific pages)
- Pages should be automatically updated with generated content in a user-friendly and Git-aware way

The code in this repository will eventually be integrated with other TeachBooks tools for general use(e.g., into the teachbooks package or a sphinx extension.

This repository was created with files from a branch of the MUDE Textbook (see [PR #42](https://github.com/TUDelft-MUDE/book/pull/42)), which was deleted after the 2024 version of the book was completed. The only code transferred from the book repo was in `./book/credits/`. Otherwise, use the 2024 or 2025 version of the book to find examples for how the citations should render (e.g., `_credits.yml`, content pages and `credits.md`).


During finalization of the 2024 version of the book, comments in contents files (e.g., credits.md, pages, etc) were used to keep track of the credits work and future dev:

- `% <START|END>-CREDITS` for attribution blocks on content pages
- `source: <source>` key in `_credits.yml` is used to find things easily
- `% CREDIT-NOTE` used for arbitrary notes

In other words: use the items above during text searches to find where pages should be modified.

This is a rough template for how the credits page was set up. It could be useful for templating contents of book pages:

```
(generic_credit)=
### `<resource_type>`: `<title>`
% CREDIT-NOTE: note that the title ref is not included because
%   the tag is displayed in the rhs toc.
% Future dev may use templating to automatically include the
%   right text in these sections

> `<title>` is written by `<authors>`.
> 
> Special thanks goes to `<name>`, who `<contribution>`.
>
> _or_
>
> Special thanks goes to:
> - `<name>`, who `<contribution>`
> - `<name>`, who `<contribution>`.
>
> Note: `<note-public>`
>
> The following resources are used in this `<resource_type>` but are _not_ included under the CC BY license of this book and cannot be reused without explicit permission from the original copyright holder:
> - `resource_type>` `<resource>` is used in `<page>` (not modified). Original content licensed under `<license>`.
> - `resource_type>` `<resource>` is used in `<page>` and `<modification>`. Original content licensed under `<license>`.
> - `resource_type>` `<resource>` (`<bibtex>`) is used in `<page>` (unmodified). Original content licensed under `<license>` and is available `<resource_location>`.
> - ...
> 
```