
## About Page Lab
#### Xcode Layout
* So far we have done all of our coding in the Xcode playground, but that's not where iPhone or iPad apps actually get written. Let's take a look at this folder in Xcode.
So far, we've only used the Xcode playground. When we create a new Xcode project, it creates a skeleton of an application for us, which consists of several different folders and files. Let's take a look at the new layout.
##### Editor Area
* Purpose: This is where the the core development tasks take place. When you open a file, it is displayed in the editor area. Right now, this should be where you see the layout of the beginning of an iphone app.
<p align="center">
  <img src="https://github.com/upperlinecode/intro-to-swift/blob/master/day-1/images/editor-area.png" height="400px" hspace="20">
</p>

##### Navigator
* How to show: click the rectangular button in the upper right hand corner of Xcode (leftmost of three).
* Purpose: Show your project's file structure.
* There are three main folders in our project: AboutPage, AboutPageTests, and Products. Right now, we're only going to be looking at files in the AboutPage folder.
<p align="center">
  <img src="https://github.com/upperlinecode/intro-to-swift/blob/master/day-1/images/navigator.png" height="400px" hspace="20">
</p>

##### Utilities
* How to show: click the rectangular button in the upper right hand corner of Xcode (rightmost of three).
* Purpose: Contains a variety of helpful tools. We will look at these as we begin developing our apps.
<p align="center">
  <img src="https://github.com/upperlinecode/intro-to-swift/blob/master/day-1/images/utilities.png" height="400px" hspace="20">
</p>

##### Assistant Editor Area
* How to show: click the button containing two overlapping circles in the upper right hand corner of Xcode.
<p align="center">
  <img src="https://github.com/upperlinecode/intro-to-swift/blob/master/day-1/images/assistant-editor.png" height="100px" hspace="20">
</p>

* Purpose: Allows you to view and edit multiple files at the same time.

##### Debug Area
* How to show: click the rectangular button in the upper right hand corner of Xcode (center of three).
* Purpose: Shows output messages. These might include print messages you put in your code, or error messages generated by Swift.
<p align="center">
  <img src="https://github.com/upperlinecode/intro-to-swift/blob/master/day-1/images/debugging-area.png" height="150px" hspace="20">
</p>


#### Model View Controller Design Pattern
Applications like Facebook, Airbnb, or Spotify use what is called a Model-View-Controller (MVC) design pattern. We will talk more about this later this week, but it's extremely important to know so we're going to go over it many times. The MVC design pattern is all about organizing your code by its purpose. The three sections are as follows.
- Model
  - This holds your data and it is where you write code that allows you to manipulate that data. For spotify, its models hold the songs' information and user data. For Facebook, the models hold all of the status updates, profile pictures, and other user information.
  - In the AboutPage app, our model is located in the About.swift file.
- View
  - This part controls how that data is displayed, and where the user can input new data. If you want to display all of your users' names and statuses on a blue table with red text, or if you need to let the user type in a song that they want to listen to, this is handled in the view.
- Controller
  - The views need to access the models' data, and this communication is handled by the controllers.
  - The file where we will be writing our controller code is ViewController.swift

#### Adding our data to the project
- This is going to be a one-page application that displays some facts about a user, like a simple profile page. In order to add your data to the page, you'll need to start by going to the About.swift file.
- You should see this:
```Swift
struct About {
    //Write your code here. Make sure to put all of your code in between the two curly braces that surround the About struct

}
```
- A struct is simply a way that we can package together several variables. Later on, we are going to have to send this data from the model to the controller, and from the controller to the view. It will be easy to do this if it's all held together in this About struct.
- Add four constants inside the curly braces of the struct:
  -  store your name in a constant called name.
  -  store your age in a constant  called age.
  -  store a paragraph about yourself in a string constant called bio.
  -  make an array of your top three favorite movies in a constant called favoriteMovies.

#### Connecting our model to our controller
- Click on the ViewController.swift file.
- There is a lot going on here, but it's not as complicated as it looks. A lot of this code gets written for us by Xcode. For now, we're just going to look at this statement (line 18)
```Swift
let about = About()
```
- We are storing our About struct from the model in a variable constant 'about'.
- Now, look at the addData function. Focus on the first line:
```Swift
Name.text = "Name: \(about.name)"
```
- We are interpolating the name constant from the about struct into a string that will be displayed in our views.

#### Connecting our controller to our view
- But where does Name.text come from? Well at the top of ViewController.swift, look at this statement:
```Swift
@IBOutlet weak var Name: UILabel!
```
- This is where the Name IBOutlet is created. An IBOutlet simply connects a property in our view to our controller. Click on the Main.storyboard file (If it doesn't show up as a picture of an iPhone and you just see code, right click on the file name and select open as -> interface builder - storyboard).
- If you click on "Name", a box around it will appear. This box will fill up with the string from the controller when you run the application.
- Test it out by clicking the blue play button in the upper left corner of Xcode. Select iPhone6 for the simulator.

<p align="center">
  <img src="https://github.com/upperlinecode/intro-to-swift/blob/master/day-1/images/about-page-final.png" height="400px" hspace="20">
</p>

#### Bonus Items
- Look up how to change the background color or the size of text
- If you have an iPhone, you can actually put this onto your phone right now. See if you can look up how to do this.
- Play around with it! What is it missing? Add your own touch to it. You can always download the code again, so it really doesn't matter if you break anything.
