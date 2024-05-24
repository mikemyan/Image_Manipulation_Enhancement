# Dithering Image Processing

## Dither an image implementation: Y
## Script command to dither an image: Y
## Dither an image from GUI: Y

## Overview of the implementation

### Model Changes
- A new method, dither(), is declared in BetterImageProcessor interface, and this is where the newer operations were declared by the previous group.
- Implemented this dither() method in the BetterColorImageProcessor class since it implements BetterImageProcessor interface.
- Added a case for dither operation in applyOperation method in the BetterColorImageProcessor class.
- The point above was done so that the dithering operation could be supported properly by existing split image operation.

### Advanced Controller Changes
- Added a new case in executeAdv() method in the AdvancedController to support the script command 'dither'
- This is then linked to the BetterColorImageProcessor model to perform the dither implementation.

### MVCCommandController Changes
- Declared a new method called performDitherOperation() in the IGraphicsController interface.
- This method is then implemented in MVCCommandController to support GUI operation of 'dither'.

### View Changes
- A new button component called ditherButton is created in the ImageGraphicsView class.
- The performDitherOperation() in the IGraphicsController is called in addOps() in ImageGraphicsView to handle all events occur to the ditherButton
- This in turn is connected to the BetterColorImageProcessor model.
