# 3B-RotateTranslateObjects
Learn how to rotate and translate objects

## To Turn In
An example image/ set of moving images with
- translation
- rotation
- push and pop obviously happening

Create something that is more than the example, something you want to turn in and share, not just the token motions shown in my example. 
## Code Example Walkthrough

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
