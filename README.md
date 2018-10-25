Recientemente StarUML se actualizó de 2.0 a 3.0. El método de crack original, la forma de modificar la función de verificación de licencia 
no se puede usar. La ubicación de instalación ha cambiado y se ha encontrado el archivo LicenseManagerDomain.js. 
¿Qué debería hacer? El viejo conductor les dijo a todos que resolvieran el problema.

StarUML está escrito en nodejs. Específicamente, está escrito en el marco frontal de Electron. 
Todo el código fuente de starUML en la nueva versión viene empaquetado por la herramienta asar. 

# Ingresar al directorio (Windows)

C:\Program Files\StarUML\resources

# Instalar la herramienta asar

```bash
npm install -g asar
```

# Desempaquetar StarUML

```bash
asar extract app.asar app
```
# Editar el archivo de licencia

```bash
app\src\engine\license-manager.js
```

### Modificar el código
Linea 125

```js
  checkLicenseValidity () {
    this.validate().then(() => {
      setStatus(this, true)
    }, () => {
    //===> Cambiar false por true
      setStatus(this, true)
      //===> Comentar Dialog
      // UnregisteredDialog.showDialog()
    })
  }
```

# Volver a empaquetar StarUML

```bash
  asar pack app app.asar
 ```
 
 # Ejecutar StarUML
 
 Fuente: https://blog.csdn.net/sam_shan/article/details/80585240
  
