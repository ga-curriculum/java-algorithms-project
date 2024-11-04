<h1>
  <span class="headline">Java Algorithms Project</span>
  <span class="subhead">Requirements and Guidance</span>
</h1>

## Overview

In this project, you will build a Cipher Algorithms or Maze Generation and Solver application that users interact with via the command line. This project focuses on demonstrating your understanding of algorithms and data structures in Java.

No matter which project you choose to build, you must implement various features to meet the minimum requirements. The users of each application should be able to select from multiple commands to interact with the application and see the results of their commands. Choose from one of the below options:

- Cipher algorithms (Caesar cipher and Vigenère cipher)
- Maze generation and solver

In addition to one of the projects above you can can also implement this functionality:

- RSA encryption with key generation using trees

***You will work individually on this project***.

> ❗️ As a reminder, General Assembly has a zero-plagiarism policy. ***Your project's code must be substantially yours***. Do not copy code from similar projects or other sources. However, using code from the internet to accomplish generic tasks is okay - for example, a line of code that replaces a character at a specific position in a string.

A printable version of the project requirements can be found [here](./assets/project-requirements.pdf).

## Technical requirements

### Minimum requirements - cipher algorithms

> ✅ If you build a cipher algorithms project any items marked incomplete in this section will result in the project receiving a failing grade.

#### Caesar cipher

- Users can input a message and a key to encrypt a message by shifting each letter in the message by the key. For example, `encrypt hello 3` would return `khoor`.
- Users can input a message and a key to decrypt a message by shifting each letter in the message by the key. For example, `decrypt khoor 3` would return `hello`.
- Users can undo the last encryption using a stack-based undo system. For example, `undo` would return the message to the state before the last encryption.
- Users can undo the last decryption using a stack-based undo system. For example, `undo` would return the message to the state before the last decryption.
- Users can input non-alphabetic characters in the message that are not encrypted. For example, `encrypt hello! 3` would return `khoor!`.
- Users can input a message with both upper and lowercase letters, and the case is preserved in the encrypted message. For example, `encrypt Hello 3` would return `Khoor`.
- Users can see an error message if they input an invalid key or message. For example, `encrypt hello 0` would return an error message.

#### Vigenère cipher

- Users can input a message and a key to encrypt a message by shifting each letter in the message by the corresponding letter in the key. For example, `encrypt hello abc` would return `hfnlp`.
- Users can input a message and a key to decrypt a message by shifting each letter in the message by the corresponding letter in the key. For example, `decrypt hfnlp abc` would return `hello`.
- Keywords are repeated recursively if the message is longer than the key.
- Users can see an error message if they input an invalid key or message. For example, `encrypt hello 123xyz` would return an error message.
- Users can analyze the message's frequency to determine the most likely key. For example, `frequency hello` would return the most likely key.
- Users can input non-alphabetic characters in the message, which are not encrypted. For example, `encrypt hello! abc` would return `hfnlp!`.
- Users can input a message with both upper and lowercase letters, and the case is preserved in the encrypted message. For example, `encrypt Hello abc` would return `Hfnlp`.
- Users can see an error message if they input an invalid key or message. For example, `encrypt "" 0` would return an error message.

#### Overall requirements

- Users can start the app by running the `main` method in the `App` class.
- Users can use the `help` subcommand to see a list of commands.
- The app is deployed online so that the rest of the world can use it.
- You are shown as the only contributor to the project on GitHub.

### Minimum requirements - maze generator and solver

> ✅ If you build a maze generator and solver project, any items marked incomplete in this section will result in the project receiving a failing grade.

#### Maze generator and solver

- Users can input the height and width to generate a maze.

  - Example command: `generate 10x10`
  - Example output:

    ```bash
    ##############
    #S     #     #
    # ### # ### ##
    #   # #   #  #
    ### # ### # ##
    #   #     #  #
    # ##### ### ##
    # #   #     ##
    ### # #####  #
    #     #   #  #
    ############E#
    
    # S = Start
    # E = Exit 
    # # = Wall
    # Space = Open Path
    ```

- Users can input mathematical expressions to customize the maze generation. For example, `generate (5 + 3 * 2)x(5 * 2)` would generate a 16x10 maze.
- Users can input `dfs` to solve the maze using a depth-first search algorithm.

  - Example command: `solve dfs`
  - Example output:

    ```bash
    ##############
    #S*****#     #
    #*###*#*### ##
    #*  #*#*  #  #
    ###*#*###*# ##
    #***#*****#  #
    #*#####*### ##
    #*#   #*****##
    ### # #####* #
    #     #***#* #
    ############E#
    
    # S = Start
    # E = Exit 
    # # = Wall
    # Space = Open Path
    # * = Path
    ```

- Users can input `bfs` to solve the maze using a breadth-first search algorithm. For example, `solve bfs` would solve the maze using a breadth-first search algorithm.
- Users can input `a*` to solve the maze using an A\* or Dijkstra's search algorithm. For example, `solve a*` would solve the maze using an A\* or Dijkstra's search algorithm.
- Users can use `all` to solve the maze using all three algorithms and see the output of the common path between the three algorithms or a message of `No common path`.

  - Example command: `solve all`
  - Example output:

    ```bash
    # Common Path
    
    ##############
    #S*****#     #
    #*###*#*### ##
    #*  #*#*  #  #
    ###*#*###*# ##
    #***#*****#  #
    #*#####*### ##
    #*#   #*****##
    ### # #####* #
    #     #***#* #
    ############E#
    ```

- Users can manipulate the maze by adding or removing walls. For example, `add 1,1` would add a wall at the coordinate 1,1.
- Users can save the maze as a binary string to a file. For example, `save maze.bin` would save the maze to a file named `maze.bin`.
- Users can load a maze from a file. For example, `load maze.bin` would load the maze from a file named `maze.bin`.
- Users can see an error message if they input an invalid command. For example, `generate 0x0` or `add 1,1,1` would return an error message.

#### Overall requirements

- Users can start the app by running the `main` method in the `App` class.
- Users can use the `help` subcommand to see a list of commands.
- The app is deployed online so that the rest of the world can use it.
- You are shown as the only contributor to the project on GitHub.

### Convention requirements

> ✅ More than two items marked incomplete in this section will result in the project receiving a failing grade.

- The files in the app are organized following the conventions demonstrated in lectures.
- The code in the app adheres to coding conventions covered in lessons, like using plural names for arrays.
- The app does not contain dead code, commented-out sections, or console logs.
- The app can be used without encountering errors.
- The app is coded using proper indentation.
- The GitHub repository used for the project must be named appropriately. For example, names that describe your project are appropriate, whereas generic names such as `ga-project` or `unit-project` are not.

## README requirements

> ✅ More than two items marked incomplete in this section will result in the project receiving a failing grade.

- The app's name.
- A brief description of your app and its functionality.
- A **Getting started** section. This section should include instructions on how to use your app.
- A **Technologies used** section. This section should list the principal technologies used by your application, including any major frameworks or libraries.
- If necessary, an **Attributions** section. This section should include links to any external resources (such as libraries or assets) you used to develop your application that require attribution. You can exclude this section if it does not apply to your application.

## Evaluation

Your instructional team will evaluate your project after the project's due date. Your instructors will use the above guidelines to determine whether or not your project meets all of the minimum requirements.

If there is a specific section of code that you would like an instructor to provide additional feedback on, please ask!

### Level Up - RSA encryption

> ✅ Level Up objectives are optional. You do not need to complete any of the following objectives to pass the project. However, you are encouraged to complete any or all of these objectives if you have time and want to differentiate your project further.

- Users can generate a pair of RSA public and private keys by providing two prime numbers. For example, `generate 61 53` would generate a public and private key pair.
- Public and private keys are generated by finding the greatest common divisor of the two prime numbers using the binary Euclidean algorithm.
- Users can save the public and private keys to a file. For example, `generate 61 53 --save` would save the public and private keys to different files (`public_key.txt` and `private_key.txt`).
- Users can see an error if the prime numbers are not prime or if the prime numbers are too small. For example, `generate 1 1` would return an error message.
- Users can encrypt a message using the public key. For example, `encrypt "hello world" public_key.txt` would return the encrypted message.
- Users can decrypt a message using the private key. For example, `decrypt "encrypted message" private_key.txt` would return the decrypted message.
- Users can see an error message if they use an invalid key or message. For example, `encrypt "hello world" invalid_key.txt` would return an error message if the public key is invalid.

## Guidance

### Getting started

Here are some quick tips to get your project started:

- Discuss your app idea with an instructor to get feedback before you dive too deep into planning.
- ***Keep it simple.*** Minimum Viable Product (MVP) functionality that looks great and works well is better than extra functionality added to an app without polish.
- Theme your app to give it a personal touch.
- Prioritize and implement new functionality to your project step-by-step, one at a time. Develop features in a way that allows you to test as you go - try your best to follow the flow of data through your app.
- Regularly review the project requirements to ensure you're on track to pass the project. A printable version of the project requirements can be found [here](./assets/project-requirements.pdf).
- Add comments to your code where it makes sense to do so. Most code is self-documenting, and you shouldn't add comments explaining the obvious. Ideally, comments should explain the ***why*** of code where it's necessary.

### Project assistance

Your instructor team will provide guidelines for reaching out for help while you're working on your project.
