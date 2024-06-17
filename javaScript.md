# JavaScript Notes
---
## Development Environment
- Prettier fpr VS Code
- Node JS for the server
- React Framework
---
## Node
### Install
```bash
# Pull the latest LTS version
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
# Install the tools
sudo apt install -y nodejs 
# npm might install auto matically with nodejs
# sudo apt install -y npm
```
Or
```bash
sudo apt install -y nodejs
npm i -g n
n install lts
# To re install dependencies in a project
npm i
```
### NPM versus NPX
`npm` is the node package manager.\
`npx` allows you execute package manager commands without nessarily having installed the package.

---
## React

### Automatically create a bare React App
```bash
npx create-react-app my-app
cd my-app
npm start
```
|Discription|File|Calls|
|-------     |------|------ |
|Root JS File| `my-app/src/index.js`|`my-app/src/App.js`|

### Manually create a bare React Back End Server
[Anthony's Plain React Backend](https://github.com/anconet/nodeJsManualBackEnd)
- Uses Express to listen and respond.
---

## NextJs
The new React recommended framework.
- Frontend
- Backend with built in routes.
- Server Side Rendering

### Automatically Create a bare Next JS Framework App and API
- Use the Framework to create the initial project.
- [nextjs.org Automatic Instructions](https://nextjs.org/docs/getting-started/installation#automatic-installation)
- [Anthony's Plain NextJs Automatic Repo](https://github.com/anconet/nextJsExample)

```bash
npx create-next-app
cd my-app
# Actually may not need Axios with Next.js
npm install axios
npm run dev
```
### Manually Create a bare Next JS Framework
- [nextjs.org Manual Instructions](https://nextjs.org/docs/getting-started/installation#manual-installation)
- [Anthony's Plain NextJs Manual Repo](https://github.com/anconet/nextJsManual)

---
## Misc Notes

### import() versus require()
- https://dev.to/costamatheus97/es-modules-and-commonjs-an-overview-1i4b
- ECMAScript 6 (ES6) 2015 brought in a new Module system called ES Modules.
- https://javascript.plainenglish.io/require-vs-import-in-js-82a7a47671f

#### require() and module.exports
- CommonJS was the older server side system.
- Started as backend.
- Was adopted by frontend.
- Uses require() on the receive side.
- Uses module.export = { stuff } on the transmit side.
- require() was function built into Node. Not part of a standard.

```javascript
// my-module.js
module.exports = {
  myValue: 42
};

// main.js
const myModule = require('./my-module.js');
console.log(myModule.myValue); // 42
```
#### import() and export
- ES Modules
- The new ES6 system per 2015.
- uses `export <stuff>` on the transmit side.
- Uses `import {stuff} from`
- Big add is the ability to statically analyze.
- Easier to maintain dependencies.
- Cannot import json files.

```javascript
// my-module.js
export const myValue = 42;

// main.js
import { myValue } from './my-module.js';
console.log(myValue); // 42
```
#### package.json settings for use of Node with ES Modules
- https://dev.to/bennycode/how-to-use-mjs-files-in-node-js-23ep

Add the `"type": "module` to package.json


```json
{
  "name": "my-package",
  "scripts": {
    "start": "node src/start.js"
  },
  "type": "module",
  "version": "0.0.0"
}
```
#### .mjs files
Just the standard file extention for ES6 Modules.

### Styling
Literally about twenty ways to skin the cat.

#### Native HTTP:
```Javascript
<style>
```
#### Native HTTP Inline:
```Javascript
 <someComponent style="css...">
 ```
 #### Native React:
 
 `myCSS.css`
 ```CSS
.myClassName  {
  border-radius: 50%;
}
 ```
 ```JavaScript
import "myCSS.css"

<myComponent className="myClassName">
 
 ```
#### Tailwind
