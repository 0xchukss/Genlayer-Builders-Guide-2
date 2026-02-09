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

# step 2
## initialize genlayer blockchain with your docker
<pre>
  genlayer init
</pre>

<img width="547" height="170" alt="git init" src="https://github.com/user-attachments/assets/5434b45e-94f1-4a20-9c4d-580101f992a9" />
<img width="547" height="170" alt="git init" src="https://github.com/user-attachments/assets/5434b45e-94f1-4a20-9c4d-580101f992a9" />

if this does not work, try the following;
- run
  <pre>
    docker pull postgres:17-alpine
  </pre>

  if you still encounter issues, pull the images from docker manually
  
