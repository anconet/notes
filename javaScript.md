# JavaScript Notes
---
## Development Environment
- Prettier fpr VS Code
- Node JS for the server
- React Framework
---
## Install Node
```bash
# Pull the latest LTS version
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
# Install the tools
sudo apt install -y nodejs 
sudo apt install -y npm
```
### NPM versus NPX
`npm` is the node package manager.\
`npx` allows you execute package manager commands without nessarily having installed the package.

---
### Create a bare React App
```bash
npx create-react-app my-app
cd my-app
npm start
```
|Discription|File|Calls|
|-------     |------|------ |
|Root JS File| `my-app/src/index.js`|`my-app/src/App.js`|

---
### Create a bare Next JS Framework App
Use the Framework to create the initial project
```bash
npx create-next-app
cd my-app
# Actually may not need Axios with Next.js
npm install axios
npm run dev
```

