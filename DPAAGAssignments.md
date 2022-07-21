## App Architecture Assignment

Write a small excerpt on each of the aboved architectural patterns and discuss how they are different.
Give a list of reasons why to use one over the other.

MVC
Stading for Model-View-Controller, MVC is an architectural pettern where the model objects can have to-one and to-many relationships with other model objects, and so sometimes the model layer on an application effectively is on or more object graphs and in which, ideally, a model object should have no explicit conection to the view objects. This might be one of the most significant differences between traditional MVC and Spple's MVC pattern, since traditional MVC llows, and actually encourages, direct communication between the model and the view objects.
The issue with MVC is that the controller ends up doing all the job, form handling user interactions, to setting up views, doing network calls, data parsing ane so on. This is also known as Massive View controller. This results on breaking the single responsibility principle.

MVP
The MVP architecture comes to improve is similar to MVC, but addresses the Single responsability breaking issue by adding the main component which is Presenter. here the ViewController is consiered as a veiw, which means it will include onl the view ralated code, nothing more, and all logic will be implemented in the presenter.
The Presenter will be in charge of all the logic, including responding to user actions and udating the UI (via delegare), and the most important is that our presenter will not be UIKit dependent, which means sell isolated, hence easily testable.


MVVM
MVVM layers are:
* Model: This layer is responsible for the abstraction of the data sources Model and ViewModel work together to get and save the data.
* View: The purpose of this layer is to inform the ViewModel about the user's action. This layer observes the ViewModel and does not contain any kind of application logic.
* ViewModel: It exposes those data streams which are relevant to the View. Moreover, it serves as a link between the Model and the View.


MVVM vs. MVP
MVVM pattern has some similarities with the MVP design pattern as the Presenter role is played by the ViewModel. However, the drawbacks of the MVP patter n has been solved by MVVM in the following ways:

* ViewModel does not hold any kind of reference to the View.
* Many to 1 relationship existebetween View and ViewModel.
* No tirggerign methods to update the View.

MVVVM vs MVC
* To be independently testable, and especially reusable when needed, a view-model has no idea what view is displayin it , but more imporatnly no idea hwere its data is coming from.
* In practice Controllers remove most of the logic, form the ViewModel, that requires unit testing. The VM then becomes a dumb container that requires litltle, if any, testing . Thisis a good thing as the VM is just a bridge, between the designer and the coder, so whould be kept simple.
* Even in MVVM, controllers will typically contain all processing logic and decide what data to display in which views usign which view models.

VIPER 
The VIPER architecturural pattern differes from the rest in the fact that it includes elements from most of the above patterns. VIPER is an achronym, that means:
    * View - Dispñplays what it its told by the Presenter and relays user input back to the Presenter.
    * Interactor - Contains the business logic as specified by a use case.
    * Presenter - Cpontains view logic for preparing content for display, which is received from the Interactor) and for reacting to user inputs (by requesting more data from the Interactor).
    * Entity - Contains basic model objects used by the Interactor.
    * Routing - Contains the navigation logic for describin which screens are shown in which order.
    
This separation of tasks is a result of the effort to conform to the SINGLE RESPONSIBILITY PRINCIPLE.

                WIREFRAME
                    |
                    |
    VIEW    ->  PRESENTER    ->  INTERACTOR  ->  (1:n)   ->  ENTITY
                                    |
                                    |
                                DATA STORE
                                


## Design Patterns Assignment

Write a small paragraph about different design patterns. (1 paragraph per) Particularly Singleton, Factory, Facade, Decorator, and two others of your choice. Explain what they are and why/when they should be used.

The Singleton design pattern consists on having only one instance of an object in the whole Application. Hence, this instance is shared throughout all the isntances in the Application where the information contained in this object is required. This allows developers to make Applications more memory efficient since only 1 instance of a class is generated. The drawbacks from this apporach are mainly related to multi-threading since, if there are many objects that want to get and modify information from the same instance, issues like a deadlocks, race conditions and livelocks. Analogy: The office of the President of the US is a Singleton. There can be at most one active presiden at any given time. Regardless of the personal identity of the acrtive president, the title, "The President of the US" is a global point of acces that identifies the person in the office.

Factory
In the Factory pattern, we create an object without exposing the creation logic to the client and refer to newly created object using a common Interface. Example: Both Truck and Ship classes should implement the Transport interface, which declares a method called deliver. each class implements this method differently: trucks deliver cargo by land, ships deliver cargo by sea. The factory method  the RoadLogistics class returns truck objects, whereas the factory method in the SeaLogistics class returns ships.

Facade
The Facade pattern involves a single class which provides simplified methods required by the client and delegates calls to methods of existing system classes. Like the Movies API. Analogy: when you call a shop to place aphone order, an operator is your Facade to all services ad departments of the shop. The operator provides you with a simple voice interface to the orderin system, payment gateways, and various delivery services.

Decorator
The Decorator pattern is a structural pattern that lets you attach additional functionalities to an object dynamically. Analogy: Backpacks can have a variety of features. The features can range from something as simple as a laptop slot, side pockets, or even a power-abank for USB charging. The main target of the Decorator pattern is to allow the client to add whatever features are required, dynamically , safely and in the easiest possible way.

Builder
Its purpose is to separate the construction of a complex object from its representation so that the same construction process can create different representations. Parse a complex representation, create on of several targets. Analogy / use: this pattern is used by fast food restaurants to construct children's means. Children's meals typically consist of a main item, a side item, a drink, and a toy. There can be a variation in the content of the children's meal, but the construction process is the same.

Prototype
The intent is to specify the kinds of objects to create using a prototypicla instance and create new objects by copying this prototype and co-opt one instance of a class for use as a breeder of all future instances. In this design pattern the 'new' operator is considered harmful. Analogy: Let's consider a scenario where the client is running a Move Rating website. Client is using an External Rest API to fetch all the details (name, releasedate, genre, etc.) related to the move title. As his is an external API, Clients have to pay a certain fee tfor every API call. Client website is desinged in such a way that rating of the Movie can change periodically but other data (Name, Genere, releasedate) is a constant and will never changel Client needs a new object of Movie for every visitor who rates the Movie. In order to save money, the External API should be hit only once and for every subsequent request, we can use the Prototype Design Pattern to return the cloned object of the previous object.


## Generics

Update your Pokemon App to utilize a generic network layer.

Done. For latest update visit the corresponding Pokedex HW Assignment repository: 
https://github.com/maverick8000/Pokedex.git

