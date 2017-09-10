# OLED_TELEGRAM
This helps you to view your message in your OLED.. 
## Fonts

Fonts are defined in a proprietary but open format. You can create new font files by choosing from a given list
of open sourced Fonts from this web app: http://oleddisplay.squix.ch
Choose the font family, style and size, check the preview image and if you like what you see click the "Create" button. This will create the font array in a text area form where you can copy and paste it into a new or existing header file.


![FontTool](https://github.com/squix78/esp8266-oled-ssd1306/raw/master/resources/FontTool.png)
### I2C with Wire.h

```C++
#include <Wire.h>  
#include "SSD1306.h"

SSD1306  display(ADDRESS, SDA, SDC);
```
or for a SH1106:
```C++
#include <Wire.h>  
#include "SH1106.h"

SH1106  display(ADDRESS, SDA, SDC);
```
### Display Control

```C++
// Initialize the display
void init();

// Free the memory used by the display
void end();

// Cycle through the initialization
void resetDisplay(void);

// Connect again to the display through I2C
void reconnect(void);

// Turn the display on
void displayOn(void);

// Turn the display offs
void displayOff(void);

// Clear the local pixel buffer
void clear(void);

// Write the buffer to the display memory
void display(void);

// Inverted display mode
void invertDisplay(void);

// Normal display mode
void normalDisplay(void);

// Set display contrast
void setContrast(char contrast);

// Turn the display upside down
void flipScreenVertically();
```
## Text operations

``` C++
void drawString(int16_t x, int16_t y, String text);

// Draws a String with a maximum width at the given location.
// If the given String is wider than the specified width
// The text will be wrapped to the next line at a space or dash
void drawStringMaxWidth(int16_t x, int16_t y, int16_t maxLineWidth, String text);

// Returns the width of the const char* with the current
// font settings
uint16_t getStringWidth(const char* text, uint16_t length);

// Convencience method for the const char version
uint16_t getStringWidth(String text);

// Specifies relative to which anchor point
// the text is rendered. Available constants:
// TEXT_ALIGN_LEFT, TEXT_ALIGN_CENTER, TEXT_ALIGN_RIGHT, TEXT_ALIGN_CENTER_BOTH
void setTextAlignment(OLEDDISPLAY_TEXT_ALIGNMENT textAlignment);

// Sets the current font. Available default fonts
// ArialMT_Plain_10, ArialMT_Plain_16, ArialMT_Plain_24
// Or create one with the font tool at http://oleddisplay.squix.ch
void setFont(const char* fontData);
```
## Manual Installation

- Click on the `Download ZIP` button in the top right corner.
- Uncompress it.
- Rename the uncompressed folder to `OLED_TELEGRAM`.
- Place the `OLED_TELEGRAM` folder in your `<arduinosketchfolder>/libraries/` folder - you may need to create the `libraries` subfolder if it is your first library.
- Restart the IDE.
