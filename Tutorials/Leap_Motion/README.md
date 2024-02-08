# Leap Motion Controller 1
Leap Motion Controller is a hand-tracking system designed to be placed on a physical desktop or mounted to VR headset.

In 2019 Leap Motion and Ultrahaptics merged to form Ultraleap. Leap Motion Controller is the older model now only supported by Windows machines. 
[Ultraleap's Leap Motion 2 is the latest model](https://leap2.ultraleap.com/)
## Setup
1. Use a Windows 7+ machine
2. [Create an account or login to Ultraleap](https://leap2.ultraleap.com/account-register/)
4. Download [Legacy Orion 4.1 Handtracking Software](https://staging.corporate.ultraleap.com/download/software?name=tracking-software&version=4.1.0&platform=windows)
5. Plug in Leap to computer

2. Update your index.html file to reference that library
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
