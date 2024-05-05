# Security-Audit
## SolGraph
### Image Pull 
```
docker pull devopstestlab/solgraph
```
### Directory
First of all we have to create a directory
```
mkdir <"dir name">
```
then enter the newly made directory
```
cd <"dir name">
```
Then we have to create a MyContract File
```
touch MyContract.sol
```
Edit this file and Enter the MyContract.sol contents
### Run Solgraph
```
docker run -it --rm -v $PWD:/data devopstestlab/solgraph
```
It will return output as your files name i.e. MyContract.sol

Now the graph is generated succesfully, To view it -
```
xdg-open MyContract.sol.png
```
![graph](https://github.com/DamanAhuja/Security-Audit/assets/142963733/8a3a2ea4-0ffd-44d0-892f-33e8d16bd23a)
## Slither
### Pull Image
```
docker pull trailofbits/eth-security-toolbox
```
### Run
```
docker run -it --rm -v $PWD:/data trailofbits/eth-security-toolbox
```
![tob](https://github.com/DamanAhuja/Security-Audit/assets/142963733/8a6f3ce6-32ea-4339-b97c-44e4c8dc7d08)
Now open another terminal,
Enter the Root directory
```
cd <"dir name">
```
And we then check the container's list
```
sudo docker container ls
```
<img width="1071" alt="container" src="https://github.com/DamanAhuja/Security-Audit/assets/142963733/d0dd6233-ce1f-4da4-a9ef-63145dacc086">
The output will be some details about the container, we need container ID for our future reference

Now - 
```
sudo docker cp $(pwd)/<"filename.sol"> <“put-containner-id”>:/home/ethsec
// replace the required fields
```
### Back to our original Terminal
```
slither MyContact.sol
// instead of MyContact.sol write your file's name
```
![image](https://github.com/DamanAhuja/Security-Audit/assets/142963733/646e473d-f291-460e-9072-243be21ade7b)
2nd Command - 
```
slither-check-erc MyContract.sol Persssist
// if you are using any other MyContract file then instead of "Persssist" add the contract name in the file
```
![image](https://github.com/DamanAhuja/Security-Audit/assets/142963733/6fcd5d51-03ee-49b3-ae48-02c14dfdf1cb)
