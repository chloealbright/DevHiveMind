node js is connected to npm when installing node js your installing npm which is package manager nvm is node version manager basically controlling the version your using.

  
sudo pacman -S nodejs npm  
  
 

install node js

---------------------

[https://github.com/nodesource/distributions/blob/master/README.md](https://github.com/nodesource/distributions/blob/master/README.md)

install nvm

---------------------

[https://github.com/nvm-sh/nvm#:~:text=GitHub%20-%20nvm-sh%2Fnvm,Actions](https://github.com/nvm-sh/nvm#:~:text=GitHub%20-%20nvm-sh%2Fnvm,Actions)

curl -o- [https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh](https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh) | bash

source ~/ .bashrc

node --version

nvm install version name

nvm list

check node version

node --version

this will change system nvm version and the node version associated with it

nvm use version name


if node js not working right


- **Creating a Symbolic Link for Node.js:**  
- If the binary is named `nodejs` instead of `node`, you can prevent issues by creating a symbolic link using the following command:  
```bash  
sudo ln -s /usr/bin/nodejs /usr/bin/node  
```