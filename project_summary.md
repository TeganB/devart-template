# Dissonance at Six


## Authors
- Tegan Bristow, github.com/TeganB - [Tegan Bristow Website](http://teganbristow.co.za/ "Tegan Bristow Website")
- Assisted by Fabrice Iyolo of the Wits University Google Dev Group.

## Description
Dissonance at Six is an experiment in interactive recursive graphics, with a focus on the number six.  I designed the piece to get participants actively together. I believe that coherence or clarity in the world comes from people sharing and cooperating. The work however also questions the limit of this cooperation and where we loose sight ourselves in this cooperation.

Dissonance at Six encourages participants to develop the image together. Every time a new participant joins the scene a recursive tree pattern literally grows. The piece continues becoming more extravagant - more participants brings not only new tree's but greater recursion and exuberance to the piece. Till six participants have joined, at this point all the “leaves” fly off the trees and the scene becomes cold, turning the focus away from the screen and towards the other participants that have taken the piece to that point.

Six is a number linked to creation; in that in many creation myths the world is created in six days. Six is also a perfect number as it alone reforms itself by addition of its’ half, its third and its sixth. It also represents the point prior to chaos, and yet in religious texts it is considered imperfect and of the earth, and the addition of one making it part of ethereal.

On a very personal note: the piece was developed soon after I lost a brother, we are a large family of eight siblings. Loosing him was akin to loosing a part of myself and I wanted to collaboratively explore the relationships in being part of a whole, moving past the notion of existence as being about individuation. The role of community and togetherness is a very important part of South African culture. I use Dissonance at Six to playfully and visually explore notions of communal experience.


## Link to Prototype
No online protoype


## Example Code
NOTE: Wrap your code blocks or any code citation by using ``` like the example below.
```
// Leaves that are attached to the branches
void leaves(float h, float leafAngle, float tri3) { 
  h *= 0.66;
  if (h > 3) {
    float base = 10;
    float baseL = constrain(tri3, 0, 1000);
    pushMatrix();
    rotate(treeTheta + leafAngle);
    translate(0, (-h)); 
    leaves(h, leafAngle, tri3); 
    popMatrix();  
    
    // restricting the movement fo the leaves when they fall
    if(leavesFall && fallY<height){
    //println(leavesFall);
    fallY = fallY + 0.02;
    }
    
    if(!leavesFall && fallY > 0){
    fallY = fallY - 0.02;
    }    
    
    pushMatrix();
    rotate(-treeTheta + leafAngle);
    translate(0, (-h));
    leaves(h, leafAngle, tri3);
    
    //yellow leaves
    noStroke();
    fill(255,255, 0, 50);
    triangle(-5-fallY, 0-fallY, 5-fallY, 0-fallY, 0-fallY, -baseL-fallY);
    //treeline
    strokeWeight(2);
    stroke(12,192,245,100);
    line(-base+fallY, fallY, base+fallY, base+fallY);
    popMatrix();
  }
  
}
```
## Links to External Libraries
The Simple OpenNI library was used to manage the Kinect CoM.
No other external's were used.

[Simple OpenNI](https://code.google.com/p/simple-openni/ "Simple OpenNI")

## Images & Videos

![DissonaceAtSix](http://teganbristow.co.za/wp-content/uploads/2013/05/MM_5.jpg "Image for Dissonance at Six")


