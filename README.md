# Number Discerner

This repo is a simple example of how to build a number discerner using [BrainJS](https://brain.js.org/#/).

It features a neural network that takes, as an input, a number (expected to be between 0 and 9) drawn by users on a grid in an HTML form, and returns its best guess as to what that number is.

## Usage

Clone (or just download) the repo to your local drive, and then open `number-evaluator.html` in your browser of choice.

Draw a number between 0 and 9 on the grid. Click `Get Assessment` to see results. The network will return a set of ten values between 0 and 1, which each represents the network's confidence that that particular number is the one drawn. The entry with the highest value represents, essentially, the network's conclusion about what number the user drew.

## Network Persistence

Each time you run the program, the code instantiates and trains a neural network to detect numbers. Normally, of course, you would want to use a pre-built model for each operation, but it is written here to spin up fresh each time to show how it is made (and also because the relatively small amount of training data makes this possible).

## Augmenting or Altering the Network's Training

You can change how the network is trained by adding or removing training rows in the `getTrainingData()` function (in `number-evaluator.html`). Doing so will likely change how accurately the network can make a determination about a number given to it.

To add more training data for the network, you can use the `training-data-recorder.html` file.

Open the file in a browser, and draw a number in the grid like you did for the one in the `number-evaluator.html` file. To create a row of training data, click the radio button next to the number you wish to categorize the number as for the network, draw a number in the grid (if you haven't already), and click `Record Input`. This creates a new row of data formatted in the way that the neural network created in `number-evaluator.html` will understand. You can click `Copy Data` at this point to add the data to your clipboard (and which you can then paste into the `getTrainingData()` function in `number-evaluator.html`).
