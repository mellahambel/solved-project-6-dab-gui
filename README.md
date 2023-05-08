Download Link: https://assignmentchef.com/product/solved-project-6-dab-gui
<br>
Overview

Your assignment is to create a Swing-based GUI front-end application for the Dots and Boxes implementation.  The interface should look something like this, although the exact layout is entirely up to you:

The graphical rendering of the game grid is handled by a custom Swing component that you’ll download below.  You’ll need to create all of the other interface elements, and ensure they work properly with the custom component and the DABGame implementation.

Details

Your implementation must be named edu.vt.cs5044.DABPanel and your JUnit test suite must be named edu.vt.cs5044.DABPanelTest.  The system relies upon your own Project 4 DABGame implementation as the fundamental engine for this system.

Reference Implementation

It is fully recognized that some of you may have outstanding bugs and/or missing features in your Project 4  DABGame implementation.  That’s not any problem at all.  Everyone is free to download a fully operational implementation of Project 4 (as a JAR with class files only; no source code) for integration within this project.

Graphical Interface Description

When your implementation is launched, it should begin with a newly-initialized 3×3 game displayed, along with a menu bar, status indicator components, and input components.  The layout does NOT need to exactly match the sample above, but it should still appear at least reasonably neat and professional in nature.  It should also be reasonably resilient to resizing, such that the interface expands or contracts to fill the available space given to its window.

The menu bar will contain one “Game” menu with a sub-menu that must look exactly like this (there is some small degree of flexibility in the test cases, but not much):

The menu includes items to initialize a 2×2, 3×3, and 4×4 grid, as well as an item to toggle on/off interactive mode (see DABGrid below).  The status indicators must include the score for each player, along with a display of which player has the current turn (or a “game over” message, when applicable).  The status indicators must always reflect the current state of the game.  The input components must include drop-down boxes to specify x and y parts of a coordinate (with only valid options shown, meaning 0, 1, and 2 for a 3×3 grid), along with a direction drop-down, plus a button to attempt to draw the specified edge when clicked.  The button should be disabled (grayed-out) when the game is over, but enabled at all other times.

DABGrid

DABGrid is the custom component responsible for drawing the grid.  You must integrate this component within your overall layout.  By default, this component simply displays the current state of the grid, by calling DABGame accessor methods.  When this component is set to interactive mode, the grid will become interactive, responding to mouse movements and clicks.  Hovering the mouse near an un-drawn edge will highlight the edge.  Clicking a highlighted edge will cause this component to call the DABGame drawEdge() mutator to draw the edge, then notify your system via a callback that the status indicators must be refreshed.  Interactive mode must be activated and deactivated by your code, in response to your menu system.







Testing

Testing of GUI applications is notoriously complicated.  Because the Swing system actually takes primary control of  application, we can’t just call the application code directly as in our previous systems.  In order for test code to interact with the application, we first need to be sure that each component has a name assigned.  The test code must search through the component hierarchy looking for these names, in order to fetch references to the key components.  All of this is handled for you already in the starter code.

Once you have references to the Swing components, your test code needs to ask Swing to schedule your method calls.  At that point you may query the state of the the GUI directly with accessors, and make assertions as normal.

This can all be done via standard JUnit test cases, but there a few additional issues that we won’t have time to cover in detail.  Thus a <em>complete</em> JUnit test suite is provided for download below.  This is exactly the same test suite used by Web-CAT for this assignment.  Assuming you don’t have any redundant conditionals or other such problems in your code, this test suite should also achieve 100% coverage of your code.

Getting started with Eclipse

Configuring the Build Path

Create a new project in Eclipse and create the edu.vt.cs5044 package within the src folder, and another new source folder called test.  Right-click the project and select Build Path | Configure Build Path, then select the Libraries tab.

First, click “Add Library” then select JUnit | JUnit 4 and click  Finish.

Next, use “Add External JARs” to navigate to and select the dab5044.jar library you downloaded during Project 4 (available below).  Expand the library node, select Javadocs, and click Edit to verify and add the dab5044-api.jar file (also available below) from Project 4 as the Javadocs.

Next, you need to download the dabgui.jar and dabgui-api.jar files (both available  below) and repeat the process above to add them to your project libraries as well.

Finally, you need to choose a Project 4 (DotsAndBoxes) implementation to use with this project.  You have two options, and you can quite easily switch between them at any time:

<em>Option 1 – Reference implementation (recommended)</em>To use the reference implementation, just download the dabgame-ref.jar file below, and save it somewhere convenient.

<em>Option 2 – Your own implementation (advanced)</em>If Web-CAT assigned you 30 “correctness” points in Project 4, you should be able to use your own implementation with no problems.  Be sure to open your Project 4 project in Eclipse, then select File | Export from the menu.  Select the Java | “JAR file” wizard and click Next.  Uncheck everything at first, then in the main top area expand your Project 4 project and check only its “src” folder (which causes the project to show a dash in the checkbox).  Below that, check “Export generated class files and resources” and uncheck all the other checkboxes and options.  Click the Browse  button, navigate to a convenient location, and choose any reasonable file name that ends with the .jar extension.  Click Finish to create and save the Jar file.

Once you’ve completed at least one of the options above, or if you later just want to switch between the two options, right-click your DAB GUI project, click Build Path | Configure Build Path, then select the Libaries tab.  If you already have one of the implementations above listed in the libraries area, select it and cilck Remove.  To add an implementation, use “Add External JARs” then navigate to the Jar file of your choice, select it, and click OK.  You do not need to add Javadocs to this file.

Starter code and test code

Download the DABPanel.java and DABPanelTest.java files anywhere convenient.  Open the folder in your operating system, then drag these files to the edu.vt.cs5044 package of the src and test source folders respectively.  Be sure to select “Copy” when Eclipse asks how to import these files.  If you configured the build path properly, both files should compile with no errors (although there are lots of Checkstyle issues with the starter code).

Please carefully review both the starter file and the test file before you begin.  Note that you don’t need to add to the test file, nor alter it in any way.  The comments are there to help you understand how it works.  The starter code is also commented to help guide your implementation approach.  There’s a “TODO” comment in each location where you must develop code.

Downloads

<a href="https://canvas.vt.edu/courses/70397/files/7167488/download?verifier=aFRO73q4efDX5vuQyLGQsSRRO2BBa2RmEgqvBedG&amp;wrap=1">dabgui.jar</a> – The DABGrid custom component, plus a utility class for component names<a href="https://canvas.vt.edu/courses/70397/files/7167487/download?verifier=bLJxQgnpbAUhVxmmRXHcVuuor9NPb5IRg4oUA8W7&amp;wrap=1">dabgui-api.jar</a> – The API for the DABGrid component and utility class<a href="https://canvas.vt.edu/courses/70397/files/7167486/download?verifier=vPwOwEtlatZBMxmjwoizGlf5dKjqEBlJr8Q7bkI8&amp;wrap=1">dabgame-ref.jar</a> – Reference implementation of the DotsAndBoxes interface (from Project 4)<a href="https://canvas.vt.edu/courses/70397/files/7167484/download?verifier=7tG99d9PWynXEs1lyxZrBYjbyTg5ZlSfFUpUL6sY&amp;wrap=1">DABPanel.java</a> – Starter code for your implementation<a href="https://canvas.vt.edu/courses/70397/files/7167483/download?verifier=3JW77o9w7RMUm8EajZDKhYBWXjSek1BH6L3uuiQQ&amp;wrap=1">DABPanelTest.java</a> – Complete JUnit test code for your implementation


