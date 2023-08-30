# RandomRouteGenerator
A Geographic Information System (GIS) - a map software that was developed in C++ along with a team of two others. This software employs the OpenStreetMap database and offers a wide array of features. Among its capabilities are determining the shortest route between two points, providing step-by-step directions for the entire journey, and more. These functionalities were made possible by developing some custom algorithms and some standard algorithms including the Dijkstra and A* algorithms.   

True to its name, its primary purpose is to generate random routes based on a specified starting point and desired travel distance. This application is a fully operational software complete with a functional Graphical User Interface (GUI) that is built using the EZGL and GTK libraries.  

___NOTE --> I will be using the terms "map software" and "GIS" interchangeably throughout this README___

<img width="700" alt="image" src="https://github.com/snehalsobti/RandomRouteGenerator/assets/106326726/21a876cc-18cf-4da7-ab8b-b5d1022be8e2">

## Disclaimer
This repository explains the functionalities of this GIS software that I developed during a Software Design and Communication course in my second year of Computer Engineering at the University of Toronto. The README file also includes screenshots and videos that illustrate the functionalities of the map. As this project is part of an academic course at the University of Toronto, I cannot publicly share the actual code for the GIS software to prevent students from committing Academic Integrity violations by copying it.   

Employers are encouraged to ask me for the Code if they are considering hiring me.   

## Motivation
We chose the idea of "Random Routes" for our GIS project to make things more interesting during activities like exercise, walks, and runs. It's also perfect for breaking the routine of taking the same old routes to work or school every day. Imagine if you could mix things up and add a bit of excitement to your daily travels! This is all about enjoying the outdoors, staying active, and saying goodbye to the boredom of sticking to the same paths. It's designed for folks who love staying fit and exploring the city.  

## Features of the map - Usability and Responsiveness
This section lists the features and functionalities that this map software offers. Moreover, it also emphasizes on how these features improve the usability and the responsiveness of the map.

### Basic functionality buttons
* The user can use the mouse or the zoom-in, zoom-out, zoom-fit and four arrow buttons for the zooming and panning functionalities. As we zoom sufficiently in, the map also shows street names, the one-way or two-way status of the streets and the names of various kinds of landmarks.
* There is a functionality for the user to change the city. The user can select from a list of around 20 cities to open the map for.
* A _Help_ button shows detailed instructions on how to use the map software effectively.
* There is also a _Reset Highlights_ button which clears all the highlighted streets and intersections on the map.

<img src="media/Basic_Functionalities.gif" width="700">

### Creative Icons and Filtering for POIs (Points Of Interest)
The GIS makes use of creative and eye-catching icons to represent different landmarks such as _bus_ for bus stations, _book_ for libraries, _plus_ symbol for hospitals, _coffee cup_ for cafe and restaurants, and so on.... This allows the user to distinctively see one or more of the locations that they wish to visit. Moreover, the map also provides an option to specifically pick and display only one type of landmarks (such as selecting only the hospitals).

<img width="700" alt="image" src="https://github.com/snehalsobti/RandomRouteGenerator/assets/106326726/654a3e2a-f51d-4053-af0b-c7c822c118d5">
   
POI filtering helps in reducing the chaos of icons and details on the map's interface. This in turn, helps increase the responsiveness of the map. The map loads faster while zoomed in --> around 400 milliseconds faster for Toronto when one POI type is selected vs drawing all the POIs.  

<img width="700" alt="image" src="https://github.com/snehalsobti/RandomRouteGenerator/assets/106326726/caf4a582-8c71-4cb1-8c74-e416e532a931">


### Clicking anywhere on the map
The user can click the mouse on a specific location on the map and the intersection closest to the mouse click will be highlighted. It automatically zooms into the enlarged view of the neighbourhood near the mouse click. Moreover, it shows a popup message displaying the name of the closest intersection and the closest landmark. For example, if the user wants to visit a cafe near a desired location, they can select _cafe_ in the POI filter and click on the specific location on the map to get the desired information. 

<img src="media/POI.gif" width="700">
<img width="700" alt="image" src="https://github.com/snehalsobti/RandomRouteGenerator/assets/106326726/e0bfa971-6eaf-4992-9140-68433d34d21f">


### Searching for an intersection
The user can enter two street names and if those two streets intersect somewhere, that intersection gets highlighted. Again, the GIS supports automatic zooming in - which means that the map automatically gets zoomed in to the enlarged view of the neighbourhood near the intersection. Furthermore, if the two streets do not intersect anywhere in the entire city, the map warns the user with a small message.

<img src="media/Intersections.gif" width="700">

### Night Mode
Night Mode has been added to the map software after doing an ample amount of research on the colour combinations that are less harmful to the human eye at night and are suitable for dark mode of map software.

<img src="media/NightMode.gif" width="700">

### Random Route Generator
The user needs to select an intersection and input the distance (in metres) that they want to travel. The random route generator generates a random route each time the _Find Random Route_ button is pressed. Again, the map takes care of automatic zooming into and focusing on the enlarged view of the random route. This feature fulfills the main purpose of this software which is to eradicate the boredom of the same usual routes. And in terms of responsiveness, the random route generation happens within milliseconds.   

<img src="media/RandomRoute.gif" width="700">

### Getting Directions
The map software allows the user to get directions in two ways:
* Enter two street names for the starting intersection and two street names for the destination, or
* Click at two locations on the map and locations closest to the mouse clicks get marked as the start and end locations.
On selecting two intersections, the GIS suggests and marks the shortest route between the start and end locations. For this purpose, I have implemented A* Algorithm to make the process of finding the shortest path faster i.e more responsive. The map does the automatic zooming in and also, marks the start and end locations with appropriate icons.

In addition to this, the GIS provides detailed explanation of the exact route from start location to the end location. The algorithm at the back end takes care of minute details such as _sharp_ or _non-sharp_ turns or if the turn is not too significant, it is mentioned as _keeping straight_ by the software.

<img src="media/GettingDirections.gif" width="700">

### Dynamic Zooming and Progressive Loading
Dynamic Zooming means showing optimum details on different zooming levels. It involves the implementation of progressive loading of different features on the map with increasing zooming-in levels. For example, when the map is at normal zoom level, only the highways and major streets of the city are displayed but with zooming in, there is a progressive loading of rest of the primary, secondary, residential and small streets. Similarly, not all the water bodies, green spaces, buildings and intersections are shown at normal zoom level. As the user zooms in, more and more features on the map get unfolded. Moreover, the street names, streets' one-way or two-way status and the landmark names are only shown when the map is sufficiently zoomed in. Not only this, but the map also avoids drawing all those landmarks and intersections which are out of the visible area of the screen.

<img src="media/DynamicZooming.gif" width="700">
    
Dynamic Zooming enables the map to zoom in a lot faster compared to the scenario when map would have needed to display all the features at once. This is because the map needs to call a 'drawMap()' function each time the map is zoomed-in or zoomed-out. So, when there is omission of millions of buildings, landmarks, and much more features, the map loads in a much efficient way.

<img width="700" alt="image" src="https://github.com/snehalsobti/RandomRouteGenerator/assets/106326726/4f7ab7ed-5cb9-42d4-8001-fb41f4a8cfcd">

## Responsiveness of Shortest Path Finding Algorithm
The following snapshots illustrate the time being taken for the map software to respond when provided with the task of finding the shortest path between two destinations which are on the extreme corners of the big cities.

<img width="700" alt="image" src="https://github.com/snehalsobti/RandomRouteGenerator/assets/106326726/487ae0f5-cf84-4c03-b4c9-4b019bcc438d">
<img width="700" alt="image" src="https://github.com/snehalsobti/RandomRouteGenerator/assets/106326726/fb0b4dc1-ae8c-4f9e-b317-e6594cb6c02c">

## Enhanced Random Route Finding Algorithm   
As an add-on to the existing software's capabilities, we had also proposed an enhanced random route finding algorithm which allows the user to input start and end locations and also various stops/landmarks in between the two locations. Following is the pseudocode that is used in the algorithm for finding a random route when a user provides the start location and end location, and also provides the time they wish to walk for. If the time is less than the shortest path between the two locations, this algorithm will generate the shortest path.
```
time_left = time input by user
shortest_path_time = shortest path time between start and end location   
while (shortest_path_time <= time_left)   
{   
	find a random route of some small distance (say, 100 metres)
	time_left = time input by user - time taken for the above calculated random route
	shortest_path_time = shortest path time from current location to destination
}
go on the shortest path from current location to destination
```
_Note - for user_speed - typical human walk speed is considered_
_Note - for shortest path finding – A* Algorithm is used_

In this enhanced random route-finding algorithm, the map software also allows the user to input various kinds of stops/landmarks that they wish to visit on their journey. For example, the user wishes to visit a cafe (Stop 1) and a lake (Stop 2) in their journey. Then, basically, the algorithm whose pseudocode has been explained above, will be used three times --> once for start location and Stop 1, Stop 1 and Stop 2 and then, Stop 2 and end location. I also used the concept of ratios for distributing the time for all the paths proportionately. The following diagram tries to illustrate an example of two stops input by the user and when the user wants to walk for 90 minutes. So, we calculate the shortest path times for all the paths (there are three --> Start to Stop 1, Stop 1 to Stop 2 and Stop 2 to End) which comes out to be in the ratio 2:1:3. So, the algorithm will divide the 90 minutes (that the user has input) in the ratio of 2:1:3 and accordingly, will generate three random paths of times 30, 15 and 45 minutes which when combined, gives a single random route of 90 minutes.   

<img width="700" alt="image" src="https://github.com/snehalsobti/RandomRouteGenerator/assets/106326726/41a9ca39-9c38-4e23-a0f1-64d184834e9d">
