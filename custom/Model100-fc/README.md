# forrcaho's custom Model 100 firmware

## Basic Remapping

I find the thumb stretch to reach the furthest thumb keys a bit uncomfortable. The default Model 100 mapping has these as shift keys, but I swapped them with the cmd (on the left) and alt (on the right) thumb keys, which I use much less frequently.

I also really missed having space available to both hands, so once I fully embraced the idea that I would be using the palm keys to shift to the function layer frequently, I made the left-hand backspace thumb key into another space key, and on the funtion layer made both space thumb keys do backspace.

I also really didn't like the vi-style mapping of the arrow keys. I rearranged these so the layout is like the way the arrow keys are typically mapped to the numpad. This also helps me remember where Home, End, Page up, and Page down are since these also match the standard numpad arrangement.

While I don't really use the numlock layer, I decided to keep it. But I was entering numlock mode by mistake too much, so I wanted to prevent that from happening accidentally. Using Macros, I made it so only control+numlock would toggle the numpad layer, and I haven't had a problem since.

## Programming Macros on the function layer

The default Model 100 layout keeps the right pinky busy, as many symbol keys used frequently in programming are on the far right.

To ameliorate this, I have a system of programming macros on the left-hand side of the keyboard. I have a system using shift and control modifiers to make variants of my macros. I came up with this on a previous keyboard where using multiple modifiers at once was easier, but I wanted to keep the basic concept:

I realized that, when programming, when I type, say, "`==`", I almost always type it with leading and trailing spaces. So, in my macro system, an unmodified keypress will type out a standard programming character sequence, and shifted will type out a variant of that sequence (where I try to make these related for easier recall) _with leading and trailing spaces_. The control key, when it is also pressed, will _suppress_ the usual leading and trailing spaces.

The keys I have programmed this way, by their macro names in the firmware code, are

- `MACRO_AND`: unshifted `&&`, shifted `&`

- `MACRO_ARROW`: unshifted `=>`, shifted `->`

- `MACRO_ENDLINE`: This one is a little different: it goes to the end of the line and adds a semicolon (or no semicolon with shift), then a newline (or no newine with control). This is the only macro I have mapped on the right side, to the semicolon.

- `MACRO_EQ`: unshifted `=`, shifted `+`.
  It seems I will have to rethink this one, since to my surpise it appears that the control modifier also gets passed to the app when I'm using it in the macro, and this combo zooms the text in or out instead of supressing the spaces :-(

- `MACRO_EQEQ`: unshifted `===`, shifted `==` (Yeah, I'm a Typescript programmer.)

- `MACRO_NEEQ`: unshifted `!==`, shifted `!=`

- `MACRO_OR`: unshifted `||`, shifted `|`

## Other stuff

I'm using Space Cadet to map my parens, brackets, and curly brackets to thumb keys. I currently don't have any other mapping for brackets or curly brackets, and I'm a bit nervous about that, but ... we'll see.

I have set up the "Heatmap" LED effect, and set the colors such that I hope it will draw less current, since I see comments in the code about not wanting to draw more than 500 mA. I don't know if I'm under that, but I'm not turning the LEDs up all the way.
