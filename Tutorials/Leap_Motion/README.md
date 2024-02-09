# Leap Motion with P5.js online web editor
Leap Motion Controller is a hand-tracking system designed to be placed on a physical desktop or mounted to VR headset.

**The [latest Leap software](https://leap2.ultraleap.com/gemini-downloads/) doesn't support websockets, which means you can't connect it to the P5 web editor.
We need to use legacy software which only runs on Windows os.**

## SETUP
1. Use a Windows 7+ machine
2. Download [Legacy Orion 4.1 Handtracking Software](https://staging.corporate.ultraleap.com/download/software?name=tracking-software&version=4.1.0&platform=windows)
3. Plug in Leap to computer and a new leap motion icon should appear. It should be green.

## TUTORIAL
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
6. Add this to the script.js file (at the bottom outside the draw loop)
   ```
   var options = {enableGestures: true};
   console.log("running…");

   Leap.loop(options, function(frame){
   	if (frame.hands.length  > 0){
   	  for(var i = 0; i < frame.hands.length; i++){
            // this is where you'll extract data from the hands detected!
            console.log(frame.hands[i]);
   	  }
   	}  
   });
   ```
