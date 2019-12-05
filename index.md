# Java Workshop WORK IN PROGRESS :)



<div class="image-div">
</div>

## Introduction
TODO: add introduction text!"

TODO: Add instruction on how to download, install JDK!

TODO: Add instruction on how to install IDE!
## Lets do some christmas themed programming!
### Hello World! 

Are you completly new to java, or programming in general? Or maybe you just want to warm up? Start here! 

**Hello World**

A hello world program is a time-honored tradition in programming as a beginners first challange. Enter the repl below in a new tab, or download the zip, and follow the instructions. 

https://repl.it/@hannary/Hello-World

As you could see in the above example, There is a class called Main and a method called main. All java code has to be inside a class (but it doesn't have to be called Main, that is just the standard name used in repl). The entry point of a program is the "public static void main(String args[])" method. Java will look for this method to know where to start executing code. Try removing it and see what the compiler says!

**A christmas greeting**

Lets try make a new method after the main method. In the HelloWorld program, after the main method, add a new method:

``` 
public static void christmasGreeting(String personToGreet) {

}
``` 

remove the System.out.println("Hello World!") from the main method and run the program. You should not get any errors or any other output.

Now add a new System.out.println inside the christmasGreeting method:

``` System.out.println("Merry Christmas " + personToGreet);``` 

Inside the main method, add a call to our new ChristmasGreeting method:

``` christmasGreeting("Name"); ```

Name can be anything you want. Now run the program, the output should be "Merry Christmas, Name!"

### Temperature converter and santa checker
Santa clause has decided to make a stand against global warming by declaring that he will only show up if the winter is actually cold, meaning the temperature is below 0 degrees celcius. Lets write a program to help our friends who only know fahrenheit!

Open the following repl in a new tab, or download the program and start it in your ide:

https://repl.it/@hannary/Temperature-converter-and-Santa-checker

As you can see, there is only one lonely print statement in there. Let's change that. 
At the top of the file is an import statement, which let's us use the build in Java Scanner to read input. After the System.out.println statement, add this:

```
Scanner reader = new Scanner(System.in);
int f = reader.nextInt();
System.out.println(f);
```

The first statement creates a reader, that can be used to read user input. The next one saves the next number the user inputs. the third one prints that number. Try it out! (try printing something other than a number.. you will get an error as Java expects a number and don't know what to do with text, for example).

Now let's do some math. The formula for converting Fahrenheit to celcius is: celsius = ((fahrenheit - 32) * 5) /9
Since an int doesnt allow decimals, this is an approximation. But it will do for now.
under the line reading in the value f, add:

```int c = ((f - 32) * 5) /9;```

Now instead of only printing f, change the System.out.print to print the new temperature:

```
System.out.println(c);
```

Change the above print statement to be a little more descreptive. instead of c, write: (c + "degrees in celsous is " + f + " degrees in 

```
System.out.println(f + "degrees in farenheit is " + c + "degrees in celsius");
```

Try it out! 

Now let's add a santa check. We want to print out "Santa is coming!" if the value of c is zero or lower, and "Santa isn't coming" otherwise. Add the following under the lines of code you just added:

```
if(c <= 0){
  //Add system.out.println here
}
else {
  //Add system.out.println here
} 
```

Add the System.out.println() statements with your output inside the if and else clauses.

Try it out! You should now have a santa checker and temperature checker, for all your winter needs.


### A Program for writing a christmas wish list

Goal: a program that lets you make a christmas wish list.
You should be able to add more items, print them out, and quit the program.

Right now, the program lets you add one item, prints it out, and qutis. It needs a loop to run in and decide what to do based on user input!
https://repl.it/@hannary/ChristmasList (DONE: https://repl.it/@hannary/DoneChristmasList)

**Step one: Before the loop**

At the start of the main method(public static void main(String[] args)), create a string to store the current user input in, and a list to store all of the input in:

``` 
List<String> s = new ArrayList<>();
String userInput;
 ```

Next, after those variables, add a boolean to control the flow of the program:

``` boolean isProgramRunning = true; ```

After that, add a System.out.println statement that prints ""Print q to quit, s to see current list ".

**Step two: in the loop**

Now we add a while loop that runs while the boolean *isProgramRunning* is true:

``` 
while(isProgramRunning){

} 
```

Inside the loop: add these lines to read input from the user and store it in a list and then print it out:

```
userInput = in.nextLine();
gifts.add(userInput)
System.out.println(gifts);
```

Try it out! This program will run forever now, so you will have to kill it to end it.

**Step three: Controlling the loop**

We have three cases: the userInput is 'l', and the gifts should be printed out.
                     the userInput is 'q', and the program should end.
                     the userInput is a new item for the wishlist (a string(, and it should be added to the list.
                     
 Inside the while loop, add an *if else* clause:
 
 ```
 if(userInput.equals("q")){
        isProgramRunning = false;
      }
 ```
 
 Try running the program. It should let you add gifts until you press q.
 
 next, add two more cases:
 
 ```
 else if (userInput.equals("l")){
    //Move the System.out.println that prints the list of gifts here
 }
 else {
    //Move the line that adds gift to the list here.
    //you could also add a System.out.println() that tells the user that a gift has been added!
 }
 ```
 

Move the System.out.printlns into the *else* clauses as specified in the comments above.

There! You have a program to store gifts. Nifty.


### Christmas Tree
It's Christmas time, so today we are going to be drawing a Christmas tree of your chosen size in Java.

https://repl.it/@Saeideh/ChristmasTree

All is about three loops:

**Step one: Loop for number of rows**
 ```
 for (int i = 0; i < x; i++) {
 ```
 
 **Step two: Loop for printing the Space**
 ```
 for (int j = 0; j < i; j++)
    System.out.print(" ");
 ```
 
 **Step three: Loop for printing the asterisks**
 ```
 for (int k = 0; k < (2 * i + 1) ; j++)
    System.out.print("*");
 ```
There we go :)
## Harder project: Lets create some christmas memories

![image](tempsnip.png)

Or in this case, Christmas Memory. Tha classic game we all love to play.
TODO: Add instructions and code. And fix the terrible pictre

In this application we are using an old java toolkit called *swing*. It's rarely used for new projects today, but it's useful for making small, lightweight applications to learn java. 

If you run the program, you should see an empty frame.  

We already created the class Card for you. Take a look: It contains an Image, an ID for comparing cards, and two booleans to keep track of if the images/have been found.

In the folder, there are 12 images we will use for the cards.

 In the setUpBoard() method in Board.java, we have already initiated two values: openCards where we will store open cards, and frame, where we store the game "frame". We'll now add some the cards to the board.

Under the two already initiated values mentioned above, we'll add the cards. Each card needs to be added twice, and have an ID and an image:

 ```
Card card1 = new Card("wreath", "wreath.png");
Card card2 = new Card("wreath", "wreath.png");
Card card3 = new Card("gift", "gift.png");
Card card4 = new Card("gift", "gift.png");
Card card5 = new Card("hat", "santa-hat.png");
Card card6 = new Card("hat", "santa-hat.png");
Card card7 = new Card("sweet", "sweet.png");
Card card8 = new Card("sweet", "sweet.png");
Card card9 = new Card("mistletoe", "mistletoe.png");
Card card10 = new Card("mistletoe", "mistletoe.png");
Card card11 = new Card("tree", "christmas-tree.png");
Card card12 = new Card("tree", "christmas-tree.png");
 ```  

After creating the cards, We'll add them all to an the array "cards" to make handeling them a little bit easier:

 ```
 cards.add(card1);  cards.add(card2);  cards.add(card3);  cards.add(card4);  cards.add(card5); 
 cards.add(card6);  cards.add(card7);  cards.add(card8);  cards.add(card9);  cards.add(card10);
 cards.add(card11); cards.add(card12);
 ```

Phew! Next, lets shuffle the cards so they'll show up at different places of the board:

```
Collections.shuffle(cards);
```


Next, we'll go through the array and add every card to the game frame, set the icon to null (so that the cards will be empty at the start of the game), and then we'll add a *listener* to each card. Since we are using swing components, the listener method is 
built in. It allows us to tell java that we want the application to listen for a click of the button. When the button is clicked, the listener method will be called:

```
for(Card card : cards) {
     frame.add(card);
     card.setIcon(null);
     card.addActionListener(this);
  }
```

Try running the program. You should see a matrix of blank cards. If you try clicking one, nothing will happen. We are not doing anything in the listener, so the application isn't doing anything when we click.
The listener method inherented from swing is called " actionPerformed(ActionEvent e)". Locate it under the setUpBoard() method.

Add this to the top of the method: 

```
Card justOpened = ((Card)e.getSource());
justOpened.togglePictureShowing(true);
```

We just got the card from the event, and set it as showing. Try running the program. You should be able to open the cards now.

We need a way to keep track of how many, and which cards are currently open. Ad this after the two other lines:

```
openCards.add(justOpened);
```

We now have a program that shows empty cards. When a cards is clicked, a listener is called and in the listener we tell the program to show the image of the clicked card and store all open cards in an array. Nice.

## Adding logic

Go back to the very top of the actionPerformed method. As soon as the user clicks a card, we want to check if two cards are currently showing:

```
if(openCards.size()==2){


}
```
If two cards are open, we can retrive them from the openCards array. Add the following **inside** the if clause:

```
Card firstOpen = openCards.get(0);
Card secondOpen = openCards.get(1);
 ```

Now lets see what we want to do with these two open cards. First, we want to check if they match. Then, we want to close them if they don't match. There are two prepared methods that matches these cases. Lets call them with our two cards:

```
 checkIfMatch(firstOpen, secondOpen);
 closeCards(firstOpen, secondOpen);
 ```
 
We need to implement the checkIfMatch() and closeCards() methods. They exist, but have no bodey. We'll start with checkIfMatch, located under the actionPerformed method. Inside it, we'll check if the cards match by comparing the id's of the cards:

```
 if(firstOpen.getId().equals(secondOpen.getId())){
           
    }
```

What we do here is asking "get the it of the first open card. Is it equal to the id of the second open card?"

If the answer is yes, we need to set the card to "found" so that they can't be closed again. Add this *inside* the if:

```
firstOpen.setAsFound();
secondOpen.setAsFound();

```

There! Let's move on to the closeCards method, under the checkIfMatch method. In the Cards class, you can look at the toggleImageShowing method. It only toggles the image of cards that aren't set to found. Add this at the top of toggleImageShowing:

```
firstOpen.togglePictureShowing(false);
secondOpen.togglePictureShowing(false);
```

The last thing we'll do inside the closeCards method is clear the array of open cards, since no cards are open anymore (except for the "found" cards, that we consider "out of the game"):

```
openCards.clear();
```


Try it out!


### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/hanna-ry/java_workshop/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
