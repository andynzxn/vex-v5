/*----------------------------------------------------------------------------*/
/*                                                                            */
/*    Module:       main.cpp                                                  */
/*    Author:       VEX                                                       */
/*    Created:      Tue Mar 16 2021                                           */
/*    Description:  Arm UI Panel                                              */
/*                                                                            */
/*    This example will configure the Workcell Arm and display                */
/*    a basic UI on the V5 Brain's screen that you can configure              */
/*                                                                            */
/*----------------------------------------------------------------------------*/


// ---- START VEXCODE CONFIGURED DEVICES ----
// Robot Configuration:
// [Name]               [Type]        [Port(s)]
// RoboticArm1          RoboticArm    1, 2, 3, 4, 1, 2, 3, 4
// EStop                bumper        E              
// Magnet5              electromagnet 5              
// ---- END VEXCODE CONFIGURED DEVICES ----


#include "vex.h"


using namespace vex;


// Function to run when the V5 Brain's screen is pressed
void onScreenPressed() {
 if (Brain.Screen.xPosition() > 250) {
   if (Brain.Screen.yPosition() > 125) {
     // Blue Box Pressed
     RoboticArm1.moveToPositionJoint(9.5, 8.2, 4);
     Magnet5.drop();
   }
   else {
     // Green Box Pressed
     RoboticArm1.moveToPositionJoint(6.5, 4.5, 4);
     Magnet5.drop();
    
   }
 }
 else {
   if (Brain.Screen.yPosition() > 125) {
     // Red Box Pressed
     RoboticArm1.moveToPositionJoint(10.18, 4.6, 4);
     Magnet5.drop();     






    
   }
   else {
     // White Box Pressed
     float X = 9.726 ;
     float Y = -4.218;
     Magnet5.drop();
     Magnet5.pickup();
     wait(1, sec);
     RoboticArm1.moveToPositionJoint(X, Y, 5);
     wait(1, sec);
     RoboticArm1.moveToPositionJoint(X, Y, 2.3);
     wait(1, sec);
     RoboticArm1.moveToPositionJoint(X, Y , 5);
     wait(1, sec);




   }
 }
}


// Function to run when the emergency stop button is pressed
void onEStopPressed() {
 RoboticArm1.emergencyStop();
}


int main() {
 // Initializing Robot Configuration. DO NOT REMOVE!
 vexcodeInit();
 
 // register event handlers
 Brain.Screen.pressed(onScreenPressed);
 EStop.pressed(onEStopPressed);


 wait(15, msec);
 // post event registration


 // draw UI on brain screen
 Brain.Screen.setPenColor(white);
 Brain.Screen.setFillColor(white);
 Brain.Screen.drawRectangle(30, 10, 200, 100);
 Brain.Screen.setFillColor(red);
 Brain.Screen.drawRectangle(30, 125, 200, 100);
 Brain.Screen.setFillColor(green);
 Brain.Screen.drawRectangle(250, 10, 200, 100);
 Brain.Screen.setFillColor(blue);
 Brain.Screen.drawRectangle(250, 125, 200, 100);
  // configure the arm
 RoboticArm1.setMasteringValues(1771, 2207, 1933, 542);
 RoboticArm1.moveToPositionJoint(4.712, 0, 3.864);


 RoboticArm1.setToolTipOffset(-0.7, 0.0, -1.0);
 Magnet5.setPower(100);
 RoboticArm1.setLinearMoveSpeed(5);
}



