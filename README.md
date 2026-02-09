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

create contracts 
<pre>
  mkdir contracts
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

you will be asked to setup an encryption key (password)

#### deploy contract to genlayer studionet
<pre>
  genlayer deploy --contract contracts/yourContractName.py
</pre>

enter password to deploy, copy your contract address (you will make use of it in setting up your .env file)

# step 4 creating the frontend logic
#### create a vue frontend template
run, in the project folder
<pre>
  npm create vite@latest frontend -- --template vue-ts
</pre>

move into frontend folder,
<pre>
  cd frontend
</pre>

install vue
<pre>
  npm install
</pre>

install genlayer SDK
<pre>
  npm install genlayer-js
</pre>

#### create environment
create a .env file inside the frontend folder and input this below

<img width="246" height="403" alt="create  env" src="https://github.com/user-attachments/assets/a7e307da-6097-4063-bda5-66cb28d06ace" />

<pre>
  VITE_CONTRACT_ADDRESS=0xYOUR_COPIED_ADDRESS
</pre>
replace 0xYOUR_COPIED_ADDRESS with the contract address deployed earlier

#### editing App.vue and styles.css 
navigate to frontend/src/styles.css and delete everything inside the file

<img width="678" height="353" alt="image" src="https://github.com/user-attachments/assets/4278211a-e2d3-4f97-b968-aaeba6372ebd" />

- your main frontend code will be stored inside App.vue
- if you cannot write that seek help from an ai

<img width="824" height="443" alt="image" src="https://github.com/user-attachments/assets/dd02b2e8-c994-4f50-a6e4-dacc550346bc" />


after filling in your frontend, save it

#### run the frontend
in your terminal, make sure your are inside the frontend directory
run,
<pre>
  npm run dev
</pre>

<img width="521" height="250" alt="image" src="https://github.com/user-attachments/assets/13377652-c907-4b7b-b893-7c5d05ca2bcc" />

it should provide a localhost address like this [http://localhost:5173/] that you can open on your browser

<img width="958" height="448" alt="image" src="https://github.com/user-attachments/assets/4afb130c-7986-4130-a48f-28e1fed8c431" />

