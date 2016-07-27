# Layers

Farnsworth has two "layers"

* Front
* Back


Farnsworth's display is composed of layers, these are represented with the `Layer` class,  all layers implement the following functions

*   `is_dirty()` - Return true if the layer has changed since it was last drawn
*   `blank(rgb_color=(0,0,0))`- Clear the layer, setting all pixels to the given color, or black if no color is given
*   `get_pixel(x,y)` - Return the value (triplet) of a speicifed pixel, `None` if no such pixel exists
*   `read_pixel(x,y)` - Identical to `get_pixel`;
*   `set_pixel(x,y,rgb_color)` - Sets a specified pixel to a specified color
*   `in_bounds(x,y)` - Returns true if the position x,y is in bounds of the layer
*   `paint_box(left,top,right,bottom,rgb_color)` - Fills a box with the specified color
*   `translate_color(color)` - Translates a color from RGB to hardware arrangement defined by configuration
*   `load_from_filename(filename,scalex,scaley,parentColor)` - Load a file (specified by name) into the layer, with optional scaling and background colors
*   `load_from_image(image, saclex, scaley, parentColor)` - Load an image (?? type ??) into a layer, witih optional scaling and background color
*   `blit_image(filename, x, y)` - Blit an image from file onto the layer at specified position
*   `serialized_data()` - return an 1d array containg all pixels, called to send data to parent process, clears dirty flage **DO NOT USE in user programs**
*   `blit(dest,x,y,parentBlack)` - Blit this layer onto another layer
*   `glyph_width(font_name, glyph)` - Return the length of  the specified glyph in the specified font
*   `render_glyph(x,y,font,glyph, rgb_color)` - Render the specified glyph at a specific offest in a specific color
*   `measure_string(font,string,space_len)` - return the lenght (in pixels) of the specified string with option lenght of space (default one)
*   `render_string(x,y,font,string,color,bgcolor,spacewidth)` - render a string
*   `scroll_string(font,string,rgb_color,y,rate)` - Scroll a string across the while witdh of the display (called every frame)
*   `render_twoline_string(string1,font1,color1,string2,font2,color2)` - Render two strings, with specified fonts and colors
