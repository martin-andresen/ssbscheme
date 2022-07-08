# ssbscheme
Stata scheme using Statistics Norway profile

# Installation

net install ssbscheme, from("https://raw.githubusercontent.com/martin-andresen/ssbscheme/master") replace

# Fonts
Unfortunately, fonts cannot be specified inschemes, and must be set globally or manually. To set Statistics Norway fonts for the session, use

``` 
translator set Graph2pdf fontfacesans "Open Sans"
translator set Graph2pdf fontfacesymbol "Roboto Condensed Bold"

foreach type in ps eps svg window {
	graph set `type' fontfacesans "Open Sans"
	graph set `type' fontface "Open Sans"
	graph set `type' fontfacesymbol "Roboto Condensed Bold"
	}
```

If you want to change fonts permanently, consider adding the above code snippet to profile.do that runs every time you start Stata.

Make sure fonts are installed to your system.

# Use
Once installed, simply specify either ```set scheme ssbscheme``` or use the option ```scheme(ssbscheme)``` in your graph commands. 

 To use the title font Roboto Condensed Bold in a title, specify ```title({stSymbol: YOUR TITLE})```, or alternatively ```title({fontface Roboto Condensed Bold: YOUR TITLE})``` directly.

# Examples
``` 
sysuse auto, clear
twoway (lpolyci price weight) (scatter price weight), scheme(ssbscheme) title("{stSymbol:Din tittel}")

twoway 	(scatter price weight) (lfit price weight) (qfit price weight) ///
	(function y=3*x, range(2000 5000)) (function y=2000+2*x, range(2000 5000)) ///
	(function y=10000+1*x, range(2000 5000)) ///
	, scheme(ssbscheme) title("{stSymbol:Dette er en tittel}")
```

<img src=example.png>
