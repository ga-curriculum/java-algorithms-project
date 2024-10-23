<h1>
  <span class="headline">Java Algorithms Project</span>
  <span class="subhead">Requirements and Guidance</span>
</h1>

## Overview

In this project, you will build a Cipher Algorithms or Maze Generation and Solver application that users interact with via the command line. This project focuses on demonstrating your understanding of algorithms and data structures in Java. No matter which project you choose, you must implement various features to meet the minimum requirements. The users of each application should be able to select from multiple commands to interact with the application and see the results of their commands. Choose from:

- Cipher Algorithms - Ceasar Cipher and Vignere Cipher
- Maze Generation and Solver

**Bonus, in addition to one of the projects above:**

- RSA Encryption with Key Generation using Trees

***You will work individually on this project***.

> ❗️ As a reminder, General Assembly has a zero-plagiarism policy. ***Your project's code must be substantially yours***. Do not copy code from similar projects or other sources. However, using code from the internet to accomplish generic tasks is okay - for example, a line of code that replaces a character at a specific position in a string.

A printable version of the project requirements can be found [here](./assets/project-requirements.pdf).

## Technical requirements

### Minimum Requirements

> ✅ Any items marked incomplete in this section will result in the project receiving a failing grade.

#### Cipher Algorithms

#### Ceasar Cipher

- Users can input a message and a key to encrypt a message by shifting each letter in the message by the key. Example: `encrypt hello 3` would return `khoor`.
- Users can input a message and a key to decrypt a message by shifting each letter in the message by the key. Example: `decrypt khoor 3` would return `hello`.
- Users can undo the last encryption using a stack-based undo system. Example: `undo` would return the message to the state before the last encryption.
- Users can undo the last decryption using a stack-based undo system. Example: `undo` would return the message to the state before the last decryption.
- Users can input non-alphabetic characters in the message that are not encrypted. Example: `encrypt hello! 3` would return `khoor!`.
- Users can input a message with both upper and lowercase letters, and the case is preserved in the encrypted message. Example: `encrypt Hello 3` would return `Khoor`.
- Users can see an error message if they input an invalid key or message. Example: `encrypt hello 0` would return an error message.

#### Vignere Cipher

- Users can input a message and a key to encrypt a message by shifting each letter in the message by the corresponding letter in the key. Example: `encrypt hello abc` would return `hfnlp`.
- Users can input a message and a key to decrypt a message by shifting each letter in the message by the corresponding letter in the key. Example: `decrypt hfnlp abc` would return `hello`.
- Keywords are repeated recursively if the message is longer than the key.
- Users can see an error message if they input an invalid key or message. Example: `encrypt hello 123xyz` would return an error message.
- Users can analyze the message's frequency to determine the most likely key. Example: `frequency hello` would return the most likely key.
- Users can input non-alphabetic characters in the message, which are not encrypted. Example: `encrypt hello! abc` would return `hfnlp!`.
- Users can input a message with both upper and lowercase letters, and the case is preserved in the encrypted message. Example: `encrypt Hello abc` would return `Hfnlp`.
- Users can see an error message if they input an invalid key or message. Example: `encrypt "" 0` would return an error message.

#### Maze Generation and Solver

- Users can input the height and width to generate a maze.

Example command: `generate 10x10`
Example Output:

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
- Users can input mathematical expressions to customize the maze generation. Example: `generate (5 + 3 * 2)x(5 * 2)` would generate a 16x10 maze.
- Users can input `dfs` to solve the maze using a depth-first search algorithm. 

Example command: `solve dfs`
Example Output:

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

- Users can input `bfs` to solve the maze using a breadth-first search algorithm. Example: `solve bfs` would solve the maze using a breadth-first search algorithm.
- Users can input `a*` to solve the maze using an A* or Dijkstra’s search algorithm. Example: `solve a*` would solve the maze using an A* or Dijkstra’s search algorithm.
- Users can use `all` to solve the maze using all three algorithms and see the output of the common path between the three algorithms or a message of `No common path`.

Example Command: `solve all`
Example Output:

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

- Users can manipulate the maze by adding or removing walls. Example: `add 1,1` would add a wall at the coordinate 1,1.
- Users can save the maze as a binary string to a file. Example: `save maze.bin` would save the maze to a file named `maze.bin`.
- Users can load a maze from a file. Example: `load maze.bin` would load the maze from a file named `maze.bin`.
- Users can see an error message if they input an invalid command. Example: `generate 0x0` or `add 1,1,1` would return an error message.

### Strech Goals

Stretch goals are optional. You do not need to complete any stretch goals to pass the project. However, you are encouraged to complete them if you have time.

#### RSA Encryption

- Users can generate a pair of RSA public and private keys by providing two prime numbers. Example: `generate 61 53` would generate a public and private key pair.
- Public and private keys are generated by finding the greatest common divisor of the two prime numbers using the binary Euclidean algorithm.
- Users can save the public and private keys to a file. Example: `generate 61 53 --save` would save the public and private keys to different files (`public_key.txt` and `private_key.txt`).
- Users can see an error if the prime numbers are not prime or if the prime numbers are too small. Example: `generate 1 1` would return an error message.
- Users can encrypt a message using the public key. Example: `encrypt "hello world" public_key.txt` would return the encrypted message.
- Users can decrypt a message using the private key. Example: `decrypt "encrypted message" private_key.txt` would return the decrypted message.
- Users can see an error message if they use an invalid key or message. Example: `encrypt "hello world" invalid_key.txt` would return an error message if the public key is invalid.

#### Overall requirements

- Users can start the app by running the `main` method in the `App` class.
- Users can input `help` to see a list of commands.
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

Your instructional team will evaluate your project after the project’s due date. Your instructors will use the above guidelines to determine whether or not your project meets all of the minimum requirements.

If there is a specific section of code that you would like an instructor to provide additional feedback on, please ask!

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
