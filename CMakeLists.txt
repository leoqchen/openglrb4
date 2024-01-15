cmake_minimum_required(VERSION 3.4...3.20 FATAL_ERROR)
project(hello_project)

#set(CMAKE_VERBOSE_MAKEFILE ON)
set(O -O0)
add_compile_options(${O} -g -Wall)

add_library(
  readImage
  STATIC
  readImage.c
)

link_libraries(
  glut
  GLU
  GL
  Xmu
  Xext
  X11
  m
  readImage
)

# This file lists the programs that are refereced in the OpenGL Programming
# Guide, Fourth Edition, by chapter.  For each program, the version of
# OpenGL that is required is listed with the program.

set(targets
  # Chapter 1: Introduction to OpenGL
  hello		#(1.0)
  double	#(1.0)

  # Chapter 2: State Management and Drawing Geometric Objects
  lines		#(1.0)
  polys		#(1.0)
  varray	#(1.1)
  mvarray	#(1.4)

  # Chapter 3: Vieweing
  cube		#(1.0)
  model		#(1.0)
  clip		#(1.0)
  planet	#(1.0)
  robot		#(1.0)
  unproject	#(1.1)

  # Chapter 4: Color
  smooth	#(1.0)

  # Chapter 5: Lighting
  light		#(1.0)
  movelight	#(1.0)
  material	#(1.0)
  colormat	#(1.1)
  scene		#(1.0)

  # Chapter 6: Blending, Antialiasing, Fog, and Polygon Offset
  blendeqn	#(1.3 or ARB_imaging_subset)
  alpha		#(1.0)
  alpha3D	#(1.1)
  aargb		#(1.1)
  aaindex	#(1.1)
  multisamp	#(1.3)
  fog		#(1.0)
  fogindex	#(1.0)
  fogcoord	#(1.4)
  pointp	#(1.4)
  polyoff	#(1.1)

  # Chapter 7: Display Lists
  torus		#(1.0)
  list		#(1.0)
  stroke	#(1.0)

  # Chapter 8: Drawing Pixels, Bitmaps, Fonts, and Images
  drawf		#(1.0)
  font		#(1.0)
  image		#(1.1)
  colortable	#(ARB_imaging_subset)
  convolution	#(ARB_imaging_subset)
  colormatrix	#(ARB_imaging_subset)
  histogram	#(ARB_imaging_subset)
  minmax	#(ARB_imaging_subset)

  # Chapter 9: Texture Mapping
  checker	#(1.0)
  texsub	#(1.1)
  texture3d	#(1.2)
  mipmap	#(1.0)
  texbind	#(1.1)
  texgen	#(1.1)
  cubemap	#(1.3)
  multitex	#(1.3 or ARB_multitexture)
  combiner	#(1.3)
  shadowmap	#(1.4)
  wrap
  texprox	#(1.1)

  # Chapter 10: The Framebuffer
  stencil	#(1.0)
  accpersp	#(1.0)
  accanti	#(1.0)
  dof		#(1.0)

  # Chapter 11: Tessellators and Quadrics
  tess		#(1.1)
  tesswind	#(1.1)
  quadric	#(1.1)

  # Chapter 12: Evaluators and NURBS
  bezcurve	#(1.1)
  bezsurf	#(1.1)
  bezmesh	#(1.1)
  texturesurf	#(1.1)
  surface	#(1.1)
  surfpoints	#(1.2)
  trim		#(1.1)

  # Chapter 13: Selection and Feedback
  select	#(1.1)
  picksquare	#(1.0)
  pickdepth	#(1.0)
  feedback	#(1.0)

  # Color Plates:
  teapots		#(1.1)
)

foreach(target ${targets})
  add_executable(${target} ${target}.c)
endforeach(target)
