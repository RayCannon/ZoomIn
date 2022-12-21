# ZoomIn
Animated zoom into a Mandelbrot set using Dyalog APL Isolates 

(See https://youtu.be/7aUOAklV2AM for a 5 minute video)

This APL workspace was initially written under Dyalog APL/W-64 Version 18.0.40684 and expects to run under a Microsoft Windows OS.

For speed, it uses Isolates if multiple processors are available on the machine. 
It expects to find the Dyalog supplied  ws "isolate.dws" in the wspath.

The top level function is "lx".

lx  ⍝ Mandelbrot with Isolates

Mandelbrot ⍝ Mandelbrot for Dyalog APL

DrawGrid ⍝ Draw a  grid of dotted lines on matrix<mat>

LeftCenter  ⍝ Some points are "known" to either be inside the black hole, or outside of it. Calculate the left and center columns and the pinch row.
 
SplitUp  ⍝ split vectors y and x into sets for each processor

BuildGlobals ⍝ build global values in namespace G 

ShowGrid ⍝ Build and show the form "f" and the bitmap "bmout"

StartingPoint ⍝ return some starting point values 

BuildIndx ⍝ return a vector of indexes for each animation of the zoom

NearBy ⍝ return 1 if ⍺ is within 1 of ⍵

ZoomTo  ⍝ Zoom in on the center of the bitmap

ManCalcColor ⍝ Calculate the mandelbrot value

Symmetry  ⍝ The Mandelbrot set is symmetrical about the real axis so only parts in one half need ever be calculated

NearEdge  ⍝ add extra points inside black area but only near its edge

BuildPos  ⍝ Build a set of positions in complex plane for each pixel from min to max

Secs      ⍝ second from time stamp

TrapLoop  ⍝ trapped cover function for main loop

CycleMap  ⍝ cycle the colours shown in the form "f"

NewComplex ⍝ Return new positions in complex plane

init_isolates ⍝ called upon initialization, or whenever user changes number of processors to use

BuildBits  ⍝ Build colour index matrix

mc   ⍝Calculate the mandelbrot value

CalcMan ⍝ Calculate unresolved points in matrix <mat>

BuildCMap ⍝ Build Colour Map - Return a CMap "table of 256 colours"

Normalise  ⍝ Normalise the values used by the Bitmap as indexes into the colour map

StartTimer ⍝ Start Time

MainLoop   ⍝ loop for each factor of 2 zoomed into the mandelbrot image

Expand  ⍝ expand quarter sized mat to full  size

NewDetails ⍝ Return text used in Caption

