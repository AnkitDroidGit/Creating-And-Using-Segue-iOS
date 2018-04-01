# Creating And Using Segue in Xcode

## Creating a segue

- To create and use segue first of all we will require two viewcontrollers. And I have created two of them namely `ViewController` and `SecondViewController` and both are there in storyboard as well.
- Lets say in our first viewcontroller we add a button from object directory by dragging and dropping uibutton in the viewcontroller, this button will take us from `ViewController` to `SecondViewController`.
- In order to that we need to setup a segue and setting up a segue is very easy. All you need to do is just click the button, hold down the control key on keyboard and click and drag and point to the `SecondViewController`.
- You will see a popup of types of segue, chose Show from the options. It can be change at point of development time if needed later on.
- As soon as you chose Show from the option, you will see that Xcode has drawn a line from `ViewController` to `SecondViewController`
- And thats all. If you run your app now click on the button it will take you to the `SecondViewController`



