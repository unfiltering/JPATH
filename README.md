# JPATH
 a library for converting urls into a path tree
# Implementation
implement this on a webpage with a textbox for awesome json path trees :D<br>
`<script src="//raw.githubusercontent.com/unfiltering/JPATH/main/jpath.js"></script>`
# Documentation
Function to generate JSON from an input, and display it in an output
```
function generateJSON() {
    let inputTextarea = document.getElementById('input');
    let outputTextarea = document.getElementById('output'); // Grab the input and output
    let text = inputTextarea.value.trim(); // Get the text
    let finalJSON = jpath.create(text); // Generate it
    outputTextarea.value = finalJSON; // Set the textboxes text to the json
}
```
# What the hell does this do?
Converts urls into a JSON tree of their paths, complicated since this is meant for website ripping.<br>A certain website uses a json file with every file's path, which understandably gives me the path to basically every file on that certain website, letting me download every file off said website.<br>
<b>Here's an example of what it does, nonetheless.</b><br>
## Input
```
https://example.com/backup/sys/skins/main.css.map
https://example.com/backup/sys/skins/main.css
https://example.com/backup/files/programs/3d/index.html
https://example.com/backup/files/programs/3d/js/three.min.js
https://example.com/backup/sys/boot/screensaver.html
https://example.com/backup/sys/boot/boot.html
https://example.com/other/images/rengae.png
https://example.com/other/images/logo.png
https://example.com/other/images/bg.png
https://example.com/other/images/bengay.png
https://example.com/other/jpath.js
https://example.com/other/jpath.py
https://example.com/other/example.html
```
## Output
```
{
  "backup": {
    "sys": {
      "skins": {
        "main.css.map": 0,
        "main.css": 0
      },
      "boot": {
        "screensaver.html": 0,
        "boot.html": 0
      }
    },
    "files": {
      "programs": {
        "3d": {
          "index.html": 0,
          "js": {
            "three.min.js": 0
          }
        }
      }
    }
  },
  "other": {
    "images": {
      "rengae.png": 0,
      "logo.png": 0,
      "bg.png": 0,
      "bengay.png": 0
    },
    "jpath.js": 0,
    "jpath.py": 0,
    "example.html": 0
  }
}
```
Note: JPath doesn't automatically beautify JSON. (this is for the downloader so you can quickly download a ton of files at once)
# The Downloader
Take that fresh json you just formatted, and use JPATH.py to quickly download every single file from 
the website you need.<br>
## How do I use it?
- You're going to have to edit the website to download the jpath from in the Python code. Its right there in the beginning, so it shouldn't be too hard to find.<br>
```
...
from colorama import Fore, Style
WEBSITE = "https://example.com" # do not include last slash
TAG = f"{Fore.BLUE}[JPATH]{Style.RESET_ALL}
...
```
- Open the python file. It's gonna ask for the JPath data, just put in the data you generated beforehand. (if you did)<br>
- After that, it's gonna ask where you want to save it. For example, the default location;
```C:\Users\*USERNAME*\AppData\Local\JPATH\JPATH_*randomNumber*```<br>
- Then all you have to do is press enter and watch it go.<br><br>
It might randomly quit for weird files, long names, etc, but if you make it download to where it was before, it will skip the ones that already exist. Just a quality of life feature, because it's a pain to download an entire site.
