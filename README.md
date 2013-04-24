jsMovie v 1.4.4
=======

Konsultaner GmbH & Co. KG - Richard Burkhardt
version 1.4.4

This is a jQuery-plugin for jQuery 1.4+ (tested). This plugin enables you
to play image sequences without flash or HTML5 with the benefit of playing
your movies backwards and having PNG images animated.

@TODO: streaming of content
@TODO: html5 / canvas for mobile devices and graphic acceleration (research)
@TODO: preload verbose

SETTINGS
===================================================================================================================
@param images		- array of images that are played in this order ! important image names my not contain any spaces  
@param sequence		- string like image####.jpg which automatically fills the images array,  
			  image#.jpg would render like image123.jpg  
			  image#####.jpg would render like image00123.jpg ! important image names my not contain any spaces  
@param from		- integer value that defines the start of the sequence  
@param to		- integer value that defines the end of the sequence  
@param step		- integer value that defines the step length of the sequence. 2 would render every second frame  
@param folder		- string that contains the image folder  
@param grid		- object that contains the structure of an image, i.e. {height:800,width:600,rows:1,columns:1}  
@param grid.height	- integer value that represents the image height of the resulting frame in a multi-frame image  
@param grid.width	- integer value that represents the image width of the resulting frame in a multi-frame image  
@param grid.rows	- integer value that represents the number of frame rows in a multi-frame image  
@param grid.columns	- integer value that represents the number of frame columns in a multi-frame image  
@param loader		- object that contains the parameters for the image preloader  
@param loader.path	- string that contains the preloader image path  
@param loader.height	- integer value that represents the preloader height  
@param loader.width	- integer value that represents the preloader width  
@param loader.rows	- integer value that represents the number of frame rows in the multi-frame preloader image  
@param loader.columns	- integer value that represents the number of frame columns in the multi-frame preloader image  
@param fps		- float value that represents the frames per second rate  
@param width		- integer value that scales the target frame to the wanted player width  
@param height		- integer value that scales the target frame to the wanted player height  
@param loadParallel 	- integer value that represents the amount of pictures that are parallely loaded  
@param repeat		- boolean value enables or disables the auto repeat function  
@param playOnLoad	- boolean value. if set to true the video atomaticly starts to play after the frames are loaded  
@param performStop		-	boolean value. if set to true the video doesn't stop and return to the first frame. It will pause  
@param playBackwards	- boolean value. if set to true the video plays backwards  
@param showPreLoader	- boolean value. if set to true the preloader will be displayed  
@param verbose		- boolean value. if set to true the player will trigger the verbose event  

METHODS
=====================================================================================================================
`init` 	        - initialises the plugin	- $(".movie").jsMovie({});  
`option`	    - sets an option	- $(".movie").jsMovie("option","repeat",true);  
`realFps`	    - returns the real frames pre second	- $(".movie").jsMovie("realFps");  
`play`	        - $(".movie").jsMovie("play");  
                - $(".movie").jsMovie("play",1,80,false,false);  
`pause`	        - $(".movie").jsMovie("pause");  
`stop`	        - $(".movie").jsMovie("stop");  
`playUntil`     - $(".movie").jsMovie("playUntil",10); !DEPRECATED - use play instead  
`nextFrame`     - $(".movie").jsMovie("nextFrame");  
`previousFrame` - $(".movie").jsMovie("previousFrame");  
`playClip`      - $(".movie").jsMovie("playClip","startClip");  
                - $(".movie").jsMovie("playClip",clip);  
                - $(".movie").jsMovie("playClip",function(){return {start:10,end:20,pause:1000} });  
                - $(".movie").jsMovie("playClip",3);  
`playClip`      - $(".movie").jsMovie("playClips");  
`addClip`       - $(".movie").jsMovie("addClip","startClip",4,13,1000); - defines a clip with start frame 4 and end frame 12 with a pause of 1 second in the end  
`getClip`       - $(".movie").jsMovie("addClip"); - returns the clip object  
`removeClip`    - $(".movie").jsMovie("removeClip","startClip"); - returns an array with the clip objects  
`getClipQueue`  - $(".movie").jsMovie("getClipQueue")  
`gotoFrame`     - $(".movie").jsMovie("gotoFrame",20);  
`destroy`	    - $(".movie").jsMovie("destroy");  
`throwError`    - $(".movie").jsMovie("throwError",1);  

EVENTS
=====================================================================================================================
  `play`		- is triggered when the movie starts playing  
  `pause`		- is triggered when the movie pauses  
  `stop`		- is triggered when the movie stops  
  `ended`		- is triggered when a clip played its last frame  
  `playing`	    - is triggered when the movie enters a frame  
  `loaded`	    - is triggered when the movie has finished its loading process  
  `verbose`	    - is triggered when the movie outputs a verbose, the callback has an extra argument like function(e,output){} which contains the text  
