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
2. Void setup & draw plain bakground
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
3. Circle 1 for reference @ 0,0
4. Circle 2, move via translate
5. Rect 1, draw
6. Rect 1 is in wrong location! Push and pop for circle 2.
7. Rect 2, push & pop
8. Rect 2, rotation
9. Rect 2, translation
10. Fiddling with distance from center of rotation
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
