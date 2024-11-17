# HtmlToPdf 

**Each html file is use for respect the perfect sizes to view entire one page in the screen with a PDF Reader**

## Format 
[Ax_FORMAT](https://www.adobe.com/fr/creativecloud/design/discover/guide-paper-sizes.html)

|Format	| Dimensions(mm) Width x Height | Dimensions(px)|
|:--:	|:--:							|:--:			|
|A0		|841 x 1189						|3179 x 4494	| 
|A1		|594 x 841						|2245 x 3179	|
|A2		|420 x 594						|1587 x 2245	|
|A3		|297 x 420						|1123 x 1587	|
|A4		|210 x 297						|794  x 1123	|
|A5		|148 x 210						|559  x 794		|
|A6		|105 x 148						|397  x 559		|
|A7		|74  x 105						|280  x 397		|
|A8		|52  x 74						|197  x 280 	|
|A9		|37  x 52						|140  x 197		|
|A10	|26  x 37						|98   x 140		|

## Use 
- `A_MM_W 	= M[Dimensions(mm)][:x]`
- `A_MM_H	= M[Dimensions(mm)][x:]`
- `A_ROTATE = {Portrait,Landscape}`
- In our case it's necessary to change the ROTATE but not the A_MM for the 
	egality between the landscape format and the portrait format.
- `wkhtmltopdf -O $A_ROTATE --page-width $A_MM_W  --page-height $A_MM_H --margin-right 0 --margin-left 0 --margin-top 0 --margin-bottom 0 --enable-local-file-access A{0,10}_format_pdf_$A_ROTATE.html file.pdf`

- Example : (CLASSIC A4 PORTAIT FORMAT)
	- `wkhtmltopdf -O Portrait --page-width 210  --page-height 297à --margin-right 0 --margin-left 0 --margin-top 0 --margin-bottom 0 --enable-local-file-access A4_format_pdf_portrait.html file.pdf`

- Example : (CLASSIC A4 LANDSCAPE FORMAT)
	- `wkhtmltopdf -O Landscaope --page-width 210  --page-height 297 --margin-right 0 --margin-left 0 --margin-top 0 --margin-bottom 0 --enable-local-file-access A4_format_pdf_landscape.html file.pdf`