# <canvas\> 
## Yahor Hlushanko
___
_1 - INTRO_  

Hy guys! My name is Egor Glushanko, I'm a student of the Rolling Scopes School. I want to talk to you about canvas.

---
_2 - MENU_  

It's history, usage, basics of drawing simple shapes with canvas, couple words about path2d interface in the end.


---
_3 - HISTORY_  

Canvas was initially introduced by Apple in 2004 for use inside their own Mac OS X WebKit component, for applications like Dashboard widgets and the Safari browser. Later, in 2005 and 2006 it was adopted in Gecko and Opera browsers rspectively. Then the Web Hypertext Application Technology Working Group (WHATWG) standardized canvas for use on new proposed specifications for next generation web technologies.
Since  october 2014 we widely use the <canvas\> element as a part of HTML5.
Today most browsers support canvas.

---
_4 - USAGE_  

The Canvas API provides a means for drawing graphics via JavaScript and the HTML <canvas\> element. It can be used for:
1. Animation
1. Creating cool backgrounds
1. Game graphics - well known Google Chrome Dino is made with canvas
1. Graphic editors - for instance Piskel, which clone we should perform by the end of the 2-nd stage here in RSS.
1. For today the best way for canvas use is dynamic rendering of information via interactive graphs and charts
Well known (an not very) chart and graph libraries use canvas as a basis. 
Examples are canvas.js or chart.js.
Here you can see the list of companies who uses canvas.js

Also canvas is used for photo manipulation, real-time video processing and many other things.

---
_5 - WHAT IS CANVAS?_  

Well as I said before, canvas itself is an HTML element which can be used to draw graphics, on the fly,via scripting (usually JavaScript). Canvas has width and height atributes. Default canvas size is 300 to 150 pixels.
Also canvas has it's own coordinate system, which starts at the top-left corner. The X axis is directed down and the Y axis goes right.

---
_6 - CREATE/ RESIZE CANVAS_  

To start working with canvas we should create it:

1.  First we add a <canvas\> element to our HTML. By the way, we can create as many canvases as we wish so it would be a good idea to add a unique id to everyone of them. 
Canvas is a paired tag and in case user's browser doesn't support canvas, any text or image we put inside it will be displayed.

1. Next step is to set the size for our canvas or to be more precise for it's drawing region. We can do it either within HTML or with JavaScript. To stretch canvas to page size we can set it’s size attributes equal to  window.innerWidth and window.innerHeight respectively

1. And what about CSS width and height? Its not forbidden to use them as well. But they just determine the size of the box in which canvas will be shown. While the HTML attributes of width and height set the size of the coordinate system or 'grid' or drawing region that the canvas API will use. And in case they are less than CSS width and height, the canvas will be stretched. We should remember this.

---  

_7 - CONTEXT_  

The Canvas API largely focuses on 2D graphics. And the CanvasRenderingContext2D interface is a part of this API. It provides the 2D rendering context for the drawing surface of a <canvas\> element.
To get 2D context, we should call getContext() on the <canvas\> element, supplying '2d' as the argument.
Now with the context in hand, we can draw anything we like.  

---
_8 - DRAWING SIMPLE SHAPES # PREPARE..._  

Now we'll talk about some properties and methods of the CanvasRenderingContext2D interface in order they are used usually.

- fillStyle and strokeStyle specify the color, gradient, or pattern to use inside shapes and for the strokes (outlines) around shapes respectively.
Their default values are #000 (black).
- lineWidth sets the thickness of lines.
- beginPath() method starts a new path by emptying the list of sub-paths. We call this method when we want to create a new path.

---
_9 - DRAWING SIMPLE SHAPES # START..._  


- rect() adds a rectangle to the current path. Unlike SVG, <canvas\> only supports one primitive shape: rectangles. All other shapes must be created by combining one or more paths.
- arc() adds a circular arc to the current path.
For arc we should specify the center coordinates, radius and a start angle of 0 radians (0°) and an end angle of 2π radians (360°).
- moveTo() method begins a new sub-path, it specifies the starting point by the given (x, y) coordinates.

---
_10 - DRAWING SIMPLE SHAPES # WAIT..._  

Next methods add lines or curves to the current sub-path. The starting point is the latest point in the current path, it can be changed using moveTo() method before creating new line or curve.

- lineTo() adds a straight line t to the specified (x, y) coordinates.
- quadraticCurveTo() method adds a quadratic Bézier curve to the current sub-path. It requires two points: the first one is a control point and the second one is the end point. 
- bezierCurveTo() adds a cubic Bézier curve. It requires three points: the first two are control points and the third one is the end point.

Here you can see control points are red and starting and end points are blue.

---
_11 - DRAWING SIMPLE SHAPES # DRAW..._  

Next methods depict our shapes
- stroke() strokes (outlines) the current or given path with the current strokeStyle and lineWidth.
- fill() fills the current or given path with the current fillStyle.
- clip() turns the current or given path into the current clipping region.

Now using some of methods and properties demonstrated above let's draw a kind of Pacman
Here it is!

---
_12 - path2D() OBJECT_  
MDN Web Docs says;
This is an experimental technology
Check the Browser compatibility table carefully before using this in production. Hmm... Okey..


What is it, the Path2D
The Path2D is an interface of the Canvas 2D API which used to declare a path that can then be used on a CanvasRenderingContext2D object. The path methods of the CanvasRenderingContext2D interface are also present on Path2D interface (such as moveTo() lineTo() and so on), which gives us the convenience of being able to retain and replay our path whenever desired.

The Path2D() constructor returns a newly instantiated Path2D object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of SVG path data. This allows connecting SVG to canvas.


When invoked with a string consisting of SVG path data, a new path is created from that description.
Then just fill it for example.

---
_13 - Q&A_  

That's all I wanted to highlight concerning canvas in my today's video. Thank you for watching. 

_The WebGL API as well as Canvas API uses the <canvas\> element, it draws hardware-accelerated 2D and 3D graphics. WebGL API works throw WebGLRendering​Context interface._

_Note: Lines can be drawn with the stroke(), strokeRect(), and strokeText() methods_

_Drawing Pacman:_
- _black rectangle - using rect() method_  
- _yelow body - here we use arc() and lineTo() methods_  
- _black eye - with arc() method_

---
