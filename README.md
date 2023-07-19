# Employee-Management-System

package employee.management.system;

/**
 *
 * @author souvi
 */
import java.awt.Color;
import java.awt.Font;
import java.awt.Image;
import java.awt.event.ActionListener;
import java.awt.event.*;

import javax.swing.*;

class Splash extends JFrame implements ActionListener/*
  */ {
  // thisjframe comes from swing package
  Splash()
  // default constructor
  {
    getContentPane().setBackground(Color.WHITE);
    // it is used to set the backgroung color of the frame.

    setLayout(null);
    // it means we will not use the swing layout for editing ,we will use own layout

    JLabel heading = new JLabel("EMPLOYEE MANAGEMENT SYSTEM");
    // IT IS A JLABEL CLASS FOR PRINTING INFORMATION ON THE FRAME

    heading.setBounds(80, 30, 1200, 60);
    // it takes four argyments first is distance of the text from the
    // left,right,width of the frame,height of the frame

    heading.setFont(new Font("serif", Font.PLAIN, 60));

    heading.setForeground(Color.RED);

    add(heading);

    ImageIcon i1 = new ImageIcon(ClassLoader.getSystemResource("icons/front.jpg"));
    // this is used to get the image from the respective file

    Image i2 = i1.getImage().getScaledInstance(1100, 700, Image.SCALE_DEFAULT);
    // this is used to scale up the image

    ImageIcon i3 = new ImageIcon(i2);
    // this is used to change it from image to imageicon because jlabel only stores
    // imageicon

    JLabel image = new JLabel(i3);

    image.setBounds(50, 100, 1050, 500);
    add(image);

    JButton clickhere = new JButton("CLICK HERE TO CONTINUE");
    clickhere.setBounds(400, 400, 300, 70);
    clickhere.setBackground(Color.BLACK);
    clickhere.setForeground(Color.WHITE);
    clickhere.addActionListener(this); /* this function tells that there is a click event */
    image.add(clickhere);

    setSize(1170, 650);
    setLocation(200, 50);
    // it takes two arguments i.e distance from left and distance from top
    setVisible(true);

    while (true) {
      heading.setVisible(false);

      try {

        Thread.sleep(500);

      } catch(Exception e) {

      }
      heading.setVisible(true);
      try {

        Thread.sleep(500);

      } catch (Exception e) {

      }

    }
    // This while loop is used for doing blinking of the heading
    // This while loop will run for infinite times
    // for this we use setvisible
    // and controlling the time we use try and catch method
  }

  public void actionPerformed(ActionEvent ae) {
    // it is the function that tells the event
    setVisible(false);

    new login();
    /*
     * we are declaring an object for login ,as the object is called automatically
     * constructor also being called hence login page w
     * ll be displayed
     */
  }

  public static void main(String args[]) {
    new Splash();
  }

}
