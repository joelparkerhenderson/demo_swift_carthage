# Demo Swift Carthage

<img src="README.png" alt="Carthage" style="width: 100%;"/>

This demonstration shows:

  * The [Swift](http://swift.org) programming language with
    [Apple](http://apple.com)
    [Xcode](https://developer.apple.com/xcode/)
    [iOS](http://www.apple.com/ios/)

  * The [Carthage](https://github.com/Carthage/Carthage) dependency manager.

  * The [Prelude](https://github.com/robrix/Prelude) Swift micro-framework of simple functional programming tools.

There are multiple git branches so pick the one you want:

  * swift-4-xcode-9: Swift version 4, Xcode version 9, iOS version 11.

  * swift-3-xcode-8: Swift version 3, Xcode version 8, iOS version 10.

To use this project:

  * You can clone this repo.

  * Or you can create the project yourself by using this README that explains how to do it.


## Create the project

Launch Xcode. 

Choose "File" → "New" → "Project". 

You see the dialog "Choose a template for your new project".

  * Choose the "iOS" radio button.

  * Choose the "Single View Application" icon.

  * Tap the button "Next".

You see the dialog "Choose options for your new project".

  * For "Product Name", type "Demo Swift Hello World".

  * For "Organization Name", type anything you want; typically this is your company's name, or team's name, or similiar. For example, "Example Company".

  * For "Organization Identifier", type anything you want; typically this is your company's reverse domain name. For example, "com.example".

  * Tap the button "Next".

You see the file chooser.

  * Choose where to save your project.

  * Tap the button "Create".

  * Xcode creates the project.


## Sign the project

If Xcode shows a "Signing" area with a "Status" alert icon, here's how to solve it.

  * Xcode may show a message such as "Signing for "Demo Swift Hello World" requires a development team. Select a development team in the project editor."

  * In the same "Signing" section, choose the "Team" dropdown, and choose your Apple ID.

  * If there's no Apple ID, then you need to add yours: Xcode → Preferences → Accounts → the "+" button → Add Apple ID


## Run the project

Run the project for the first time.

  * Xcode → Product → Run

  * This is simply to verify that the project runs so far.

The Simulator launches.

  * The Simulator shows a blank screen.

  * Quit the Simulator and go back to using Xcode.


## Get Carthage

To see if you have Carthage installed, and if the Carthage version is current, run this command:

    $ carthage version
    0.25.0

If Carthage is not installed, or the version is lower than 0.25.0:

  * Use these [Carthage instructions](https://github.com/Carthage/Carthage)


## Create a Cartfile
 
Create an empty text file named `Cartfile` at the top level of the project. 
   
Edit the `Cartfile`.

  * You can add any framework you want. 

  * For this demo, we add the "Prelude" framework, which is provides programming functions.

  * Add this text:

      github "robrix/Prelude"

Update.

    $ carthage update
    *** Fetching Prelude
    *** Downloading Prelude.framework binary at "2.0"
    *** xcodebuild output can be found in /var/folders/…

See the results if you like.

  * There is a new file `Cartfile.resolved` that lists the framework and its exact version number.

  * There is a new directory `Carthage`. This contains the `Build` directory and the framework files.

    $ ls -1
    Cartfile
    Cartfile.resolved
    Carthage
    Demo Swift Carthage
    Demo Swift Carthage.xcodeproj
    Demo Swift CarthageTests
    Demo Swift CarthageUITests

    $ ls Carthage
    Build

    $ cat Cartfile.resolved
    github "robrix/Prelude" "2.0.0"


## Link the framework

Go to the Xcode project "General" area.

Scroll down the section "Linked Frameworks and Libraries", with the text that says "Add frameworks &amp; libraries here".

Tap the "+" icon.

  * A dialog opens that says "Choose frameworks and libraries to add".

  * Tap the button "Add Other..."

Choose the framework.

  * A file chooser opens.

  * Navigate up a folder, and you see the "Carthage" folder.

  * Open the folder "Carthage", then the folder "Build", then the folder "iOS".

  * Tap the file "Prelude.framework" to highlight it.

  * Tap "Open"

The section "Linked Frameworks and Libraries" now shows "Prelude.framework".


## Create the Run Script

Go to the Xcode project "Build Phases" settings area.

  * Click the "+" icon, then choose "New Run Script Phase".

  * Click the triangle by the new "Run Script" list item.

  * The "Shell" field should say `/bin/sh`.

  * The larger text field should say `Type a script or drag a script file from your workspace to insert its path`.

  * Set the larger text field to say `/usr/local/bin/carthage copy-frameworks`

Add input files.

  * In the area "Add input files here", click "+".

  * Set the "Input Files" to `$(SRCROOT)/Carthage/Build/iOS/Prelude.framework`


## Run

Run the project.

  * Xcode → Product → Run

The Simulator launches.

  * The app will launch normally. 

  * This verifies that Carthage can connect the files.

  * Congratulations! You're successful!

  
## Tracking

* Package: demo_swift_carthage
* Version: 3.0.0
* Created: 2016-04-09
* Updated: 2017-09-22
* License: BSD, MIT, GPL
* Contact: Joel Parker Henderson (joel@joelparkerhenderson.com)
