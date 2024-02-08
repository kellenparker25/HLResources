# Leap Motion Controller 1
Leap Motion Controller is a hand-tracking system designed to be placed on a physical desktop or mounted to VR headset.

In 2019 Leap Motion and Ultrahaptics merged to form Ultraleap. Leap Motion Controller is the older model now only supported by Windows machines. 
[Ultraleap's Leap Motion 2 is the latest model](https://leap2.ultraleap.com/)
## Setup
1. Use a Windows 7+ machine
2. [Create an account or login to Ultraleap](https://leap2.ultraleap.com/account-register/)
4. Download [Legacy Orion 4.1 Handtracking Software](https://staging.corporate.ultraleap.com/download/software?name=tracking-software&version=4.1.0&platform=windows)
5. Plug in Leap to computer and a new leap motion icon should appear. It should be green.

## Using Leap Motion Controller 1 with P5.js online editor
1. Open [Brick Breaker](https://editor.p5js.org/HybridLabCCA/sketches/CS4ZA99aJ) and see if it works
2. Create a new p5 project
3. Download leap p5 library [here](https://github.com/CCAHybridLab/HLResources/blob/main/Tutorials/Leap_Motion/leap-1.1.1.min.js)
4. Upload that file to your p5 project [tutorial on how to upload files to online editor](https://thecodingtrain.com/tracks/code-programming-with-p5-js/code/7-arrays/upload-editor)
5. Update your index.html file to reference that library
   ```
   <!DOCTYPE html>
      <html>
        <head>
          <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.7.3/p5.min.js"></script>
          <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.7.3/addons/p5.sound.min.js"></script>

          <!-- ADD THIS LINE OF CODE -->
          <script src="leap-1.1.1.min.js"></script>
   
          <link rel="stylesheet" type="text/css" href="style.css">
          <meta charset="utf-8" />
      
        </head>
        <body>
          <script src="sketch.js"></script>
        </body>
      </html>
   ```
## Examples
1. P5.js Examples
   - [Brick Breaker](https://editor.p5js.org/HybridLabCCA/sketches/CS4ZA99aJ)
