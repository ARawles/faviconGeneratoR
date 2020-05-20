
<!-- README.md is generated from README.Rmd. Please edit that file -->

# faviconGeneratoR

<!-- badges: start -->

<!-- badges: end -->

The goal of faviconGeneratoR is to provide some simple wrapper functions
to the [realfavicongenerator.net](https://www.realfavicongenerator.net)
API. This allows you to create favicons for lots of different platforms
from local or online images.

## Installation

Currently, faviconGeneratoR is only available from GitHub. To install,
use the `devtools` package:

``` r
# install.packages("devtools")
devtools::install_github("ARawles/faviconGeneratoR")
```

## Example

The main function in the package is `generate_favicon()`. This function
uses a number of helper functions to build your request, send it, and
save the response:

``` r
convert_to_favicon(image = "www.this.in.an.image.com",
                   save_loc = "C:/Users/me/Downloads",
                   favicon_design = build_favicon_design(ios = ios_helper(),
                                                         windows = windows_helper(),
                                                         firefox_app = firefox_app_helper(),
                                                         android_chrome = android_chrome_helper(),
                                                         safari_pinned_tab = safari_pinned_tab_helper(),
                                                         coast = coast_helper(),
                                                         open_graph = open_graph_helper(),
                                                         yandex_browser = yandex_browser_helper())
)
```

The favicon design can be customised for lots of different platforms.
When specifying the properties for each platform, use the `*_helper()`
functions to easily provide the required parameters. To exclude a
platform, just set the parameter for that platform to `NULL`.
