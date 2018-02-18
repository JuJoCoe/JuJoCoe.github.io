# Virtual Reality 4331 Project 1

Project 1 focusus on creating a human scale scene experienced from the 'inside out'. Included in my project are 15+ unique models, user controlled lighting, user navigation, and a dynamic object to interact with. 

## Important Links 

<a href="https://jujocoe.github.io/">Project 1 Interaction</a>
Given the amount of unique objects in this project, the project may take some time to load all assets and may lag a little while it is loading all assets. 

<a href="http://slides.com/jordancoe/project-1#/">Project 1 Presentation</a>

<a href="https://github.com/JuJoCoe/JuJoCoe.github.io/blob/master/demo_video/Project_1_Demo.mp4">Project 1 Demo Video mp4 file</a>
This links to the raw file which you can download to view the demo.

<a href="https://www.youtube.com/watch?v=fuZHbIO0vaQ&feature=youtu.be">Project 1 Demo Youtube</a>

### Instructions
After clicking the Project 1 Interaction and allowing it to load all assets, you will be able to move around the room using wasd. You can turn your camera by using a mouse on computer, or by simply turning your head in VR. My project has no click action, instead it allows the user to place the cursor on an object and click after 1 second. For example, in the picture below the user hovers over the green box for 1 second, then the action will complete. 
![ScreenShot](/demo_images/GreenLights.png)

All the objects that the user can interact with are listed below. 

- The user may interact with the light switches in the living room. The on switch is on the left, while the off switch is on the right.
- The dynamic object is the door. The user may open and close the door.
- The choose your color boxes in the bedroom. The user can choose 1 of 4 colors, and all the lights inside the bedroom will match the color. 
- When the user goes up to the laptop sitting on the desk, the laptop will make a startup sound. 


### Code    
My project uses the aframe library to run the code. I used an addon for aframe called aframe-event-set-component. This library allowed me to contain multiple events within one object, and also allowed me to target specific object within my scene using the id-tag function for example. The code below uses an invisible box, which triggers 4 events on one click. 

```
 <a-box id="box" material="color:tomato;transparent:true;opacity:0"
           position="7.43 1.666 -2.00" height="1" depth="1" width="1"
           event-set__1="_event: click; _target: #Living_Light1; distance: 0.01;"
           event-set__2="_event: click; _target: #Living_Light2; distance: 0.01;"
           event-set__3="_event: click; _target: #Living_Light3; distance: 0.01;"
           event-set__4="_event: click; _target: #Living_Light4; distance: 0.01;"></a-box>
```
These 4 events target 4 different lights within my scene and sets the distance to 0.01(which turns the lots off). I found this library to be very user friendly and easier than setting up components using JavaScript. 

Another unique addition to my code is using the fuse command in my camera controls. The fuse command allows the user to create a timer on the cursor, which will act as a click when hovering over a button for a certain amount of time. I found this setting easier to use with a VR headset because the user can just look at the object of 1 sec and act as a click instead of having to use the volume buttons on the phone. If your headset doesn't have a controller, using buttons can be problematic. The code below shows how to use the fuse command. 
```
<a-entity cursor="fuse: true; fuseTimeout: 1000;"
```
The fuseTimeout:1000 is what sets the time it takes for the click to respond. To low and a user could accidently click buttons, and to high and the user would spend to much time staring at one object. 

### Theme 
My theme of my project was to make a nice apartment or house that I would like to live in. It is simple, but clean and nice. The majority of my objects are neutral color like black, grey, and brown. Since I wanted all my objects to work together, I spent a large portion of my time just downloading and testing assets to see if they fit my theme. I believe that I accomplished my goals in making a nice neutral house.
![ScreenShot](/demo_images/LivingRoom1.png)

### Issues
While doing my project I ran into many issues on the way, but there were two issues that gave me the most problem. My first issue was trying to find a way to have one object affect other objects. I spent countless hours trying to learn complicated JavaScript code to do a task that I thought was fairly simple. I came across a website after searching google which gave me a simple solution to my problem. 

<a href="https://www.npmjs.com/package/aframe-event-set-component">aframe-event-set-component</a>

This simple a-frame component addon fixed all the issues that I was having.

The second issue I had was trying to optimize my house to run better. My first implementation of my code had about 30 assets, multiple rooms, multiple lights, and high resolution textures. I quickly found out that this made my code sluggish and laggy. I ended up removing about 12 assets that were high resolution and pointless, and stick to two rooms. I found a very interesting article about aframe optimization that really helped me improve my performance while still meeting all the requirements.

<a href=https://hacks.mozilla.org/2017/07/optimizing-performance-of-a-frame-scenes-for-mobile-devices/>Optimizing Performance of A_Frame Scenes for Mobile Devices</a>

This article had very many interesting facts about aframe optimization, for example, using textures that are powers of two helps ensure optimal memory use. 

### Conclusion
In conclusion, I think that this project was a good stepping stone into learing how to code in virtual reality. A learned the basics of aframe and I now feel confident in my ability to code using it. I plan on coming back to this project in the future and improving it even more. Some improvements I would like to make is making an outside area, and making multiple levels(upstairs and downstairs). 

### Contribution
- Created by Jordan Coe.

<a href="https://github.com/JuJoCoe/JuJoCoe.github.io/blob/master/assets/Assetsworkcited.txt">Assets Used</a>
