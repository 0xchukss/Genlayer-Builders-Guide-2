# Genlayer-Builders-Guide-2

# Requirements:
- docker
- wsl
- vsCode
- Rabby wallet extension
- Node.js (v18+) & npm
- Python (v3.10+)

## Note: we will be deploying first on localnet and its rpc so we can test locally before deploying on studionet

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
to create your own contract please read the genlayer docs [docs](https://docs.genlayer.com/developers/intelligent-contracts/first-contract)

