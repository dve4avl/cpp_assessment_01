
A class should be implemented which is able to (linearly) interpolate between a set of given points.

The images show exemplarily what is provided as an one dimensional input, and what the resulting output should look like for 2 points interpolated in between 2 datapoints.

4 classes shall be implemented

-   "AbstractInterpolator" which acts as a base class for "LinearInterpolator"
-   "LinearInterpolator" which implements the actual interpolation (derived from AbstractInterpolator)
-   "CoordinatesImporter" which parses the coordinates in the given .csv file
-   "Coordinate" which holds data for an n-dimensional Coordinate of arbitrary datatype (in that case doubles)

**The following tasks shall be performed:**

-   "CoordinatesImporter" parses the coordinates in the given .csv and stores them in the "Coordinate" class.  
    Please play attention that n-dimensional coordinates may be used. In that specific .csv 3D-coordinates are given
-   "CoordinatesImporter" implements a method with the following signature, returning a list of Coordinates:  
    std::vector<T> import(const std::string& filePath);
-   Every coordinate (line) parsed from the input file should only be instantiated once on the heap

The Coordinates therefore should only exist once in the application context for the whole application runtime
-   The "Coordinate" class should overload the insertion operator << to provide formatted output for the datatype
-   The "Coordinate" datatype should support a constructor with an initializer list as argument
e.g. you should be able to write Coordinate<double> coord{ 0.0, 0.0, 0.0 };
-   The "AbstractInterpolator" class declares the following method which is also implemented by "LinearInterpolator"  
    virtual std::vector<T> interpolate(const std::vector<T> coordinates, const unsigned numberOfInterpolatedPoints) const = 0;  
    In that example T will be of type "Coordinate<E>"
The return value is a vector with interpolated values
-   "LinearInterpolator" should work independently of the number of dimensions supported by the "Coordinate" datatype.
-   "LinearInterpolator" interpolates numberOfInterpolatedPoints points as illustrated in the pictures. In the given example numberOfInterpolatedPoints is 2;
-   Print a list of the interpolated coordinates

**General:**

-   Modern C++ features (C++11, C++14, C++17) should be used whenever possible.
-   The example should be kept simple, but still elegant. No overengineering!
-   No 3rd parts libraries are allowed. Only C++ standard libraries.
-   Implement efficient error and exception handling

**Compiling:**

- You can choose an IDE of your choice.
- The exercise can be fulfilled on an OS of your choice.

**Hints:**

-   Operator overloading in the "Coordinates" class may lead to a more elegant and simple design, depending on how the implementation of the "LinearInterpolator" class looks like
-   If something in the instructions is not clear, just keep going with what you think is correct. That's not a problem at all!

**Delivery:**

-   Please note that the time duration for this exercise is important
-   Time starts from the point when the exercise is downloaded
-   Time ends when the source files are uploaded to the following github repository  
    [https://github.com/dve4avl/cpp_assessment_01](https://github.com/dve4avl/cpp_assessment_01)

**Required Result:**

A sample output for 3 interpolation points for the given coordinates.csv may look like the following:

0.000 - 0.000 - 0.000  
0.000 - 0.250 - 0.000  
0.000 - 0.500 - 0.000  
0.000 - 0.750 - 0.000  
0.000 - 1.000 - 0.000  
0.250 - 0.750 - 0.250  
0.500 - 0.500 - 0.500  
0.750 - 0.250 - 0.750  
1.000 - 0.000 - 1.000  
1.000 - 0.250 - 1.000  
1.000 - 0.500 - 1.000  
1.000 - 0.750 - 1.000  
1.000 - 1.000 - 1.000  
