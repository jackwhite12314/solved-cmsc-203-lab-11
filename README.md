Download Link: https://assignmentchef.com/product/solved-cmsc-203-lab-11
<br>
Concepts tested by this program:        NOTE: This lab requires attention to             Inheritance      detail. Follow the following instructions

Interfaces                                                                           carefully.

Polymorphism

Abstract classes

Overriding methods

JUnit Tests

Optimization of functions by estimation

In this project, you will extend the graphing application developed in Lab 8 to estimate the optimal solution(s) to three optimization problems presented in the MATH 181 YouTube videos by Dr Jason Lee entitled “<a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">Math 181 </a><a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">Section 4.6</a><a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">”</a> <a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">(</a><a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz</a><a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">)</a>.  This application will replace functions #1, #2, and #3 from Lab 8 with the three functions developed in the videos for finding local extrema, and iterate over them from a left extent to a right extent to find the minimum or maximum.  It will report the results, and continue on to graph the function using the same methods developed in the previous project.  Based on good object-oriented programming practices, the function definitions can easily be changed, so design and programming tasks are focused on iterating through the function to find the local extrema. <em> </em>

<h1>Operation</h1>

<ul>

 <li>When the user selects the “Optimize a problem” button, the application will display the three problems and ask the user to select one of them to optimize.</li>

</ul>




<ul>

 <li>The application will then ask the user for the left and right extents, which will be the range over which the function is computed.</li>

 <li>Then the application will compute the maximum or minimum, depending on the problem, and display the results.</li>

</ul>




<ul>

 <li>Then the application will graph the function being optimized (as in the previous project).</li>

</ul>




<ul>

 <li>The user may then re-optimize and graph the same or a different function, or exit.</li>

</ul>

<strong> </strong>

<h1>Specifications</h1>

<u>Data Element</u> – (same as Lab 8)




<u>Data Structure</u> – Just as in Lab 8, the abstract class Function holds an abstract method fnValue that the programmer will implement for each sub-class function, and an implemented function fnValueToPlot (provided) that uses fnValue to transform the values to the display coordinate system.

The programmer will implement the three functions which are described in MATH 181 videos entitled “<a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">Math 181 </a><a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">Section 4.6</a><a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">”</a>, each in a class that extends Function.  The estimation approach will approximate local extrema programmatically, <em><u>avoiding</u></em> the need to deal with critical points, the closed interval method, first derivative tests, or second derivative tests.  Note that this approach is not as precise as methods used in calculus.

Each function will have a toString() method that returns a description of the problem, preceded by its index, and an answerString(…) method tailored to each problem.  The answerString() method will take the four values held by the Optimum instance, and display them as appropriate to the specific problem.  Note that not all four values will always be displayed.  For example, in problem #1, z is just a place-holder, and is not displayed.

<u>Data Manager</u> – the OptimizerManager class implements the methods of OptimizerManagerInterface, plus other helper methods as needed.

Just as in Lab 8, the OptimizerManager selects the correct instance of the function based on the integer chosen. It implements its toString method by calling the three function toString methods.  It will receive the user-selected extents of x (left and right) and the grid width in pixels and compute the extents of f(x) (minimum and maximum) as in the previous project.

Then the OptimizerManager will use its optimize() method to iterate from the left extent to the right extent computing the value of the objective function at each point, and remember the minimum or maximum function value found.  OptimizerManager will call the answerString() method for the selected function to provide the problem-specific solution.

Then the OptimizerManager will compute the value of the function within the coordinate system of the panel, just as in Lab 8.  This value will be returned to the GUI to be plotted.

<h2>GUI Driver</h2>

<ul>

 <li>At start-up, a blank panel is displayed with an Exit Button and an Optimize button.</li>

 <li>When the Optimize button is selected, a JOptionPane prompts the user to choose one of the three problems.</li>

 <li>A JOptionPane is then used to select the left and right extents of x (i.e., the minimum and maximum values of x).</li>

 <li>The GUI will create and use a OptimizerManager object to iterate from left to right extents, and save the minimum (or maximum depending on the problem) value of the function. This will be the “extremum” reported in the answerString() method of the chosen function.</li>

 <li>The user will then be allowed to repeat the process for the same or another function, or exit.</li>

</ul>




<strong>           </strong>

<h1>TASK #0 – Study the code</h1>

Familiarize yourself with the code. Note how it is extended from Lab 8.  Compile it and observe that there are errors in the OptimizerManager constructor, because none of the Function classes are implemented.

<h1>TASK #1 – Implement Problem #1</h1>

Create a subclass of the Function.java abstract class named Function1.java which implements the cost function shown below, as well as the other functions required by Function.java.




In MATH 181 (Calculus I) you studied how to optimize problems that could be expressed as a function of one variable.  Three problems were presented in the MATH 181 <strong>YouTube </strong>videos <strong>by Dr Jason Lee </strong>entitled “<a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">Math 181 Section 4.6</a><a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">”</a>.  If you need to review these problems go to the link at:<strong>              </strong><a href="https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz">https://www.youtube.com/playlist?list=PL94c6yqxunA3fz2AJ7TzMehUcb08JuJjz</a>

The first problem is to find the radius and height of a cylindrical can that would hold 2 liters of fluid and minimize the cost of construction, according to different costs for the base and top versus the side.  The following shows the derivation of cost as a function of radius (height is a function of radius also).




So C(r) is the expression of cost as a function of the radius.  Create a subclass of the Function.java abstract class named Function1.java which implements the functions fnValue, toString, answerString, getXVal, getYVal, and getZVal, according to the following descriptions:

<ul>

 <li>fnValue(double x): returns a double which is the cost in terms of x, the specified radius. (Follow the examples in Lab 8 for this method).</li>

 <li>toString(): returns a string describing the problem, e.g., “Minimize the cost of a can that will hold 2 liters of liquid”;</li>

 <li>answerString(double cost, double radius, double height, double z): returns a string that describes the result of the optimization. For problem 1, z is not used, so can be any value.</li>

 <li>getXVal(double x): returns x, the radius</li>

 <li>getYVal(double x): returns the height in terms of the radius, according to the formula derived above in eliminating the variable h.</li>

 <li>getZVal(double x): returns the double -1.0, but is not relevant to problem 1.  This method is included only to conform to the abstract class Function.java, which requires it to be implemented.</li>

</ul>




In order to run the application with only Function1.java implemented, you comment out the following lines:

<ul>

 <li>two lines in OptimizerManager() constructor that attempt to instantiate Function2 and Function3</li>

 <li>two lines in OptimizerManager.toString() that deal with functions 2 and 3</li>

 <li>two lines in OptimizerManager.answerString(…) that deal with functions 2 and 3</li>

</ul>

When running the application, be careful not to select anything other than choice #1 .




<h1>TASK #2 – Implement Problem #2</h1>

The second problem discussed in the above videos is to find the minimum speed with which a dog can run and swim to fetch the ball in the problem below, along with the distance the dog should run along the beach (AB) before jumping in the water.




Using the Pythagorean Theorem, we can sketch out the dog’s path, and assign the variable x to the distance it runs along the beach.




Using the time-distance formula and the known speeds on land and in the water, we find a formula for the time, Q, it takes for the dog to reach the ball as a function of the distance x it runs along the beach.




Create a subclass of the Function.java abstract class named Function2.java which implements the six functions described in Task #1.  In this case, fnValue(double x): should return a double which is the time required in terms of x.




<h1>TASK #3 – Implement Problem #3</h1>

The third problem discussed in the above videos is to find the closest point on a parabola to a given point.




The formula for the distance between an arbitrary point P on the parabola to the point Q is derived as:




As above, create a subclass of the Function.java abstract class named Function3.java which implements the six functions described in Task #1.  In this case, fnValue(double x): should return a double which is the distance between P and Q, according to the above formula for D.

Note that the graph of the distance function is not a parabola, because D is not a quadratic formula.  It does make sense, however, in that there are two points at which the distance D will be minimized, for a negative and a positive x.




<strong>Turn in the following: </strong>

The corrected java src directory in a compressed (zip or tar) file


