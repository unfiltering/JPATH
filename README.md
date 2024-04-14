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
Converts urls into a JSON tree of their paths, super complicated since this is meant for website ripping.<br>A certain website uses a little file called files.json, which gives me the path to basically every file on that certain website, letting me clone every aspect of said website.<br>
<b>Here's an example of what it does, nonetheless.</b><br>
## Input
```
https://example.com/backup/sys/skins/w93.css.map
https://example.com/backup/sys/skins/w93.css
https://example.com/backup/files/programs/3d/index.html
https://example.com/backup/files/programs/3d/js/three.min.js
https://example.com/backup/sys/boot/screensaver.html
https://example.com/backup/sys/boot/boot.html
```
## Output
```
{
  "backup": {
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
          "index.html": 0,
          "js": {
            "three.min.js": 0
          }
        }
      }
    }
  }
}
```
Note that JPath doesn't automatically beautify JSON. (this is for downloader so you can quickly download a ton of files at once)
