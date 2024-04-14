# JPATH
 a library for converting urls into a path tree
# Implementation
implement this on a webpage with some textbox for awesome json formatted path trees :D<br>
`<script src="//raw.githubusercontent.com/unfiltering/JPATH/main/jpath.js"></script>`
# Documentation
Function to generate JSON from an input, and display it in an output
```
function generateJSON() {
    let inputTextarea = document.getElementById('input');
    let text = inputTextarea.value.trim();
    let finalJSON = jpath.create(text); // Use the create method from the jpath library

    let outputTextarea = document.getElementById('output');
    outputTextarea.value = finalJSON; // Set the JSON output directly

    // You can remove the console.log statement as it's not needed anymore
}
```
# What the hell does this do?
Mostly nothing, this is meant for website ripping. Specifically Windows 93 ripping.<br>Windows 93 uses a little file called files.json, which gives me the path to basically every file on windows 93.<br>Yes I made this so I can make awesome w93 things stfu
Here's an example of what it does, nonetheless.<br>
## Input
```
https://windows93.net/c/sys/skins/w93.css.map
https://windows93.net/c/sys/skins/w93.css
https://windows93.net/c/files/programs/3d/index.html
https://windows93.net/c/files/programs/3d/js/three.min.js
https://windows93.net/c/sys/boot/screensaver.html
https://windows93.net/c/sys/boot/boot.html
```
## Output
```
{
  "c": {
    "sys": {
      "skins": {
        "w93.css.map": 0,
        "w93.css": 0
      },
      "boot": {
        "screensaver.html": 0,
        "boot.html": 0
      }
    },
    "files": {
      "programs": {
        "3d": {
          "js": {
            "three.min.js": 0
          },
          "index.html": 0
        }
      }
    }
  }
}
```
Note that JPath doesn't automatically beautify JSON. (this is for downloader so you can quickly download a ton of files at once)
