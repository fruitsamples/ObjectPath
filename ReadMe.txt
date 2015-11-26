ObjectPath
==========

"ObjectPath" is a Cocoa sample application that demonstrates how to use the NSPathControl class.  The NSPathControl class is a subclass of NSControl that represents a file system path or virtual path.  This sample is intended to show how to use the different features and aspects of this control including NSPathControlDelegate protocol.


Sample Requirements
The supplied Xcode project will build with Mac OS X 10.6 or later and the build will run on Mac OS X 10.5 or later.


About the Sample
"ObjectPath" shows off the following:

1. Setting a file system path by clicking the "Set Path..." button.

2. Setting a custom path (with icons and specific URLs) by clicking the "Custom Path" checkbox.

3. Control's doubleAction
Sets the double action of this control so users can double-click a path component and reveal the file system object in the Finder.

4. Control Delegate Methods
Customizes the popup menu through the use of:
	- (void)pathControl:(NSPathControl*)pathControl willPopUpMenu:(NSMenu*)menu

Customizes the Open panel through the use of:
	- (void)pathControl:(NSPathControl*)pathControl willDisplayOpenPanel:(NSOpenPanel*)openPanel

5. Drag and Drop
Customizes drag and drop behaviors using the following:

To affect the user interface when a drop occurs by using:
	- (BOOL)pathControl:(NSPathControl*)pathControl acceptDrop:(id <NSDraggingInfo>)info
In this case, after a drop operation occurs the app updates its window, no longer requesting the user to drop something.

To control which file system object can be dragged from the control by using:
	-(BOOL)pathControl:(NSPathControl*)pathControl
		shouldDragPathComponentCell:(NSPathComponentCell*)pathComponentCell withPasteboard:(NSPasteboard*)pasteboard
In this case, volumes are arbitrarily chosen as objects you cannot drag.

To validate a drop operation on the control by using:
	- (NSDragOperation)pathControl:(NSPathControl*)pathControl validateDrop:(id <NSDraggingInfo>)info


Using the Sample
Simply build and run the sample using Xcode.  Drag any file system object from the Finder to the drop area in the window.

	
Changes from Previous Versions
1.0 - First Release
1.1 - Fixed static analyzer warnings, upgraded for Snow Leopard.


Feedback and Bug Reports
Please send all feedback about this sample to:
	<http://developer.apple.com/contact/feedback.html>

Please submit any bug reports about this sample to:
	<http://developer.apple.com/bugreporter>