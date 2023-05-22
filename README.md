# exampledesc
Reproducible example of issue experienced when using renv 0.17.3

Example code:

```R
# Install version 0.17.3 of renv.
devtools::install_version("renv", version = "0.17.3")

# Install example package.
renv::install("jzistr/exampledesc")

# Attempt to open function help documentation.
?exampledesc::example_function
# Error DESCRIPTION is not in valid DCF format.
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
Imports: data.table
RoxygenNote: 7.2.2
Author: First Last [aut, cre]
Maintainer: First Last <first.last@example.com>
Built: R 4.2.0; ; 2023-05-21 23:45:57 UTC; windows
RemoteType: local
RemoteUrl: C:/Users/jzistr/workspace/delete/exampledesc

```