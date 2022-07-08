# ssbscheme
Stata scheme using Statistics Norway profile

# Installation

net install ssbscheme, from("https://raw.githubusercontent.com/martin-andresen/ssbscheme/master")

# Fonts
Unfortunately, fonts cannot be specified in graph schemes, and must be set globally or manuall
``` 
translator set Graph2pdf fontfacesans "Open Sans"
translator set Graph2pdf fontfacesymbol "Roboto Condensed Bold"

foreach type in ps eps svg window {
	graph set `type' fontfacesans "Open Sans"
	graph set `type' fontface "Open Sans"
	graph set `type' fontfacesymbol "Roboto Condensed Bold"
	}
```
