# Avalanche-HyperSDK-Module2
The HyperSDK is a powerful framework that simplifies the development of blockchain applications on the Avalanche network. It provides the tools and libraries necessary to easily create customized blockchain protocols with a focus on speed, scalability, and security. With the HyperSDK, developers can quickly deploy decentralized applications, making the development process more efficient and simple.

## Description
HyperSDK is better than using a traditional subnet in Avalanche because it provides a flexible and efficient development framework for building custom blockchain applications while subnets allow for flexibility, HyperSDK goes further to build and deploy tools and custom libraries play a key role to provide network speed, scalability and security They reduce complexity and time requirements, making it a more efficient option for developers who want to leverage the full potential of Avalanche Networks without they are not involved in the complexities of subnet design and management

## Getting Started
- Vedio explanation of the project work.
  
  https://www.loom.com/share/54a3fc1ab9a14757b1c5e3291e749bd0?sid=49b0fa05-e6f7-4e54-a961-caad3c26d85b

### Installing
- For creating a custom virtual machine we first need to install the go compiler [https://go.dev/doc/install] from here.
- Then we have to run {go mod tidy} to normalize all the dependencies in our project folder.
-  Afterwards we have to configure the project constants by going on consts/consts.go then we have to add the missing code in the registry/registry.go
  // TODO: register action: actions.CreateAsset
		consts.ActionRegistry.Register(&actions.CreateAsset{}, actions.UnmarshalCreateAsset, false),
		// TODO: register action: actions.MintAsset
		consts.ActionRegistry.Register(&actions.MintAsset{}, actions.UnmarshalMintAsset, false),
- Then check the go compiler version of ours

  
- Then [./scripts/run.sh;] run this command for launching the subnet and for one run this command also [Run MODE="run-single" ./scripts/run.sh].
- To interact with the tokenvm, implement the token-cli. Next, we'll need to build this. by using this command[./scripts/build.sh]
- This command will put the compiled CLI in ./build/token-cli._
- Lastly, we'll need to add the chains that we created and the default key to the token-cli. we can use the following commands [./build/token-cli key import demo.pk]
  [./build/token-cli chain import-anr]

### Executing program
- Firstly we are going to create our asset for that we have to run command [./build/token-cli action create-asset] then it will give the address and chainID , then asks for the metadata where we have to provide our chain name.
  <img width="1049" alt="mint" src="https://github.com/user-attachments/assets/75f00c73-063e-4a4b-9b69-ca17b3341a7b">

<img width="1049" alt="Screenshot 2024-08-12 at 11 04 50 PM" src="https://github.com/user-attachments/assets/97f922be-d9e1-43da-80ed-34617934479e">


- After successful creation we are going to mint using the following command [./build/token-cli action mint-asset] then after running this command we have to provide our assetID which is similar to our txID (so copy and give it to the assetID) then it will ask for the value so give some and type 'y' for confirmation.

<img width="1049" alt="Screenshot 2024-08-12 at 11 04 57 PM" src="https://github.com/user-attachments/assets/877b4434-7312-4dcc-b613-d67e8d8a9bb8">


- Then we will be going to check/view our balance using  command [./build/token-cli key balance] here also we have to give the assetID which is similar to the txID.
  
<img width="1049" alt="Screenshot 2024-08-12 at 11 05 10 PM" src="https://github.com/user-attachments/assets/5e4791dd-0856-4cdb-850f-379c93240ab5">
<img width="1049" alt="Screenshot 2024-08-12 at 11 05 21 PM" src="https://github.com/user-attachments/assets/767f508c-960e-4f01-a2f5-3dbc0fbdeaed">
<img width="1049" alt="Screenshot 2024-08-12 at 11 05 45 PM" src="https://github.com/user-attachments/assets/4d1b52ed-f85f-46cc-bb41-d18f071c3956">


- We are having some command which we can also  use for different functionalities
./build/token-cli action create-order
./build/token-cli action fill-order
./build/token-cli action close-order
./build/token-cli chain watch
./build/token-cli chain watch
./build/token-cli action export
./scripts/tests.load.sh
./scripts/tests.disk.sh

- At the end for closing our Local Avalanche Network , we have to run [killall avalanche-network-runner]

## Authors

Manish Kumar 
(https://www.linkedin.com/in/manish-kmr/)
