# OpenGL

Notes from http://www.glprogramming.com/ and https://developer.apple.com/library/content/documentation/GraphicsImaging/

What does OpenGL do:

It has primitives like lines, points, polygons and bitmaps through which you can create any graphic

Lets you arrange objects in a 3D space and helps you select a view point to view the space

Calculates color of all the objects either by explicit assignment from the application or based on specified lighting conditions, or some texture or all three.

Converts the mathematical description of objects and their associated color information to pixels on the screen - Rasterizing. See the note on rendering, frame buffer and bitplanes below.

Arrange the objects in three-dimensional space and select the desired vantage point for viewing the composed scene.

Calculate the color of all the objects. The color might be explicitly assigned by the application, determined from specified lighting conditions, obtained by pasting a texture onto the objects, or some combination of these three actions.

Convert the mathematical description of objects and their associated color information to pixels on the screen. This process is called rasterization.

Client and Server in OpenGL

Client. - That issues commands for drawing
Server - The machine that performs the drawing 



Rendering - The process by which computers create images from models - models are created by geometric primitives likes points, lines, polygons etc

The final output of rendering are pixels. As we know pixel is the smallest visible element - display hardware can be put on the screen. Information about pixels for example about how rid a pixel should be are organized into bitplanes. The bitplanes are held in the frame buffer which holds all the information required to render the image with correct color and intensity on the screen.


Remembering rules for OpenGL command syntax:

- All commands start with gl
- All constants are prefixed with GL_
- OpenGL - commands accept 8 types of data - 8,16 ,32 bit integers - 32,64 bit floating point numbers, 8 ,16,32 bit unsigned integers.  - You can specify what kind of data you are passing to the commands after the command name and the number of arguments . 

For example in the case glColor3f - 3f stands for 3 arguments of floating point numbers. 
glColor3i - 3i stands for 3 arguments of integers (32 bit) . 

Note : Apart from i and f you will sometimes see ‘v’ - which is a pointer to an array of values that can be passed as an argument to an OpenGL command. Some commands may have a vector and non vector form while some may exclusively take non vector arguments. 


OpenGL is a state machine (Brush up on your knowledge of state machines )

Note on OpenGL on Mac

Macintosh computers ship with dedicated graphics hardware that is optimized to perform graphics calculations in parallel.With this hardware configuration, the OpenGL client executes on the CPU and the server executes on the GPU.

Important note on OpenGL Commands

- OpenGL commands are usually executed asynchronously, the client can return control to the application before the server is done executing them

- OpenGL commands are executed in order

- OpenGL copies data required by client during call time before returning control to the application

- OpenGL relies on platform specific libraries for critical functionality

Some terminology

Renderer - Combination of OpenGL hardware and software to execute OpenGL Commands

Renderer and Buffer Attributes - Constants used to help OpenGL set context before drawing content

Pixel Format Data  - the format for pixel data storage in memoryThe description includes the number and order of components as well as their names (typically red, blue, green and alpha). It also includes other information, such as whether a pixel contains stencil and depth values. A pixel format object is an opaque data structure that holds a pixel format along with a list of renderers and display devices that satisfy the requirements specified by an application.

Rendering Context - holds state information like the current color drawing in

Drawable object - OS X - A drawable object refers to an object allocated by the windowing system that can serve as an OpenGL framebuffer. A drawable object is the destination for OpenGL drawing operations
Eg- cocoa view, offscreen memory, pixel buffer

Virtual Screen - Renderer + Physical Display . Virtual screen - hardware renderer + physical display or software renderer + physical display

Getting Started with OpenGL on Xcode:

1. Open Xcode
2. Click on Create a new xcode project
3. Choose macOS - and start a new command line tool application
4. Choose c++ as the language 
5. In the project folder - navigate to build phases and click on link binaries an dlibraries and add OpenGL.framework and GLUT.framework

