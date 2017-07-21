<!--
$theme: default
page_number: true
footer: Java Class - Week 1
-->

# Week 1

- **Terminology, commands, and installing Java**
- **Hello, World**
- **Input and output**
- **Variables**
- **Data types**
- **Operators**
- **Reading compiler output**

-----------------------------------------------------------------------------

# Terminology and commands

Before we start writing code, let's cover a few terms, commands, and other useful information that you will need to know to effectively continue with the next sections.

-----------------------------------------------------------------------------

==**Code editor**==: this is a program used to write anything, including code. Examples include Nodepad, Notepad++, Sublime Text, Atom, IntelliJ. If you're unsure about white editor to use, start with [Atom](https://atom.io/).

-----------------------------------------------------------------------------

==**Terminal/Command Prompt**==: this is a program used to _run_ other programs. Your computer already has this program installed.
  - To open the command prompt in Windows, click on the Start menu and search for "_command_".
  - To open the terminal in Macos, open Spotlight <kbd>Cmd + Space</kbd> and search for "_terminal_".

-----------------------------------------------------------------------------

==**Command**==: a computer program similar to your browser, text editor, and music player, but with a few differences. First, you run commands in your terminal or command prompt. And second, commands generally don't have a GUI, meaning that you won't see a window or be able to click on buttons when you run them, but just text.

-----------------------------------------------------------------------------

==**"Running a command"**==: when the phrase "_running a command_" or "_run this command_" is used, the intention is that you open your command prompt, carefully type in the example command, and press the Enter key to run it.

-----------------------------------------------------------------------------

==**Compile**==: or "_compiling_" is the act of taking code that you wrote and preparing it so that your computer can run it. Not all programming languages need to be compiled, but Java does.

-----------------------------------------------------------------------------

==**Command arguments/parameters**==: sometimes you want to pass custom information to a command. This information is placed after the command name and is refered to as an argument or a parameter. For example, the command to compile a Java file is `javac` and this command takes a file name as one of its arguments. So if I wanted to compile a file named "HelloWorld.java" I would run `javac HelloWorld.java` where `javac` is the command and `HelloWorld.java` is the argument.

-----------------------------------------------------------------------------

==**Input and output**==: there are many forms of input and output, but for the next sections, we mean input to be custom arguments you pass to your Java programs and output to be the text that you see after running a command in your terminal/commandline prompt.

-----------------------------------------------------------------------------

# Commands


- `cd`: lets you move from one folder to another folder. Remember the phrase "_change directory_" (change = c, directory = d)
- `dir` (Windows) or `ls` (Macos/Linux): this command is used to list all of the files and folders in the folder you are currently in.
- `pwd` (Macos/Linux): this command will tell you what folder you are on right now. Useful when you want to `cd` into another folder.

-----------------------------------------------------------------------------

# Commands

- `javac`: the Java compiler. For example, if you had a file named "HelloWorld.java" and you wanted to compiled it, you would do so by running `javac HelloWorld.java` in your terminal/command prompt.
- `java`: another Java related command. This one is used to actually run your compiled program.

-----------------------------------------------------------------------------

# Reading these slides: code

Below is an example of how code is represented in these slides. Notice the gray background color. When you see code in slides, it will usually mean that you should write it in your text editor.

<br>

```java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello, World!");
  }
}
```

-----------------------------------------------------------------------------

# Reading these slides: commands

Commands will a lot like code with the exeption that they will have a "_>_" at the beginnig of the line. That's how you will know if it is a command instead of Java code. When you see this, it means that you should open your terminal/command prompt and run the command or commands.

```bash
> javac HelloWorld.java
> java HelloWorld
```

The example above is telling you to run `javac HelloWorld.java`, press enter, then run `java HelloWorld` and press enter again.

-----------------------------------------------------------------------------

# Installing Java

Open your USB drive and double click on the "_jdk_" program.

-----------------------------------------------------------------------------

# Hello, World

Now we can get started writing code. In this section we're going to use a text editor to write a Java program and then go into the terminal/command prompt to compile and run your program.

-----------------------------------------------------------------------------

In your text editor, create a new file and write the program below. Make sure you save this file in your pen drive in the "_week01_" folder and name it "_HelloWorld.java_".

<br>

```java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello, World!");
  }
}
```

-----------------------------------------------------------------------------

Go to your terminal and run the following commands (make sure you're in the right folder)

<br>

```bash
> cd PATH_TO_USB_DRIVE_ON_WINDOWS_COMPUTER
> javac HelloWorld.java
> java HelloWorld
```

<br>

If everything worked you should see `Hello, World!` as the output of running the last command.

-----------------------------------------------------------------------------

# Input

Now that we have written a program which has output, let's update it to also work with user input. As mentioned earlier commands can take arguments, so let's use an argument to make our Hello World program have the ability to say "Hello" to more than just "World" depending on if we run our program with an argument or not.

-----------------------------------------------------------------------------

In your text editor, create a new file and write the program below. Make sure you save this file in your pen drive in the "_week01_" folder and name it "_HelloWorldWithArguments.java_".

```java
public class HelloWorldWithArguments {
  public static void main(String[] args) {
    String name = "World";

    if (args.length > 0) {
      name = args[0];
    }

    System.out.println("Hello, " + name + "!");
  }
}
```

-----------------------------------------------------------------------------

Go to your terminal and run the following commands (make sure you're in the right folder)

<br>

```bash
> cd PATH_TO_USB_DRIVE_ON_WINDOWS_COMPUTER
> javac HelloWorldWithArguments.java
> java HelloWorldWithArguments Programmer
```

<br>

If everything worked you should see `Hello, Programmer!` as the output of running the last command.

-----------------------------------------------------------------------------

# Variables

> A variable is a symbolic name for (or reference to) information. The variable's name represents what information the variable contains. They are called variables because the represented information can change but the operations on the variable remain the same. [1]

-----------------------------------------------------------------------------

Three things are required to create a new variable in Java: the data type, a name, and an optional value.

A valid variable name can be made up of letters, numbers, dollar signs `$` and underscores `_`. They should always begin with letters, however (`$` and `_` are valid characters at the beginning of variable names, but this should be avoided.)

<br>

```java
String activityName = "Java programming";
int age = 47;
double pi = 3.14159;
```

-----------------------------------------------------------------------------

# Additional terminology

-----------------------------------------------------------------------------

==**Declaration**==: as previously mentioned, a value is optional when creating a variable. When a variable is created and it does not have a value, this is a way of _declaring_ the variable, meaning you are telling your program that this variable exists and it is information that should be tracked, but that you do not yet know what the value is and will set it after the program starts running. Keep in mind that the variable's data type is only required when it is being _declared_.

<br>

```java
int x;
```

-----------------------------------------------------------------------------

==**Definition**==: a variable is _defined_ when it is given a value. As shown in earlier examples, a variable can be declared and defined in one step, but that is not required. The first example below declares and then defines `x` and the one below that does the same but in one step:

<br>

```java
int x;
x = 7;
```

```java
int x = 7;
```

-----------------------------------------------------------------------------

# Data types

-----------------------------------------------------------------------------


- `byte`, `short`, `int`, and `long` are for integers, such as `1`, `99`, and `32423325`
- `float` and `double` are for floating-point numbers, such as `3.14`, `3.1`, and `89.12e32`
- `boolean` is for storing either `true` or `false` (think of this as on/off or yes/no)
- `char` is for a single character, such as `a`, `B`, and `\n`
- `String` is for a sequence of characters, or a string. For example, `Hello, World!`

-----------------------------------------------------------------------------

# Operators

-----------------------------------------------------------------------------

# Reading compiler output

-----------------------------------------------------------------------------

# Additional resources

- _Introduction and Setting up Your Environment_ by Jim Wilson https://app.pluralsight.com/player?course=java-fundamentals-language&author=jim-wilson&name=java-fundamentals-language-m1&clip=0
- _Variables, Data Types, and Math Operators_ by Jim Wilson https://app.pluralsight.com/player?course=java-fundamentals-language&author=jim-wilson&name=java-fundamentals-language-m3&clip=0

-----------------------------------------------------------------------------

# Reference list

1. Germain, https://www.cs.utah.edu/~germain/PPS/Topics/variables.html