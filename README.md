# UI-Component
Assignment 2 : UI Component
//UI-Control
//Name: Megat Danish Andzxar bin Abd Samad
//ID: 1132702823
//Lecturer: Dr Kim Yonggeun
//Lecturer:Dr. Forest Lim Yang Peng
//Subject Code: MMA 2013
//Subject: Interaction Design
import controlP5.*;
ControlP5 cp5;

int myColor = color(255);
int c1, c2;
float n, n1;

int p1, p2;

int Opacity;
int DistanceFromMouse;
boolean Switch;

void setup() {
  size(1280, 720);
  noStroke();
  cp5 = new ControlP5(this);

  cp5.addButton("Colour").setValue(0).setPosition(500, 420).setSize(200, 19); //For the button
  cp5.addSlider("Opacity").setPosition(500, 300).setSize(15, 100).setRange(0, 100);//Slider
  cp5.addKnob("DistanceFromMouse") .setRange(0, 255).setValue(50).setPosition(600, 300).setRadius(50).setDragDirection(Knob.VERTICAL);//Knob
  cp5.addToggle("Switch").setPosition(540,390).setSize(50,15).setMode(Toggle.SWITCH);
  cp5.addRadioButton("radioButton").setPosition(400,450) .setSize(40,20) .setColorForeground(color(120)).setColorActive(color(255)).setColorLabel(color(255))
                                   .setItemsPerRow(5).setSpacingColumn(50).addItem("50",1).addItem("100",2).addItem("150",3).addItem("200",4).addItem("250",5);
}

void draw() {
  background(p1,p1,p1);//background
  myColor = lerpColor(c1, c2, n);//button
  n += (1-n)* 0.1;//button
  
  if(Switch==true) {
    p1 = 255;
  } else {
    p1 = 0;
  }
  ellipse(mouseX-DistanceFromMouse,mouseY-DistanceFromMouse,50,50);
  fill(myColor,Opacity);
}
//button
public void controlEvent(ControlEvent theEvent) {
  println(theEvent.getController().getName());
  n = 0;
  //button
}


public void Colour(int theValue) {
  println("a button event from colorA: "+theValue);
  c1 = c2;
  c2 = color(random(255), random(255), random(255));
}
