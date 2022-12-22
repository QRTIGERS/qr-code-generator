# QRTIGER - QR Code Generator

[![](/images/qr-code-generator.png)](https://github.com/QRTIGERS/qr-code-generator)

Our custom qr code generator API offers a professional solution for brands that need to have custom qr code templates with data tracking system, dynamic qr codes or qr codes in bulk and have qr codes integrated in their CRM.

## Create QR Code

**1. First login and get the API key to authorise Click My Account --> Click setting --> API key**
**2. Add this API key in every req (POST) as Authorization: Bearer API key**
**3. Generate Static custom QR code**

|Key|value|
| ------ | ------ |
| URL | /api/qr/static |
| Method | POST |
| Authorization | Bearer API KEY |
| Response | Binary Image File (PNG, SVG) |

## Request Parameter
| Key | Type | Value  | Description
|--|--|--|:--|
|qrCategory|	string|	url| qrCategory define different type of qr like url, Vcard, facebook, etc. Check below qrCategory table.|
|text|	String|	https://qrcode-tiger.com|	Your desired redirect URL will be embedded in QR|
|size|number|500|Size of the qr|
|logo|	url|	null|	Add any logo url to enable the logo at the center of QR|
|colorDark|	string|	#5e0bf0|	Color of the qr patterns|
|backgroundColor	|String	|#ffffff	|Background color of the QR. (Note: Always choose bright color for a fully scanable QR)|
|gradient|	Boolean|	false|	Set “true” to enable gradient color|
|grdType	|Number|	0 (Left-to-Right)|	Check below table for grdType
|color01	|String	|#5e0bf0	|Gradient color 1 of qr patterns|
|color02	|String|	#f30505	|Gradient color 2 of qr patterns|
|eye_color	|Boolean	|false	|Set “true” to change the eye color|
|eye_color01|	String|	#5e0bf0	|Color of outer eye|
|eye_color02|	String|	#f30505|	Color of inner eye|
|eye_outer|	String|	eyeOuter0|	Different design of outer eye, check below table for all design patterns|
|eye_inner|	String|	eyeInner0|	Different design of inner eye, check below table for all design patterns|
|qrData	|String	|pattern0	|Different design of qr data patterns, check below table for all design patterns|
|qrFormat	|String|	png|	Download binary image file type “png” or “svg”|
|transparentBkg	|Boolean	|false|	If enabled, QR code will have a transparent background|
|frame	|Number|	null|	If enabled, QR will have a frame. Check below table for frame designs|
|frameColor|	String|	null	|Frame color change the color of frame text|
|frameText|	String|	SCAN ME	|Frame text shown over QR frame|

## Example

URL --  /api/qr/static
Method -- POST
#### Parameter
```
{ 
    "size": 500,
  "colorDark": "rgb(5,64,128)",
  "logo": "scan_me.png",
  "eye_outer": "eyeOuter2",
  "eye_inner": "eyeInner1",
  "qrData": "pattern0",
  "backgroundColor": "rgb(255,255,255)",
  "transparentBkg": false,
  "qrCategory": "url",
  "text": "https://qrcode-tiger.com"
}
```
### Response
```
{
  "data": "base 64 QR image data",
  "url": "1601477992984.png"
}
```
[![](https://qrcode-tiger.com/static/img/Api/qr_example_5.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)

## grdType
|Parameter|	Type|	Value|	Description|
|-|-|-|-|
|Left - Right|	String	|linear	|Gradient flow left to right|
|Top - Bottom|	String	|upDown|	Gradient flow Top to Bottom|
|NW - SE|	String	|diagonal1|	Gradient flow Diagonally Downward|
|SW - NE|	String	|diagonal2|	Gradient flow Diagonally Upward|
|Radial|	String	|radial	|Gradient flow Radially|

## eye_outer (Default 0)
|Parameter	|Type	|Value	|Description|
|-|-|-|-|
|eye_outer|	String	|eyeOuter0|[![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter0.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)  |
| | | eyeOuter1 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter1.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | | eyeOuter2 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter2.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | | eyeOuter3 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter3.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | | eyeOuter4 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter4.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | | eyeOuter5 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter5.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | | eyeOuter6 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter6.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | | eyeOuter7 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter7.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | | eyeOuter8 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter8.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | | eyeOuter9 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeOuter/eyeOuter9.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|

## eye_inner
|Parameter|	Type|	Value|	Description|
|-|-|-|-|
|eye_inner|	String|	eyeInner0| [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner0.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) |
| | |eyeIneer1 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner1.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | |eyeIneer2 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner2.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | |eyeIneer3 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner3.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | |eyeIneer4 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner4.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | |eyeIneer5 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner5.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | |eyeIneer6 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner6.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | |eyeIneer7 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner7.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | |eyeIneer8 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner8.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| | |eyeIneer9 | [![](https://www.qrcode-tiger.com/static/img/Api/eyeInner/eyeInner9.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|

## qrData

|Parameter|	Type|	Value|	Description|
|-|-|-|-|
|qrData|	String|	pattern0|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/00.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| |	|	pattern1|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/01.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	pattern2|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/02.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	pattern3|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/03.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	pattern4|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/04.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	pattern5|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/05.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	pattern6|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/06.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	pattern7|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/07.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	pattern8|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/08.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) |
| |	|	pattern9|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/09.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) |
| |	|	pattern10|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/10.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) |
| |	|	pattern11|[![](https://media.qrtiger.com/static/img/Home/Dots/QR2/13.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 

## Frame (Default : null)

|Parameter|	Type|	Value|	Description|
|-|-|-|-|
|frame|	Number|	1|[![](https://media.qrtiger.com/static/img/Home/Frames/frame1.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png)|
| |	|	2|[![](https://media.qrtiger.com/static/img/Home/Frames/frame2.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	3|[![](https://media.qrtiger.com/static/img/Home/Frames/frame3.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	4|[![](https://media.qrtiger.com/static/img/Home/Frames/frame4.png)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	5|[![](https://media.qrtiger.com/static/img/Home/Frames/5.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	6|[![](https://media.qrtiger.com/static/img/Home/Frames/6.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	7|[![](https://media.qrtiger.com/static/img/Home/Frames/7.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	8|[![](https://media.qrtiger.com/static/img/Home/Frames/8.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	9|[![](https://media.qrtiger.com/static/img/Home/Frames/9.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	10|[![](https://media.qrtiger.com/static/img/Home/Frames/10.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|11|[![](https://media.qrtiger.com/static/img/Home/Frames/11.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	12|[![](https://media.qrtiger.com/static/img/Home/Frames/12.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	13|[![](https://media.qrtiger.com/static/img/Home/Frames/13.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	14|[![](https://media.qrtiger.com/static/img/Home/Frames/14.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 
| |	|	15|[![](https://media.qrtiger.com/static/img/Home/Frames/15.svg)](https://www.qrcode-tiger.com/static/img/Api/qr_example_5.png) | 

## Visit QRTIGER for dynamic [QR code generator](https://www.qrcode-tiger.com) and learn more about QR