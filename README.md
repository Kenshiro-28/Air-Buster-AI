# Air Buster AI

This is an Air Buster artificial intelligence based on the T-Rex evolutionary neural network. It trains playing the game until it's unable to improve its best score. After completing the training, the program plays a last game rendering the game screen.

## Game information

Air Buster is a horizontal-scrolling shoot-em-up arcade game developed by Kaneko. In Japan, the arcade version was published by Namco, while in North America the arcade version was published by Sharp Image Electronics. Two players control the "Blaster Fighter" star ships in their efforts to destroy a mysterious mechanical fortress orbiting Earth, with plans to take control of the planet. The Blaster Fighters can equip one of seven available weapons, which will change the ship's firepower and abilities, such as diagonal shots, homing missiles and small drones that follow the player's ship.

Air Buster received a favorable reception for its visuals, sound effects and gameplay. Ports of the game were released for both the TurboGrafx-16 and Sega Genesis, the former being renamed to Aero Blasters for international releases. The Sega Genesis release was ported over to the "Project EGG" digital storefront in 2014, which remained exclusive to Japan. 

This program uses the Sega Genesis console emulator provided by OpenAI Gym Retro.

## Neural network information

T-Rex is an evolutionary neural network. It learns by adjusting the strength of the connection weights by mutation and selection. The programmer must define the problem to solve with a scoring system so that T-Rex can evolve gradually until finding the optimal solution.

Main features:

- Binary feedforward neural network
- Configurable number of inputs, hidden layers and outputs
- Developed using object-oriented programming
- Fast, robust and portable

### Input layer

The input of the neural network is the screen output of the Sega Genesis console. The original image is processed with Canny edge detection to extract useful structural information and dramatically reduce the amount of data to be processed. Finally, the image resolution is reduced to one tenth of its original size. The input layer has 5734 neurons.

### Hidden layers

The neural network has 10 hidden layers. The T-Rex architecture states that the number of neurons in each hidden layer is set as the number of input neurons so they have 5734 neurons.

### Output layer

The neural network outputs are the button activations on the player's gamepad. As the game emulation provides 12 buttons, the output layer has 12 neurons.

## Installing dependencies

### T-Rex

You must compile T-Rex as a shared library:

https://github.com/Kenshiro-28/T-Rex

Copy the generated file **libT-Rex.so** in the folder /usr/local/lib

### Python

Run this command to install Python:

```
$ sudo apt install python3-dev python3-pip python3-wheel python3-opencv
```

### OpenAI Gym Retro

Run this command to install OpenAI Gym Retro:

```
$ pip3 install gym-retro
```

### Game ROM

This program has been tested with the USA version of the game. Run this command in the folder containing the ROM file:

```
$ python3 -m retro.import ./
```

## Running

Run this command in the root folder to start the program:

```
$ python3 air-buster.py
```

This project includes a trained neural network. Running the program will skip the training phase if there is a neural network file in the same folder. To train a new neural network, delete the file **neural_network.json**.

----- Work in progress -----
