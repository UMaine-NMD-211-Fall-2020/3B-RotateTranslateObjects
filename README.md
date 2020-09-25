# 3B-RotateTranslateObjects
Learn how to rotate and translate objects

Concepts covered
- translation
- rotation
- push & pop

## To Turn In
An example image/ set of moving images with
- translation
- rotation
- push and pop obviously happening
- [Extra] experiment with the order of translations and rotations. What happesn if you rotate first?

Create something that is more than the example, something you want to turn in and share, not just the token motions shown in my example. 
## Concept Walk Through via Code
### Code Set Up
1. Start the lab with your comments
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
```
2. Set up your drawing space. This exercise uses ellipses and rectangles so I added ellipseMode and rectMode. A constant, plain black background works well for this exercise. 
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
}
```
3. Draw a circle at (0,0). This will be a reference point for the rest of our lab. It will help us understand what happens when we translate or rotate shapes.  
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);         // red 
     ellipse( 0, 0, 100, 100); // circle - x, y, w, h
     
}
```
4. Draw a 2nd circle. This is the circle we will try translate on. Make it a different color, and place it exactly where circle 1 is. 
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);         // red 
     ellipse( 0, 0, 100, 100); // circle - x, y, w, h
     
     //Circle 2
     fill( 255, 255, 0);         // yellow 
     ellipse( 0, 0, 100, 100); // circle - x, y, w, h
}
```
5. Test translate on the new circle. We will move it a half page away from 0 using width, along the x direction, and half a page down from 0, along the y direction.
```
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);         // red 
     ellipse( 0, 0, 100, 100); // circle - x, y, w, h
     
     //Circle 2
     translate( width/2, height/2);     // move the circle
     fill( 255, 255, 0);         // yellow 
     ellipse( 0, 0, 100, 100);   // circle - x, y, w, h
}
```
6. Let's draw a rectangle as a new shape, and use it as a reference for future rotations. We want to place the rectangle at a quarter of the page from 0 in the x and y directions. We try just placing it. 
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);         // red 
     ellipse( 0, 0, 100, 100); // circle - x, y, w, h
     
     //Circle 2
     translate( width/2, height/2);     // move the circle
     fill( 255, 255, 0);                // yellow 
     ellipse( 0, 0, 100, 100);          // circle - x, y, w, h
     
     //Rect 1
     fill( 0, 255, 0);                  // green
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
}
```
7. Hmm... Rect 1 is in wrong location! We need to remember the state the canvas was in using Push, translate circle 2, then and pop and return to the original state.
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);         // red 
     ellipse( 0, 0, 100, 100); // circle - x, y, w, h
     
     //Circle 2
     push();
     translate( width/2, height/2);     // move the circle
     fill( 255, 255, 0);                // yellow 
     ellipse( 0, 0, 100, 100);          // circle - x, y, w, h
     pop();
     
     //Rect 1
     fill( 0, 255, 0);                    // green
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
}
```
8. Great! Everything works as expected. Let's push and pop and prepare a rectangle 2 that we will experiment with rotation on. 
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);         // red 
     ellipse( 0, 0, 100, 100); // circle - x, y, w, h
     
     //Circle 2
     push();                            // save layout coordinates
     translate( width/2, height/2);     // move the circle
     fill( 255, 255, 0);                // yellow 
     ellipse( 0, 0, 100, 100);          // circle - x, y, w, h
     pop();                             // returned to saved layout coordinates
     
     //Rect 1
     fill( 0, 255, 0);                    // green
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     
     //Rect 2
     push();                              // save layout coordinates
     fill( 0, 255, 255);                  // teal
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     pop();                               // returned to saved layout coordinates
}
```
9. Right now, Rect 2 overlaps Rect 1. We will add rotation. First, we will hardcode rotate the shape, 0.1 radians or roughly 5 degrees around an axis and origin to be determined later. 
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);         // red 
     ellipse( 0, 0, 100, 100); // circle - x, y, w, h
     
     //Circle 2
     push();                            // save layout coordinates
     translate( width/2, height/2);     // move the circle
     fill( 255, 255, 0);                // yellow 
     ellipse( 0, 0, 100, 100);          // circle - x, y, w, h
     pop();                             // returned to saved layout coordinates
     
     //Rect 1
     fill( 0, 255, 0);                    // green
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     
     //Rect 2
     push();                              // save layout coordinates
     rotate( 0.1 );                       // rotate 0.1 radians
     fill( 0, 255, 255);                  // teal
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     pop();                               // returned to saved layout coordinates
}
```
10. Degrees are nicer to deal with and give us smaller turns. We change the code in the rectangle's rotations to get smaller turns.
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);         // red 
     ellipse( 0, 0, 100, 100); // circle - x, y, w, h
     
     //Circle 2
     push();                            // save layout coordinates
     translate( width/2, height/2);     // move the circle
     fill( 255, 255, 0);                // yellow 
     ellipse( 0, 0, 100, 100);          // circle - x, y, w, h
     pop();                             // returned to saved layout coordinates
     
     //Rect 1
     fill( 0, 255, 0);                    // green
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     
     //Rect 2
     push();                              // save layout coordinates
     rotate( radians(1) );                // rotate 1 degree
     fill( 0, 255, 255);                  // teal
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     pop();                               // returned to saved layout coordinates
}
```
11. Make a global variable for degrees. We will change the degrees rotated over time, incrementing by 1. Replace the 1 degree by the degrees rotated. 
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
int degreesRotated = 0;

void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);                 // red 
     ellipse( 0, 0, 100, 100);         // circle - x, y, w, h
     
     //Circle 2
     push();                            // save layout coordinates
     translate( width/2, height/2);     // move the circle
     fill( 255, 255, 0);                // yellow 
     ellipse( 0, 0, 100, 100);          // circle - x, y, w, h
     pop();                             // returned to saved layout coordinates
     
     //Rect 1
     fill( 0, 255, 0);                    // green
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     
     //Rect 2
     push();                              // save layout coordinates
     rotate( radians(degreesRotated) );   // rotate 1 degree
     fill( 0, 255, 255);                  // teal
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     pop();                               // returned to saved layout coordinates
    
    degreesRotated += 1;                  // increment degrees 
}
```
12. Rect 2 is rotating, but it's rotating around (0,0), our top left corner. To change the point around which the shape rotates, add a translation. 
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
int degreesRotated = 0;

void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);                 // red 
     ellipse( 0, 0, 100, 100);         // circle - x, y, w, h
     
     //Circle 2
     push();                            // save layout coordinates
     translate( width/2, height/2);     // move the circle
     fill( 255, 255, 0);                // yellow 
     ellipse( 0, 0, 100, 100);          // circle - x, y, w, h
     pop();                             // returned to saved layout coordinates
     
     //Rect 1
     fill( 0, 255, 0);                    // green
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     
     //Rect 2
     push();                              // save layout coordinates
     translate( width/2, height/2);       // move to the center
     rotate( radians(degreesRotated) );   // rotate 1 degree
     fill( 0, 255, 255);                  // teal
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     pop();                               // returned to saved layout coordinates
    
    degreesRotated += 1;                  // increment degrees 
}
```
13. Change the rectangle's x and y to change how far it rotates from the center.
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - ADD WHAT YOU ARE TURNING IN SPECIFICALLY, HERE
     - ADD QUESTIONS, COMMENTS, CONCERNS ABOUT YOUR CODE
     - ADD SOURCES
*/
int degreesRotated = 0;

void setup(){
     size( 500, 500);
     
     noStroke();
     ellipseMode( CENTER );
     rectMode( CENTER );
}
void draw(){
     background(0);
     
     //Circle 1
     fill( 255, 0, 0);                 // red 
     ellipse( 0, 0, 100, 100);         // circle - x, y, w, h
     
     //Circle 2
     push();                            // save layout coordinates
     translate( width/2, height/2);     // move the circle
     fill( 255, 255, 0);                // yellow 
     ellipse( 0, 0, 100, 100);          // circle - x, y, w, h
     pop();                             // returned to saved layout coordinates
     
     //Rect 1
     fill( 0, 255, 0);                    // green
     rect( width/4, height/4, 100, 100);  // square - x, y, w, h
     
     //Rect 2
     push();                              // save layout coordinates
     translate( width/2, height/2);       // move to the center
     rotate( radians(degreesRotated) );   // rotate 1 degree
     fill( 0, 255, 255);                  // teal
     rect(0, 0, 100, 100);  // square - x, y, w, h
     pop();                               // returned to saved layout coordinates
    
    degreesRotated += 1;                  // increment degrees 
}
```
That's everything you need to understand translations and rotations!
## Example End Code
```processing
/*   3B - NMD 211 
     FirstName LastName
     September 25, 2020
     
     Translations & Rotations
     - translate shape
     - rotate shape
*/
int degreesRotated = 0;

void setup(){
  size( 500 , 500 );
  
  noStroke();
  ellipseMode( CENTER );
  rectMode( CENTER );
}

void draw(){
  background( 0 );
  
  // circle 1
  fill( 255 , 0 , 0 );
  ellipse( 0, 0, 100, 100); // x, y, w, h
  
  //circle 2
  pushMatrix();             // snapshot of coordinate system up to now
  translate( width/2, height/2);
  fill( 255, 255, 0);
  ellipse( 0, 0, 100, 100); // x, y, w, h
  popMatrix();              // back to coordinate system from the snapshot
  
  // rect1
  fill( 0, 255, 0);
  rect( width/4, height/4, 100, 100);
  
  // rect 2
  pushMatrix();             // snapshot of coordinate system up to now
  translate( width/2,height/2);
  rotate(radians(degreesRotated));
  fill(0, 255, 255);
  rect( width/4, height/4, 100, 100); // x, y are how far you are from center of rotation
  popMatrix();              // back to coordinate system from the snapshot


  degreesRotated += 1;
}
```

## Submit Via Github
For those of you who want to submit this lab via Github, submit below by adding a link to your github repository for the lab. 
- [Lab3B-FirstNameLastName](http://example.com)
