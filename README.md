# SOLIS public repository

This repo contains public source code and intermediate results from SOLIS research and development.

SolisBoxChecker is a open-source mini-app developed in Python that uses Pytorch and Tensorflow frameworks. This application can be used as a test tool in order to test different deployment setups on a wide range of hardware and software setups.
See at the bottom of readme instructions regarding IPC tests between python modules on SolisBox devices.

## Preparing NVIDIA Jetson environment:
In order to setup NVIDIA Jetson envrionment you can access following pdf for a stept-by-step tutorial:
[Jetson Setup](https://github.com/Lummetry/SolisPublic/blob/main/results/JetsonSetup.pdf).
Please note that this step-by-step tutorial has been done using a TX2 Developer Kit device.

## Preparing non-Jetson environments:
1. Install Anaconda or Minicoda
2. Run environment setup:
```
    conda create -n vaporbox anaconda opencv python=3.7
    conda activate vaporbox
    conda install -c anaconda tensorflow-gpu==2.1.0
    conda install pytorch torchvision -c pytorch
```
    
## Running SolisBoxChecker
1. Git clone the project (including submodules): 
    <br>`git clone https://github.com/Lummetry/SolisPublic.git --recurse-submodules`
2. Go to project folder: `cd SolisPubic`
3. Run: `python run.py`
4. Wait for script to run and check results
5. Send results to Lummetry Team as indicated in the script results

## Example outputs:
Below you can find a range of outputs after testing the script on different operating systems, hardware platforms and environment setups.

1. Windows Results:

![Windows Results](https://github.com/Lummetry/SolisPublic/blob/main/results/windows.png)

2. Ubuntu Results:

![Ubuntu Results](https://github.com/Lummetry/SolisPublic/blob/main/results/ubuntu.png)

3. MacOS Results:

![MacOS Results](https://github.com/Lummetry/SolisPublic/blob/main/results/macos.png)

4. JetsonTX2 Results:

![JetsonTX2 Results](https://github.com/Lummetry/SolisPublic/blob/main/results/jetson.png)


## IPC Tests

After cloning repo run proceed with the following steps:

1. Start a shell and enter folder where repo has been cloned then run:
```
>cd ipc_test
>python server.py
```
2. Start a second shell from the same repo folder and run:
```
>cd ipc_test
>python client.py
```
_OBS: if you start the shell in `(repo_folder)/ipc_test` directly then you can bypass the `cd` command_

Now you should see outputs from both client and server as below. The simulation takes into accounting both inference as well as 
post processing operations on the data received from the "transcoder".
Provided source code has various comments and suggestions.

#### Server output
![Server](https://github.com/Lummetry/SolisPublic/blob/main/results/ipc_img1.png)
#### Client output
![Client](https://github.com/Lummetry/SolisPublic/blob/main/results/ipc_img2.png)

