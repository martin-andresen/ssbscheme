# ssbscheme
Stata scheme using Statistics Norway profile

#Installation

translator set Graph2pdf fontfacesans "Open Sans"
translator set Graph2pdf fontfacesymbol "Roboto Condensed Bold"

foreach type in ps eps svg window {
	graph set `type' fontfacesans "Open Sans"
	graph set `type' fontface "Open Sans"
	graph set `type' fontfacesymbol "Roboto Condensed Bold"
	}
