# Creating And Using Segue in Xcode

## Creating a segue from UI element to another view controller

- To create and use segue first of all we will require two viewcontrollers. And I have created two of them namely `ViewController` and `SecondViewController` and both are there in storyboard as well.
- Lets say in our first viewcontroller we add a button from object directory by dragging and dropping uibutton in the viewcontroller, this button will take us from `ViewController` to `SecondViewController`.
- In order to that we need to setup a segue and setting up a segue is very easy. All you need to do is just click the button, hold down the control key on keyboard and click and drag and point to the `SecondViewController`.
- You will see a popup of types of segue, chose Show from the options. It can be change at point of development time if needed later on.
- As soon as you chose Show from the option, you will see that Xcode has drawn a line from `ViewController` to `SecondViewController`
- And thats all. If you run your app now click on the button it will take you to the `SecondViewController`

## Segue can be created from one view controller to another without initiating it from any UI Element
- What you need to just click on yellow symbol on top the screen which indicates the "View Controller"
- Hold down the `control` key and drag aero to the `SecondViewController` and chose type of segue. Now this segue links `ViewController` to `SecondViewController`
- Now your question might be "how do I trigger it when I press the button ? "  
- In order to use this segue you will need to give it a identifier,  go to atribute inspector and keep segue selected and give a name to it. I have given `goToSecondScreen`.
- Now we need to link the button via IBAction, we can call it `buttonPressed`.
- Now all we have to say that 

        performSegue(withIdentifie: "goToSecondScreen", sender : self)
        
        
## Why need identifier for segues
- Actually we can create multiple segues from single view controller to multiple view controllers.
- We can trigger the other segue from other button on single view controller to some other view controller.
- Since identifier is the string, we have to make sure that we use it exaclty  with casing to completely identical to how we names it in atribute inspector


## Passing data from one view controller to another using a segue

- Lets consider what user does on first screen will determine the what will apear on second screen.
- Lets take `TextField` on first screen  `ViewController` and  `Label` on second screen `SecondViewController`. We are going to ask user to enter some data on first screen and we will pass it to the second screen to display as result.
- I have connected `TextField` to `ViewController`  and named it `textField` and  `Label` to `SecondViewController` and named it `label`.
- Now override a method `prepare for segue` as below

        override prepare (for segue: UIStoryboardSegue, sender: Any?){
            if segue.indentifier == "goToSecondScreen" {
        
            }
        }
- Now lets create a prperty in `SecondViewController` called `textPassedOver`.
            
            var textPassedOver : String?
            
- Now we have to grab the reference of  `SecondViewController` and assign value to it from `textField`
        
            let destinationVC - segue.destination as! SecondViewController
            destinationVC.textPassedOver textField.text

- Now lets set `textPassedOver` value to `label` in `SecondViewController`.
- And its working.
