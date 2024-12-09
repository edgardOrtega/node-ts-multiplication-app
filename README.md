# los pasos que se usaron para iniciar el proyecto Node-TS

se realizaron dependencias:

1. instalacion de types/node, como dependencias de desarrollo

`
npm i -D typescript @types/node
`

2. Inicializar el archivo de configuración de TypeScript 

`
npx tsc --init --outDir dist/ --rootDir src
`


3. se realiza instalacion de nodemon 

 `
 npm install -D ts-node nodemon
 `

luego se crea un archivo denominado nodemon.json que dentro tendra el siguiente scripts:

```
{
    "watch": ["src"],
    "ext": ".ts,.js",
    "ignore": [],
    "exec": "npx ts-node ./src/app.ts"
} 
  ```

4. en el package.json agregar los scripts para que corran en desarrollo

```
  "dev": "nodemon"
  "dev": "npx nodemon" // En caso de no querer instalar nodemon
```
5. se instalo  rimraf para eliminacion de directorio

`npm install -D rimraf`

6. Crear scripts en el package.json para construir e iniciar en producción

```
 "build": "rimraf ./dist && tsc",
 "start": "npm run build && node dist/app.js"
```

el proyecto se instalaron dependencias de npm para separar el codigo de terceros de nuestro codigo realizando un archivo de plugins para utilizar en nuestro codigo

-se instalo yargs para manejo de argumento por terminal de comandos