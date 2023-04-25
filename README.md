# Electron React JS App
## Criação de app utilizando as tecnologias Electron JS e React JS

Foi utilizado o tutorial de Sam Decrock <br>
[Building Electron.js apps with React.js (2023 update)](https://samdecrock.medium.com/building-electron-js-apps-with-react-js-2022-4d14fb2924ac) 

O único detalhe é que depois de digitar os comandos `npm install --save-dev @electron-forge/cli
npx electron-forge import`, adicione no `forge.config` o seguinte:

```
hooks: {
    packageAfterCopy: async (config, buildPath, electronVersion, platform, arch) => {
      var src = path.join(__dirname, '../react-app/build/');
      var dst = buildPath;
      fs.cpSync(src, dst, {recursive: true});
    }
  }


```
e importe: 
```
const path = require('path');
const fs = require('fs');
```

