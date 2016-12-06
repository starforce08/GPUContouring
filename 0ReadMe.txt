	We are very sorry that the source code belongs to a militery cooperative project, which is not suitable to be open source to the public. However, here are several typical binary executable examples, by which the validity of the our work can be verified.
	The examples can be download from https://github.com/starforce08/GPUContouring. Due to the 25MB size limitation of the uploaded file in GitHub, we have to compress all of the datasets into "Data.zip". So, before running the programs, it is needed to uncompress "Data.zip" to the current folder. Please make sure that the binary executables and the "Data" folder are in the same directory.

	1. The apps "AdaptiveContourWithoutSortingX_Y.exe" show the totally smooth contouring results from very sparse DEM data resource, which is archieved in real time on GPU. Although the results are segments, not continuous contour lines, they are still  good enough for rendering only.
	Here X means the resolution of the raw data is X*X; And Y means the resolution of the finite element mesh (FEM) that we used for segments extration is Y*Y.
	These two apps have been tested on consumer PCs or notebooks with Intel/Nvidia graphic cards.
	Following are some useful manipulation tips:
	Mouse drag with left button down - view move;
	Mouse drag with right button down - view scale;
	Press key "[" or "]" - decrease or increase the "而" value that we used to Cardinal Spline interpolation in the paper;
	Press key "s" or "S" - toggle the OpenGL line-smoothness;
	Press key "v" or "V"- toggle the visibility of the contours;
	Press key "t" or "T"- toggle the visibility of the dem terrain;
	Press key "1" - change the dem interpolation method to nearest;
	Press key "2" - change the dem interpolation method to blinear;
	Press key "3" - change the dem interpolation method to cardinal spline;
	Press key "q" or "Q" - quit the app;
	Some useful information is output in the CMD console, such as the dem interpolation method, current  "而" value, time consumed, and so on.

	The contours in these two apps will adapt with the changes of the "而" value and the dem interpolation method in real time. And ofcourse it can adapt to dynamic grid DEM data too.

	2.  The apps "GPUSortingContourX.exe" show the full stack of our contouring method, include segments extraction by GPU, transform feedback, and CPU "Grid Sorting" algorithm. The raw dataset is quite large, and the results are sorted continuous contour lines. This is not a realtime operation, but it is still much faster than the previous CPU approches.
	Here X means the resolution of the raw DEM data is X*X; and the resolution of the finite element mesh (FEM) that we used for segments extration is also X*X.
	Due to the large dataset and parallel sorting algorithm, we need about 1.5GB free memory both in the cpu system and grapihc card. A grapihc card with Nvidia GTX650 core chips and 2GB memory, or higher, is recommended. An appropriate version of GPU driver which supports OpenGL 3.3 is also need to be installed. And the better the GPU is, the more acceleration our algorithm can get. 
	Following are some useful manipulation tips:
	Mouse drag with left button down - view move;
	Mouse drag with right button down - view scale;
	Press key "[" or "]" - decrease or increase the "而" value that we used for Cardinal Spline interpolation from the paper;
	Press key "s" or "S" - toggle the OpenGL line-smoothness;
	Press key "v" or "V"- toggle the visibility of the contours;
	Press key "t" or "T"- toggle the visibility of the dem terrain;
	Press key "1" - change the dem interpolation method to nearest;
	Press key "2" - change the dem interpolation method to blinear;
	Press key "3" - change the dem interpolation method to cardinal spline;
	Press key "q" or "Q" - quit the app;

	Press key "r" or "R" - re-generte contours based on current dem interpolation and "而" value, and make all of them visiable;
	Preass key "LeftArrow" or "RightArrow" - change the index of a single sorted contour line that will be visiable only, which can confirm the sorting results.

	Some useful information is output in the CMD console, such as the dem interpolation method, current  "而" value, time consumed, the number of segments, and so on.

	You may notice that the number of segments from "GPUSortingContour4096.exe" may verify a little from the result in the paper. This is because in the paper, we used a dataset with ".asc" format for experiment, which is a kind of text formatting. For decreasing the size of data file and transferring via internet conveniently, we convert the origin dataset into ".bt" format with GlobalMapper. However, some little variations in detail may occur during the format conversion. But we believe these differences will not affect the concolusion of the paper. Sorry for any possible inconvenience and misleading caused. 
	
	Best wishes.
	



