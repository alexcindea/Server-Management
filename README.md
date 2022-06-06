# Server-Management
   This application is a server management utility, where users can store the servers on their network, and check their availability. The first part of this assignment meant designing the database, ensuring a conection and testing it. The Resource pack contains the logic for operation on the database. Model pack contains the model for the database. Repositories pack contains the interface for accessing the database. Controllers pack contains the controller which maps the operation executed on db.
   
![EntityDiagram (1)](https://user-images.githubusercontent.com/72449923/172213084-2d1974be-683c-47a3-814d-25a1d6f95f28.png)


   At a second commit I updated the project with more endopoints, the user now being able to do a multitude of operations for managing their server. We now had more GET methods, which could return a list of the severs, or by a specific id. The ServerResource class  contains all the logic for calling these methods. I also implemented a dummy factory pattern which would be used for further advancing the apps capabilities. For the implementation of the factory pattern, I implemented an enum which classifies the types of servers that can be created. The model package contains an entity class for the server as well as a Response class, which is used as Decorator of sorts. Every communication with the server is wrapped in the Response object, which adds some extra information to the requests, like a specific message and a timestamp. The repo is reponsible for communication with the database, while the serverResource controls the whole application, acting like a facade controller.Model–view–controller (MVC) is a software architectural pattern commonly used for developing user interfaces that divide the related program logic into three interconnected elements. This is done to separate internal representations of information from the ways information is presented to and accepted from the user. In it's implementation it contains all the main actions that the application can perform, with the help of the serverService. The serverService is an interface that represents the contract of communication between the controller and the serviceImplementation, therefore fulfiling SOLID principles. Inside the server service we handle all the functions that the server can take. Here, with the create method we receive a server as a parameter, and the service assigns a IMG url and calls the repo to save the server in the database. The ping method looks with the repo for the server with the specified ip address, and checks if it is reachable with a specific function. We can also list, add, get, update, and delete servers by ip.
![Package server (1)](https://user-images.githubusercontent.com/72449923/172213077-f40b9e7b-300b-4bf2-b116-990059e52b6a.png)


   For the frontend part of the assignment, an android app was created. We were required to use kotlin for our development, and we were tasked with creating a user interface that would be able to communicate with the Backend that we implemented the previous assignment.Firstly we created a mapping for receiving data from the backend, on this case a Server class. We used Retrofit to be able to make Api Calls. My implementation for the user interface is represented by a listView, as the user needs to be able to manage all his servers. Therefore, when the application is started, it makes an asynchronous API call to the backend trough Retrofit, wich is a GET that returns all the saved servers from the database. The call is asynchronous so the UI doesn't freeze it's UI thread.
    Once loaded, the listed servers can be clicked in order to display the specific details of a server. I also added a button that when pressed, ideally would make an API Post call in order to add another server to the database. In order to create the listing of the servers, I had to implement a ListAdapter that would populate the list_activity.xml with the data passed as an ArrayList.
    For every activity which was created in layouts folder will be created an xml file for develop the design of the page. Android studio offer two ways to yo that task, first write code in xml file, second way is drag and drop method and create your own design. Also we have an xml file where are stored references to all activities and useer permissions. Android studio offer to you the posibility to develop the background image of your application for every page, draw objects whic will be displayed. You can instantiate colors for your app and create some theme like light mode theme or dark nmode theme. In the project structure exist o specific folder for scripts and instatiate libraries for your project. Main files are build.gradle app module, build.gradle project module and gradle.properties.

    This part of the project was pushed into another commit because this part was developed in android studio.
