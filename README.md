# JPATH
 a library for converting urls into a path tree
# Implementation
implement this on a webpage with some textbox for awesome json formatted path trees :D
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
