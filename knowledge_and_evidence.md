# Evidence and Knowledge

This document includes instructions and knowledge questions that must be completed to receive a *Competent* grade on
this portfolio task.

## 1. Required evidence

### 1.1. Answer all questions in this document

- Each answer should be complete, well-articulated, and within the specified word count limits (if added) for each
  question.
- Please make sure **all** external sources are properly cited.
- You must **use your own words**. Please include your full chat transcripts if you use generative AI in any way.
- Generative AI hallucinates, is not an authoritative source

### 1.2. Make all the required modifications to the code

- Please follow the instructions in this document to make the changes needed to the code.

- When requested to upload evidence, upload all screenshots to `screenshots/` and embed them in this document. For
  example:

```markdown
![Example Running Code](screenshots/screenshot1.png)
```

![Sample](screenshots/sample.png)
> Note the `!`, and the use of a relative path.

- You must upload the code into your GitHub repository.
- While you can use a branch, your code should be in main when you submit.
- Upload a zip of this repository to Blackboard when you are ready to submit.
- You will be notified of your result via Blackboard
- However, if using GitHub classrooms, you may also receive additional feedback on GitHub directly

### 1.3. Optional: Use of Raspberry Pi and SenseHat

Raspberry Pi or SenseHat is **optional** for this activity. You can use the included `sense_hat.py` file to simulate the
SenseHat on your computer.

If you use a Pi, please **delete** the `sense_hat.py` file.

### 1.4. Accessible version of the code

This project relies on visual patterns that appear on an LED matrix. If you have any accessibility requirements, you can
use the `udl/accessible` branch to complete the project. This branch provides an accessible code version that uses
text-based patterns instead of visual ones.

Please discuss this with your lecturer before using that branch.

## 2. Specific Tasks & Questions

Address the following tasks and questions based on the code provided in this repository.

### 2.1. Set up the project locally

1. Fork this repository (if not using GitHub Classrooms)
2. Clone your repository locally
3. Run the project locally by executing the `main.py` file
4. Evidence this by providing screenshots of the project directory structure and the output of the `main.py` file

![DirectoryStructure.png](screenshots/DirectoryStructure.png)

![MainOutput.png](screenshots/MainOutput.png)


If you are running on a Raspberry Pi, you can use the following command to run the project and then screenshot the
result:

```bash
ls
python3 main.py
```

### 2.2. Fundamental code comprehension

Answer each of the following questions **as they relate to that code** supplied by in this repository (ignore
`sense_hat.py`):

1. Examine the code for the `smiley.py` file and provide an example of a variable of each of the following types and
   their corresponding values (`_` should be replaced with the appropriate values):

| Type                    | name  | value              |
|-------------------------|-------|--------------------|
| built-in primitive type | Int   | "255" and "0"      |
| built-in composite type | Array | "self.pixels = []" |
| user-defined type       | Class | "class Smiley:"    |

> https://www.geeksforgeeks.org/primitive-data-types-vs-non-primitive-data-types-in-python/

2. Fill in (`_`) the following table based on the code in `smiley.py`:

| Object                  | Type  |
|-------------------------|-------|
| self.pixels             | List  |
| A member of self.pixels | Tuple |
| self                    | Class |

3. Examine the code for `smiley.py`, `sad.py`, and `happy.py`. Give an example of each of the following control
   structures using an example from **each** of these files. Include the first line and the line range:

| Control Flow | File      | First line | Line range |  
| ------------ |-----------|------------|------------|
| sequence     | smiley.py | 39         | 5 to 9     |
| selection    | sad.py    | 25         | 25 to 30   |
| iteration    | happy.py  | 33         | 33 to 43   |

4. Though everything in Python is an object, it is sometimes said to have four "primitive" types. Examining the three
   files `smiley.py`, `sad.py`, and `happy.py`, identify which of the following types are used in any of these files,
   and give an example of each (use an example from the code, if applicable, otherwise provide an example of your own):

| Type  | Used? | Example                               |
|-------|-------|---------------------------------------|
| int   | Yes   | "mouth = [49, 54, 42, 43, 44, 45]"    |
| float | Yes   | "delay=0.25"                          |
| str   | No    | N/A                                   |
| bool  | Yes   | "def draw_eyes(self, wide_open=True)" |

5. Examining `smiley.py`, provide an example of a class variable and an instance variable (attribute). Explain **why**
   one is defined as a class variable and the other as an instance variable.

> WHITE, GREEN, RED, YELLOW, BLANK are examples of class variables. They are considered class variables because they
> are declared and utilized in the class and have the same defined value with every instance.

> "self.sense_hat = SenseHat()" defined under "def __init__(self):" is considered an instance variable. Its values are
> determined with each instance of the SenseHat class and are unique to that instance.

> https://www.digitalocean.com/community/tutorials/understanding-class-and-instance-variables-in-python-3

6. Examine `happy.py`, and identify the constructor (initializer) for the `Happy` class:
    1. What is the purpose of a constructor (in general) and this one (in particular)?

   > The constructor for 'happy.py' is "def __init__(self):". A constructors purpose is to intialize a created object
   with determined values. In the case of this code, it sets up the smiling/happy face being drawn.

    2. What statement(s) does it execute (consider the `super` call), and what is the result?

   > The line "super().__init__()" calls the Smiley class since Happy inherits from Smiley due to the super() function.

>

### 2.3. Code style

1. What code style is used in the code? Is it likely to be the same as the code style used in the SenseHat? Give to
   reasons as to why/why not:

> The code style follows Python PEP8 standards.
> It is likely to be the same code style as the SenseHat due to the usage of snake casing and uppercasing names for
> constants (eg. "DEFAULT_RGB")

2. List three aspects of this convention you see applied in the code.

> Three aspects of PEP8 conventions seen in the code include snake casing, indentation and uppercase constant names.

3. Give two examples of organizational documentation in the code.

> """
> Set the SenseHat's light intensity to low (True) or high (False)
:param dimmed: Dim the display if True, otherwise don't dim
"""

> """tkinter GUI for the mock SenseHAT. Tkinter is not thread-safe, so we need to run it in a separate process."""

### 2.4. Identifying and understanding classes

> Note: Ignore the `sense_hat.py` file when answering the questions below

1. List all the classes you identified in the project. Indicate which classes are base classes and which are subclasses.
   For subclasses, identify all direct base classes.

Use the following table for your answers:

| Class Name | Super or Sub? | Direct parent(s)  |
|------------|---------------|-------------------|
| Happy      | Sub           | Smiley, Blinkable |
| Smiley     | Super         | N/A               |
| Blinkable  | Super         | N/A               |
| Sad        | Sub           | Smiley            |

2. Explain the concept of abstraction, giving an example from the project (note "implementing an ABC" is **not** in
   itself an example of abstraction). (Max 150 words)

> Abstraction is when unnecessary details of how something works are hidden, while only essential data is shown,
  simplifying how it is interacted with. An example is found in the 'Blinkable' class, where the method "blink"
  is created but no value is assigned within that class. The specific function and values are assigned by other classes 
  based on what the author wants to happen.


3. What is the name of the process of deriving from base classes? What is its purpose in this project? (Max 150 words)

> Inheritance is when a class derives properties from another 'parent' class. It's purpose in this project is to
  display different emotions on the face. 'Happy' inherits all the code from both 'Smiley' and 'Blinkable', while
  'Sad' inherits code from just 'Smiley'. Since these classes both inherit from parent classes, they are considered
  "Subclasses".

### 2.5. Compare and contrast classes

Compare and contrast the classes Happy and Sad.

1. What is the key difference between the two classes?
   > Sad doesn't inherit from Blinkable, unlike Happy, and it doesn't have a blink method.


2. What are the key similarities?
   > Both classes inherit from Smiley

   > Both classes use lists to draw the mouth


3. What difference stands out the most to you and why?
   > The Sad class not inheriting from the 'Blinkable' class and not having a blink method stands out the most to me
   as the rest of the code is structurally similar.


4. How does this difference affect the functionality of these classes
   
> When the face is drawn using the 'Sad' class the result will not blink.

>

### 2.6. Where is the Sense(Hat) in the code?

1. Which class(es) utilize the functionality of the SenseHat?
   
> The primary class that uses SenseHat is 'Smiley'. 'Happy' and 'Sad' are also utilizing SenseHat as they are 
     subclasses of 'Smiley'.
   

2. Which of these classes directly interact with the SenseHat functionalities?
   > Smiley

>

3. Discuss the hiding of the SenseHAT in terms of encapsulation (100-200 Words)
> Encapsulation is when methods that affect the internal state and inner workings of a project are put into a Class for 
  the purpose of protecting data and simplifying code. In the case of this project an example of encapsulation is found 
  in the 'SenseHat' class, which contains important methods for initialization. Specific details such as these are to be
  hidden in order to protect and organize such methods so they are not altered. Other classes are able to use these
  methods by calling the 'SenseHat' class. An example is how 'Smiley' class calls the 'SenseHat' class so the arrays can
  be displayed on a mock SenseHat, however, the 'SenseHat' class does not need to be interacted with to edit what is 
  shown.



### 2.7. Sad Smileys Can’t Blink (Or Can They?)

Unlike the `Happy` smiley, the current implementation of the `Sad` smiley does not possess the ability to blink. Let's
first explore how blinking has been implemented in the Happy Smiley by examining the blink() method, which takes one
argument that determines the duration of the blink.

**Understanding Blink Mechanism:**

1. Does the code's author believe that every `Smiley` should be able to blink? Explain.

> Yes, it seems the Author intended the 'Sad' smiley to blink. This is evident in this line of code:
>     def draw_eyes(self, wide_open=True):
        """
        Draws open or closed eyes on a smiley
        :param wide_open: Render eyes wide open or shut
        """
        eyes = [10, 13, 18, 21]
        for pixel in eyes:
            if wide_open:
                eyes = self.BLANK
            else:
                eyes = self.YELLOW
            self.pixels[pixel] = eyes

> The for loop contains an if/else statement for the eyes being opened or closed. However, 'wide_open' is set to 'True'
  so the 'else' will never initialize.



2. For those smileys that blink, does the author expect them to blink in the same way? Explain.

> No, the author expected the 'Happy' and 'Sad' smiley's to behave differently. In 'Happy' the blinking is animated in
  a method to open and close with a delay. 'Sad' is written to use a 'for' loop, but can't blink since the bool cannot
  change.



3. Referring to the implementation of blink in the Happy and Sad Smiley classes, give a brief explanation of what
   polymorphism is.

> Polymorphism is when separate classes contain methods with the same names. Both 'Happy' and 'Sad' have a method
  called 'draw_eyes' which aims for similar functionality but are structurally different.



4. How is inheritance used in the blink method, and why is it important for polymorphism?

> The usage of polymorphism with the 'blink' method is important as it is more efficient to have an inherited method
  which completes the same function amongst multiple classes opposed to typing out similar code. This ensures code is 
  concise and intention from the author is clear.


1. **Implement Blink in Sad Class:**

    - Create a new method called `blink` within the Sad class. Ensure you use the same method signature as in the Happy
      class:

   ```python
   def blink(self, delay=0.25):
       pass  # Replace 'pass' with your implementation
   ```

2. **Code Implementation:** Implement the code that allows the Sad smiley to blink. Use the implementation from the
   Happy Smiley as a reference. Ensure your new method functions similarly by controlling the blink duration through the
   `delay` argument.

3. **Testing the Implementation:**

- Test the new blink functionality on your Raspberry Pi or within the Python classes provided. You might need to adjust
  the `main.py` script to incorporate Sad Smiley's new blinking capability.

Include a screenshot of the sad smiley or the modified `main.py`:

![SadSmiley.png](screenshots/SadSmiley.png)

- Observe and document the Sad smiley as it blinks its eyes. Describe any adjustments or issues encountered during
  implementation.

  > Initially I had problems getting the blinking to work, then I realised I had to import the Blinkable class and the
    time module.

  ### 2.8. If It Walks Like a Duck…

  Previously, you implemented the blink functionality for the Sad smiley without utilizing the class `Blinkable`.
  Assuming you did not use `Blinkable` (even if you actually did), consider how the Sad smiley could blink similarly to
  the Happy smiley without this specific class.

    1. **Class Type Analysis:** What kind of class is `Blinkable`? Inspect its superclass for clues about its
       classification.

    > 'Blinkable' is considered an "Abstract Base Class" (ABC)
    
    > https://www.geeksforgeeks.org/abstract-base-class-abc-in-python/
    
  
  2. **Class Implementation:** `Blinkable` is a class intended to be implemented by other classes. What generic term
       describes this kind of class, which is designed for implementation by others? **Clue**: Notice the lack of any
       concrete implementation and the naming convention.

    > The generic term for classes that do this is an "interface" class

  3. **OO Principle Identification:** Regarding your answer to question (2), which Object-Oriented (OO) principle does
       this represent? Choose from the following and justify your answer in 1-2 sentences: Abstraction, Polymorphism,
       Inheritance, Encapsulation.

   > The principle to define this class is 'Abstraction'. There is no value defined in the method itself and is
     designed to be assigned values from other classes. 

  4. **Implementation Flexibility:** Explain why you could grant the Sad Smiley a blinking feature similar to the
       Happy Smiley's implementation, even without directly using `Blinkable`.

  > Inheriting from 'Blinkable' is only used to define a "blink" method. You can create a blink method self-contained
    in the class and it'll function normally.

5. **Concept and Language Specificity:** In relation to your response to question (4), what is this capability known
   as, and why is it feasible in Python and many other dynamically typed languages but not in most statically typed
   programming languages like C#? **Clue** This concept is hinted at in the title of this section.

  > This capability is known as "Duck Typing", which is possible because Python is a dynamically typed langauge.
    Static-typed languages, like C#, are much more strict with how data is declared which restricts the ability
    of assumption.

  ***

  ## 3. Refactoring

  ### 3.1. Does a Smiley Have to Be Yellow?

  While our current implementation predominantly features yellow smileys, emotional expressions like sickness or anger
  typically utilize colors like green, red, or orange. We'll explore the feasibility of integrating these colors into
  our smileys.

1. **Defined Colors and Their Location:**

    1. Which colors are defined and in which class(s)?
        > Yellow and black (BLANK) are defined in the 'Smiley' class.

    2. What type of variables hold these colors? Are the values expected to change during the program's execution?
       Explain your answer.
        > These variables are stored as tuples, therefore their values are not expected to change.
 
    3. Add the color blue to the appropriate class using the appropriate format and values.
        > ![AddedBlue.png](screenshots/AddedBlue.png)

    2. **Usage of Color Variables:**

        1. In which classes are the color variables used?
           > When drawing the eyes and mouth in 'Happy' and 'Sad', also when drawing the base face in 'Smiley'

    3. **Simple Method to Change Colors:**
    4. What is the easiest way you can think to change the smileys to green? Easiest, not necessarily the best!
       > Replacing "YELLOW" with "GREEN" in areas where "YELLOW" is called.

  Here's a revised version of the "Flexible Colors – Step 1" section for the smiley project, incorporating your
  specifications for formatting and content updates:

  ### 3.2. Flexible Colors – Step 1

  Changing the color of the smileys once is straightforward, but it isn't very flexible. To facilitate various colors
  for smileys, it is advisable not to hardcode values in any class. This approach was identified earlier as a necessary
  change. Let's start by removing the built-in assumptions about color in our classes.

    1. **Add a method called `complexion` to the `Smiley` class:** Implement this instance method to return
       `self.YELLOW`. Using the term "complexion" instead of "color" provides a more abstract terminology that focuses
       on the meaning rather than implementation.
   
    2. **Refactor subclasses to use the `complexion` method:** Modify any subclass that directly accesses the color
       variable to instead utilize the new `complexion` method. This ensures that color handling is centralized and can
       be easily modified in the future.

    3. **Determine the applicable Object-Oriented principle:** Consider whether Abstraction, Polymorphism, Inheritance,
       or Encapsulation best applies to the modifications made in this step.

    4. **Verify the implementation:** Ensure that the modifications function as expected. The smileys should still
       display in yellow, confirming that the new method correctly replaces the direct color references.

  This step is crucial for setting up a more flexible system for color management in the smiley display logic, allowing
  for easy adjustments and extensions in the future.

  ### 3.3. Flexible Colors – Step 2

  Having removed the hardcoded color values, we now enhance the base class to support dynamic color assignments more
  effectively.

    1. **Modify the `__init__()` method in the `Smiley` class:** Introduce a default argument named `complexion` and
       assign `YELLOW` as its default value. This allows the instantiation of smileys with customizable colors.

    2. **Introduce a new instance variable:** Create a variable called `my_complexion` and assign the `complexion`
       parameter to it. This step ensures that each smiley instance can maintain its own color state.

    3. **Rationale for `my_complexion`:** Using a distinct instance variable like `my_complexion` avoids potential
       conflicts with the method parameter names and clarifies that it is an attribute specific to the object.

    4. **Bulk rename:** We want to update our grid to use the value of complexion, but we have so many `Y`'s in the
       grid. Use your IDE's refactoring tool to rename all instances of the **symbol** `Y` to `X`. Where `X` is the
       value of the `complexion` variable. Include a screenshot evidencing you have found the correct refactor tool and
       the changes made.

  ![BulkRename.png](screenshots/BulkRename.png)

    5. **Update the `complexion` method:** Adjust this method to return `self.my_complexion`, ensuring that whatever
       color is assigned during instantiation is what the smiley displays.

    6. **Verification:** Run the updated code to confirm that Smileys still defaults to yellow unless specified
       otherwise.

  ### 3.4. Flexible Colors – Step 3

  With the foundational changes in place, it's now possible to implement varied smiley colors for different emotional
  expressions.

    1. **Adjust the `Sad` class initialization:** In the `Sad` class's initializer method, change the superclass call to
       include the `complexion` argument with the value `self.BLUE`, as shown:

       ```python
       super().__init__(complexion=self.BLUE)
       ```

    2. **Test color functionality for the Sad smiley:** Execute the program to verify that the Sad smiley now appears
       blue.

    3. **Ensure the Happy smiley remains yellow:** Confirm that changes to the Sad smiley do not affect the default
       color of the Happy smiley, which should still display in yellow.

    4. **Design and Implement An Angry Smiley:** Create an Angry smiley class that inherits from the `Smiley` class. Set
       the color of the Angry smiley to red by passing `self.RED` as the `complexion` argument in the superclass call.
![Sad.png](screenshots/Sad.png)
![Angry.png](screenshots/Angry.png)
  ***
