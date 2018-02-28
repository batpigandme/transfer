# Tidyverse Org Checklist

### Initial transfer

  * [ ] Move to tidyverse organisation.
  * [ ] Search for `hadley/` and replace with `tidyverse/`.
  * [ ] Run [styler](https://github.com/r-lib/styler) over whole package, `usethis::use_tidy_style()`.
  * [ ] Modify `.git/config`.

### travis

  * [ ] Set up travis and codecov with `usethis::use_tidy_ci()`.
  * [ ] Make sure includes:

    ```yaml
    r:
     - oldrel
     - release
     - devel
    ```

### pkgdown

  * [ ] `usethis::use_pkgdown()`.
  
  * [ ] Add template `_pkgdown.yml`.

    ```yaml
    template:
      package: tidytemplate
      default_assets: false
    ```

  * [ ] Add to `.Rbuildignore` (already done if created with usethis).

  * [ ] `pkgdown::build_site()` then push.

  * [ ] In admin use `docs/` for documentation and turn off wiki.

  * [ ] create `docs/CNAME` consisting of `{{package}}.tidyverse.org`

  * [ ] Update url on github repo page.

  * [ ] Add url to DESCRIPTION.

  * [ ] Group functions deliberately in function reference.
  
  * [ ] Add news with `usethis::use_news_md()`.

### Logo

  * [ ] Copy in hex logo (120 x 139).

  * [ ] Package name + hex logo.

    ```
    # {{package name}} <img src="logo.png" align="right" />
    ```

  * [ ] Add image + link on <http://tidyverse.org>

### `README.Rmd`

  * [ ] `usethis::use_readme_rmd()`.
  
  * [ ] Switch from `.md` to `.Rmd`.

  * [ ] Add install instructions:

    ````r
    # The easiest way to get {{package name}} is to install the whole tidyverse:
    install.packages("tidyverse")

    # Alternatively, install just readr:
     install.packages("{{package name}}")

    # Or the the development version from GitHub:
    # install.packages("devtools")
    devtools::install_github("tidyverse/{{package name}}")
    ```

  * [ ] Overview: 1-2 paragraphs including brief description/goals. Add h2, and set:

    ```yaml
    home:
     strip_header: true
    ```

  * [ ]  Link to appropriate R4DS chapter:

   ```
   If you are new to {{package name}}, the best place to start is the
   [{{relevant chapter}}](http://r4ds.had.co.nz/{{relevant-chapter}}.html) in R
   for data science.
   ```

  * [ ] Add link to `_pkgdown.yaml`

   ```yaml
     links:
     - text: Learn more
       href: http://r4ds.had.co.nz/{{relevant-chapter}}.html
   ```

  * [ ]  Usage section shows a few examples.

### Package help

  * [ ] Review package title and description in DESCRIPTION (`usethis::use_tidy_description()`).

  * [ ] Ensure that RStudio is listed as funder.

  * [ ] Add package help page.

   ```r
   #' @keywords internal
   "_PACKAGE"
   ```

  * [ ] Use markdown for docs (`usethis::use_roxygen_md()`).

  * [ ] Review topic titles. Check for trailing full stops.

### Articles

  * [ ] Ensure all vignettes have neither date, nor author.

  * [ ] Write `vignette/{{package name}}.Rmd` which expands on README (`usethis::use_vignette({{package name}})`).

  * [ ] Add direct links to navbar.

       ```yaml
       - text: Intro
         href: articles/stringr.html
       - text: RegEx
         href: articles/regular-expressions.html
       ```

  * [ ] Translate blog posts to `vignettes/releases`. Update navbar.

       ```yaml
       - text: News
         menu:
         - text: "Release notes"
         - text: "Version 1.1.0"
           href: articles/releases/stringr-1.1.0.html
         - text: "Version 1.0.0"
           href: articles/releases/stringr-1.0.0.html
         - text: "------------------"
         - text: "Change log"
           href: news/index.html
       ```

### Community

 * [ ] Add contributing guidelines, issue template, support guide, and Code of Conduct (`usethis::use_tidy_github()`).
 
 * [ ] Add text (as propmpted) re. CoC to README.
 
 * [ ] Add GitHub labels with `usethis::use_github_labels()`.
