# 3B-RotateTranslateObjects
Learn how to rotate and translate objects

## DETAILS COMING SOON

## END CODE
int shapeRad = 50;
int pathRad = 200;

float beginX = 0;
float beginY = -pathRad;

float currentX = beginX;
float currentY = beginY;
float currentRotation = 0;


void setup(){
  size(500,500);
  noStroke();
  ellipseMode(CENTER);
}
void draw(){
  background(0);
  
  pushMatrix();
  translate(width/2, height/2);
  rotate(radians(currentRotation));

  
  fill(255);
  ellipse( currentX, currentY, shapeRad, shapeRad);
  
  popMatrix();
  
  currentRotation +=1;
}
