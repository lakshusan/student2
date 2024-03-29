---
toc: false
comments: true
layout: post
title: Color Generator
description: Color Generator
courses: {compsci: {week: 14}}
type: tangibles
---


# Color Generator

- Input decimal values 0-255 in each box
- Code validates RGB values
- Converts RGB decimal to binary
- Displays converted RGB values in binary
- Displays final color

## Input and Result

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Color Generator</title>
    <style>
        #result {
            margin-top: 20px;
            width: 200px;
            height: 200px;
            border: 1px solid #000;
        }
        #colorText {
            margin-top: 10px;
        }
    </style>
    <script>
        function translateColor(event) {
            event.preventDefault();
            // get input values
            var redValue = document.getElementById("redValue").value;
            var greenValue = document.getElementById("greenValue").value;
            var blueValue = document.getElementById("blueValue").value;
            // validate input values (must be between 0 and 255)
            if (!isValidInput(redValue) || !isValidInput(greenValue) || !isValidInput(blueValue)) {
                alert("Please enter valid numbers between 0 and 255.");
                return;
            }
            // convert inputs to binary
            var redBinary = decimalToBinary(redValue);
            var greenBinary = decimalToBinary(greenValue);
            var blueBinary = decimalToBinary(blueValue);
            // display binary output
            document.getElementById("colorText").innerHTML = `
                <p>Red: ${redBinary}</p>
                <p>Green: ${greenBinary}</p>
                <p>Blue: ${blueBinary}</p>
            `;
            // calculate the final color
            var finalColor = "rgb(" + redValue + "," + greenValue + "," + blueValue + ")";
            // display the final color
            document.getElementById("result").style.backgroundColor = finalColor;
        }
        function decimalToBinary(decimalValue) {
            return parseInt(decimalValue).toString(2);
        }
        function isValidInput(value) {
            return !isNaN(value) && parseInt(value) >= 0 && parseInt(value) <= 255;
        }
    </script>
</head>
<body>
    <form onsubmit="translateColor(event)">
        <label for="redValue">Number 0-255 for Red</label><br>
        <input type="number" id="redValue" name="redValue" required><br>
        <label for="greenValue">Number 0-255 for Green</label><br>
        <input type="number" id="greenValue" name="greenValue" required><br>
        <label for="blueValue">Number 0-255 for Blue</label><br>
        <input type="number" id="blueValue" name="blueValue" required><br>
        <input type="submit" value="Submit">
    </form>
    <div id="result"></div>
    <div id="colorText"></div>
</body>
</html>


## Ideation Diagram

<img src = "https://media.discordapp.net/attachments/1174540464951676969/1174591418451369994/image.png?ex=65682681&is=6555b181&hm=10da97d668d2ce6c0e1dea11fd5e9fd743ab5dacc88778b282c5017d15aa1c79&=&width=1333&height=993">


## Final Diagram

<img src = "https://media.discordapp.net/attachments/796087225535168512/1182042253544390677/image.png?ex=658341a2&is=6570cca2&hm=b9f88c35b358da82ba5c602f1066a93376ce8719f7de9bb61972c69f27a1e644&=&format=webp&quality=lossless&width=1189&height=993">



## Key Commits

- <a href="https://github.com/trevorhuang1/cpt_warmup/commit/8bf1214933ef5cbe29572b1d4caa4a233b67532a">input-based js color generator</a>
- <a href="https://github.com/trevorhuang1/cpt_warmup/commit/e7fc72d08a77e54c11d55395bd2c14881b9efd5c">color result separate</a>
- <a href="https://github.com/trevorhuang1/cpt_warmup/commit/a9aa10d3a696960b662604dc98f4ea624c7f5fe5">sample color input</a>


