# Goodboy-Cube
A deep learning and search based Rubik's Cube that tries its best to solve any scramble


https://github.com/death4slash/Goodboy-Cube/assets/96627029/f442eb72-dce5-4676-aae1-9beac6bffcf7


Download the Project here

https://drive.google.com/file/d/1xJijPxozg2fcaedx1gSYDewNT8NglzB3/view?usp=sharing

These are the prerequisites required to run this project:
PyTorch--Tensorboard--Flash--Three.js--Tween.js
-----------------------------------------------------------------------------------------------------------------
Following packages are needed to run the
complete Cube through flash servers and 
monitor the learning using tensor.
-----------------------------------------------------------------------------------------------------------------
Python modules(pip required)
PyTorch:
	pip install torch===1.7.1 torchvision===0.8.2 torchaudio===0.7.2 -f https://download.pytorch.org/whl/torch_stable.html
-----------------------------------------------------------------------------------------------------------------
Flask:
	pip install -U Flask flask-restful flask-cors
-----------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------
Javascript modules
--Run these commands inside the CubeGUI folder--
Three.js
	npm install --save three
-----------------------------------------------------------------------------------------------------------------
Tween.js
	git clone https://github.com/tweenjs/tween.js
	cd tween.js
-----------------------------------------------------------------------------------------------------------------
Now build using the following commands.
	npm i .
	npm run build

USING THE CODE
Training New Model
A new model can be trained using the following command in cmd.exe inside the main folder.
	python train.py -c config/cube3.ini -mp True
For training the 2x2 cube, use the following command
	python train.py -c config/cube2.ini -mp True
This creates a new network file inside the saves folder.
-----------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------
Training Existent Model
For an existing model just replace "YourNetworkHere" in the given command with the name of 
your exiting network inside the saves folder.
	python train.py -c config/cube3.ini -nt saves\YourNetworkHere.pt -mp True
For 2x2 cube use the following command
	python train.py -c config/cube2.ini -nt saves\YourNetworkHere.pt -mp True
These can also be used to restart training if it was interrupted
-----------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------
Tracking the Progress
The progress of your run can be tracked using tensorboard, through the following command.
	tensorboard --logdir=runs
-----------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------
Testing Your Model
To test your current model, you can put your replace "YourNetworkHere" in the given command with the name of 
your trained network.
	python solve.py -n saves/YourNetworkHere.pt -c config/cube3.ini 
for 2x2 cube, use the following command. Make sure to use the correct network in each case(3x3 or 2x2).
	python solve.py -n saves/YourNetworkHere.pt -c config/cube2.ini 
-----------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------
Running the Cube GUI
The graphic interface is made in javascript. You can use the index.html file and create a local server.
Sending and receiving the data is done using the Flask API
For creation of local server, I recommend using live server extension in visual studio code. Here you can rightclick
anywhere in index.htm and click open with live server.
For the creation of flask server use the following command 
	python cubeAPI.py -n2 saves/Your2x2NetworkHere.pt -n3 saves/Your3x3NetworkHere.pt -c2 config/cube2.ini -c3 config/cube3.ini
-----------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------
I have included 1 network for each of the cubes. They are created using the simple network system. You can create
a different one just by changing the network type in the configuration folders.
-----------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------
Now you should have a working copy of the Good Boy Cube that tries his 
best to solve any cube state for a 3x3 and 2x2 cube.
Keep running it so it turns into a Big Boy Cube someday thanks to reinforcement learning.
