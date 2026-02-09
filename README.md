# Genlayer-Builders-Guide-2

# Requirements:
- docker
- wsl
- vsCode
- Rabby wallet extension
- Node.js (v18+) & npm
- Python (v3.10+)

## Note: we will be deploying on studionet

# step 1
## install genlayer cli
<pre>
  npm install -g genlayer
</pre>

## create project folder
<pre>
  mkdir yourProjectName
</pre>

navigate to project folder
<pre>
  cd yourProjectName
</pre>

create contracts and frontend folder inside project folder
<pre>
  mkdir contracts
</pre>

<pre>
  mkdir frontend
</pre>  

<img width="914" height="436" alt="mkdir contracts and frontend" src="https://github.com/user-attachments/assets/9cd0d83a-f671-498c-9b7f-387a4a1cea2c" />


# step 2
## initialize genlayer blockchain with your docker
<pre>
  genlayer init
</pre>

<img width="547" height="170" alt="git init" src="https://github.com/user-attachments/assets/5434b45e-94f1-4a20-9c4d-580101f992a9" />

you will be asked to select LLM type and provide API keys
- use heurist ai
- visit [heurist](https://dev-api-form.heurist.ai)
- use "genlayer" as ref code to get free api credits
- get your credits and use it to run the initialization
  
#### if this does not work, try the following;
- run
  <pre>
    docker pull postgres:17-alpine
  </pre>

#### if you still encounter issues, pull the images from docker manually
  
  <img width="941" height="425" alt="manually pull images" src="https://github.com/user-attachments/assets/7a645f23-cb7b-40f7-983e-26adfacbfa03" />

after getting thr initialization started, run
<pre>
  genlayer up
</pre>

to start up the blockchain

# step 3 creating and deploying your contract
to create your own contract please read the genlayer [docs](https://docs.genlayer.com/developers/intelligent-contracts/first-contract)
or you can feed the genlayer [docs](https://docs.genlayer.com/full-documentation.txt) to any ai and ask it to write a smart contract depending on what you intend to create

## creating your contract file
i believe you must have your smart contract written down already
- in your terminal, run
<pre>
  code .
</pre>

<img width="753" height="491" alt="image" src="https://github.com/user-attachments/assets/1c8d5e8e-5dd7-4442-88d4-102d79c7113d" />

this opens up your project folder inside vsCode editor (from here you can make simple copy and paste edits to your project files)
- right click on the contracts folder and create a new file (name it according to your project, eg, fight.py since genlayer contracts are written in python)
- paste you contract code into the file and save

#### set at studionet
go back to your terminal and run
<pre>
  genlayer network set studionet
</pre>

<img width="595" height="100" alt="create studionet deployer" src="https://github.com/user-attachments/assets/0c35624b-78d7-4ebb-b98d-bd2a7eebd1fa" />

#### create deployer account
<pre>
  genlayer account create --name studio-deployer
genlayer account use studio-deployer
</pre>

<img width="468" height="100" alt="create and set acct" src="https://github.com/user-attachments/assets/5137ddf2-f715-4162-8e2f-57cf56ef410f" />

you will be asked to setup an encryption key (password)

#### deploy contract to genlayer studionet
<pre>
  genlayer deploy --contract contracts/yourContractName.py
</pre>

enter password to deploy, copy your contract address (you will make use of it in setting up your .env file)



