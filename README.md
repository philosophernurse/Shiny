# Shiny

A lightweight Shiny app for scraping Google Scholar search results and working with the output in R.

This project follows the workflow used in GSscraper and packages the core steps into a browser-based interface so users can run searches without writing the full scraping logic themselves.

## Features

- Search Google Scholar from a Shiny app
- Pause between pages to reduce the risk of IP blocking
- Collect search result metadata
- Export cleaned results for downstream analysis
- Run locally in R without needing to build a custom front end

## Installation

With R installed, run the following in the R console to install the app's dependencies. Already-installed packages are skipped:

```r
install.packages(setdiff(c(
  "shiny", "magrittr", "zip", "RCurl", "shinybusy", "purrr",
  "dplyr", "shinyjs", "shinyWidgets", "textclean", "stringi", "mgsub"
), rownames(installed.packages())))

install.packages("remotes")
remotes::install_github("hrbrmstr/cfhttr")
```

## Run the app

From the repository's project directory, start the app with:

```r
shiny::runApp()
```

## Example workflow

1. Launch the app.
2. Enter a Google Scholar query.
3. Choose the result range and pagination settings.
4. Run the scraper.
5. Review the extracted metadata.
6. Export the results to CSV or continue working with them in R.

## Reference

This project was informed by the GSscraper package and Shiny app developed by Neal Haddaway:

- https://github.com/nealhaddaway/GSscraper

## Notes

Google Scholar's site structure can change over time, so some scraping logic may need occasional updates to remain compatible with the latest page layout and anti-bot protections.
