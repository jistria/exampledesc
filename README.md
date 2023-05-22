# exampledesc
Reproducible example of issue experienced when using renv 0.17.3

Example code:

```R
# Install version 0.17.2 of renv.
devtools::install_version("renv", version = "0.17.2")

# Install example package.
renv::install("jistria/exampledesc")

# Attempt to open function help documentation.
?exampledesc::example_function
# Help documentation loads correctly.
```

In a new R session:

```R
# Install the latest version of renv.
install.packages("renv")

# Reinstall example package.
renv::install("jistria/exampledesc", rebuild = TRUE)

# Attempt to open function help documentation.
?exampledesc::example_function
# Error : file '<library path>/exampledesc/DESCRIPTION' is not in valid DCF format
```

Taking a look at the DESCRIPTION file in the installed package in a text editor we see that there are empty lines:
```
Package: exampledesc
Title: What the Package Does (One Line, Title Case) This Title Is

    LongerThanMost
Version: 0.0.0.9000
Authors@R: person(
 given = "First"
 , family = "Last"
 , role = c("aut", "cre")
 , email = "first.last@example.com"
 )
Description: What the package does (one paragraph).
License: MIT + file LICENSE
Encoding: UTF-8
Imports: shinydashboardPlus , data.table
RoxygenNote: 7.2.2
Author: First Last [aut, cre]
Maintainer: First Last <first.last@example.com>
Built: R 4.2.0; ; 2023-05-22 00:23:50 UTC; windows
RemoteType: github
RemoteHost: api.github.com
RemoteUsername: jistria
RemoteRepo: exampledesc
RemoteRef: main
RemoteSha: 0556c2f0552bcb466ad5ddbf303d7b6d5b7589a4
GithubHost: api.github.com
GithubRepo: exampledesc
GithubUsername: jistria
GithubRef: main
GithubSHA1: 0556c2f0552bcb466ad5ddbf303d7b6d5b7589a4
Remotes:
    github::RinteRface/shinydashboardPlus@96d01501d8b463d8624598699d93e26363ff3a76,

    github::Rdatatable/data.table

```