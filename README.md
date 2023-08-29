# RandomRouteGenerator
A Geographic Information System (GIS) - a map software that was developed in C++ along with a team of two others. This software employs the OpenStreetMap database and offers a wide array of features. Among its capabilities are determining the shortest route between two points, providing step-by-step directions for the entire journey, and more. These functionalities were made possible by developing custom algorithms inspired by the Dijkstra and A* algorithms.   

True to its name, its primary purpose is to generate random routes based on a specified starting point and desired travel distance. This application is a fully operational software complete with a functional Graphical User Interface (GUI) that is built using the EZGL and GTK libraries. (screenshot here)

___I will be using the terms "map software" and "GIS" interchangeably throughout this README___

## Disclaimer
This repository explains the functionalities of this GIS software that I developed during a Software Design and Communication course in my second year of Computer Engineering at the University of Toronto. The README file also includes screenshots and videos that illustrate the functionalities of the map. As this project is part of an academic course at the University of Toronto, I cannot publicly share the actual code for the GIS software to prevent students from committing Academic Integrity violations by copying it.   

Employers are encouraged to ask me for the Code if they are considering hiring me.   

## Motivation
We chose the idea of "Random Routes" for our GIS project to make things more interesting during activities like exercise, walks, and runs. It's also perfect for breaking the routine of taking the same old routes to work or school every day. Imagine if you could mix things up and add a bit of excitement to your daily travels! This is all about enjoying the outdoors, staying active, and saying goodbye to the boredom of sticking to the same paths. It's designed for folks who love staying fit and exploring the city.  

## Features of the map along with their Usability and Responsiveness
This sec

### Basic functionality buttons (Screenshot here)
* The user can use the mouse or the zoom-in, zoom-out, zoom-fit and four arrow buttons for the zooming and panning functionalities. (screenshot here)
* It also allows the user to change the city. The user can select from a list of around 20 cities to open the map for.
* A _Help_ button shows detailed instructions on how to use the map software effectively.
* There is also a _Reset Highlights_ button which clears all the highlighted streets and intersections on the map.

### Clicking anywhere on the map
The user can click the mouse on a specific location on the map and the intersection closest to the mouse click will be highlighted. Moreover, it also shows a pop


### Searching for an intersection
The map software provides two ways to select an intersection. When an intersection is selected, it gets highlighted. (Screenshot here)   
*   (video here)
* The user can enter two street names and if those two streets intersect somewhere, that intersection gets highlighted
In both the above-mentioned scenarios, the GIS supports automatic zooming in - which means that the map automatically gets zoomed in to the enlarged view of the neighbourhood near the intersection.

### Night Mode
Night Mode has been added to the map software after doing an ample amount of research on the colour combinations being used by other map software such as Apple Maps, Google Maps and also, choosing the colours which are less glowing to the human eye. (Screenshot here)

### Random Route Generator
The user needs to select an intersection and input the distance (in metres) that they want to travel. The random route generator generates a random route each time the _Find Random Route_ button is pressed. Again, the map takes care of automatic zooming into and focusing on the enlarged view of the random route. (Video here)   

### Getting Directions
The map software allows the user to get directions in two ways:
* Enter two street names for the starting intersection and two street names for the destination, or
* Click at two locations on the map and locations closest to the mouse clicks get marked as the start and end locations.
On selecting two intersections, the GIS suggests and marks the shortest route between the start and end locations. For this purpose, I have implemented A* Algorithm to make the process of finding the shortest path faster i.e more responsive. The map does the automatic zooming in and also, marks the start and end locations with appropriate icons.    
In addition to this, the GIS provides detailed explanation of the exact route from start location to the end location. The algorithm at the back end takes care of minute details such as _sharp_ or _non-sharp_ turns or if the turn is not too significant, it is mentioned as _keeping straight_ by the software. (Video here)

### Creative Icons and Filtering for POIs (Points Of Interest)
The GIS makes use of creative and eye-catching icons to represent different landmarks such as _bus_ for bus stations, _book_ for libraries, _plus_ symbol for hospitals, _coffee cup_ for cafe and restaurants, and so on.... This allows the user to distinctively see one or more of the locations that they wish to visit. Moreover, the map also provides an option to specifically pick and display only one type of landmarks (such as selecting only the hospitals). (Video here)

### Dynamic Zooming and Progressive Loading
Dynamic Zooming means showing optimum details on different zooming levels. It involves the implementation of progressive loading of different features on the map with increasing zooming-in levels. For example, when the map is at normal zoom level, only the highways and major streets of the city are displayed but with zooming in, there is a progressive loading of rest of the primary, secondary, residential and small streets. Similarly, not all the water bodies, green spaces, buildings and intersections are shown at normal zoom level. As the user zooms in, more and more features on the map get unfolded. Moreover, the street names, streets' one-way or two-way status and the landmark names are only shown when the map is sufficiently zoomed in. (Video here)   





