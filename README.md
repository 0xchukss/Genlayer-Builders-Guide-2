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

# NOTE; test to see if everything works as you want, then proceed to pushing into github

## create a github repository
visit [github](https://github.com)
sign in with your account and create a repository

# important: do not toggle on read.me, gitignore or license when creating your project github repo

## create a gitignore file
make sure you are in the projects main folder then run,
<pre>
  node_modules
.env
dist
__pycache__
</pre>

<img width="636" height="117" alt="create gitignore" src="https://github.com/user-attachments/assets/8682cbee-cc3c-46d0-b762-d3d49ea45582" />

## set your email
run this, anything works here lol
<pre>
  git config --global user.email "kek@example.com"
</pre>

<img width="589" height="85" alt="set username chuks for git" src="https://github.com/user-attachments/assets/bdcff862-1adf-4605-b91b-c740e916ef33" />

## set username
run,
<pre>
  git config --global user.name "anyname"
</pre>

## add to main repo and final commit
run
<pre>
  git init
git add .
git commit -m "i am doing my best kek"
</pre>

<img width="529" height="268" alt="make commit changes final" src="https://github.com/user-attachments/assets/915c56af-b876-40e3-a3d2-1f8865f877ee" />

you can replace "i am doing my best kek" to actually anything

## push to github
run,

#### note; replace the first url with the url of your github repo
e.g i replaced mine to https://github.com/0xchukss/genlayer-explorer.git

<pre>
 git remote add origin https://github.com/YOUR_USERNAME/repositoryname.git
git branch -M main
git push -u origin main
</pre>

<img width="712" height="81" alt="push to github" src="https://github.com/user-attachments/assets/3631d3ee-70b4-4894-864c-18cd46155c2d" />

you will be asked for your github username and password
- input your username
- for password, create a personal access token in your github

 ### how to create personal access token:
- go to your github settings
- navigate to developer settings
- then create personal access token
- use tokens (classic)
- select no expiration
- name it as "vercel"
- tick only "repo"
- scroll down and generate token
- copy token and paste as the password on your terminal
- enter
- this should push to github and you can see it on you github
- 
<img width="1847" height="751" alt="pat" src="https://github.com/user-attachments/assets/7f6f2e8c-1c4b-4c46-ac22-b6fb6645013f" />

## deploy on vercel
- visit [vercel](https://vercel.com)
- signin with your github
- click on add new and select project
- you should see the latest github repos on your github

<img width="878" height="407" alt="image" src="https://github.com/user-attachments/assets/744ca396-951a-4790-981a-49ae0083af76" />

- select your project repo and import
- on root directory click edit and choose frontend

 <img width="782" height="418" alt="edit and deploy on vercel" src="https://github.com/user-attachments/assets/34dd4e0b-5716-499d-89d2-d95e91dd5e68" />

 - open up environment variables,
   input; VITE_CONTRACT_ADDRESS in key section and your contract address in the value section

- finally, you can deploy

## making it public
- after deployment, go to dashboard and locate your newly deployed project
- click on the three dots and select settings

<img width="1800" height="750" alt="damn" src="https://github.com/user-attachments/assets/b6d5bf46-5518-4ea4-afbf-0c90d1751a5b" />

- go to deployment protection and turn vercel authentication off
- then save
- you can now share ypur project with youe friends

<img width="1708" height="720" alt="h,mm" src="https://github.com/user-attachments/assets/963c4709-2f68-465c-8be7-50ceb6c9e75a" />

# GUIDE MADE BY CHUKSDAKINGS, [X](https://x.com/chuksdakingz)






