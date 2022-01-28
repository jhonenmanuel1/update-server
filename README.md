# Scraping e-Boleta
## Scripts
```npm install``` : ejecutar para instalar las dependencias del proyecto.

```npm start``` : ejecutar para iniciar el proyecto en modo producción.

```npm run dev``` : ejecutar para iniciar el proyecto en modo desarrollo.

- En el modo producción, los cambios realizados en el código, solo surtiran efecto luego de la cancelación y reinicio del proyecto.

- En el modo desarrollo, los cambios realizados en el código provocan un reinicio automatico del proyecto, evitando la cancelación del mismo.

```npm install -g pkg``` : ejecutar para instalar módulo de creación **.exe**.

```pkg .``` : ejecutar dentro del directorio del proyecto para la construción de un ejecutable **.exe**.

## Chromium
Para que el ejecutable **.exe** funcione correctamente, requiere del navegador **Chromium**, este se encuentra dentro de la carpeta *node_modules*, especificamente en la carpeta del paquete *puppeteer*.

Pasos a seguir para habilitar el navegador **Chromium** en la ejecución del **.exe** :

- Abir CMD , git bash, o terminal.
- Ubicarse dentro del directorio del proyecto.
  ```
  cd scraping-eboleta
  ```

- Crear una carpeta con el nombre *chromium* en la raiz de su proyecto.
  ```
  mkdir chromium
  ```
- Copiar desde el directorio *puppeteer* a una nueva carpeta.

  **¡Importante!** Antes de ejecutar este comando, debe cambiar las x de win64 por su verdadero valor, este lo puede ver navegando hasta dicho directorio dentro de node_modules\puppeteer\\.local-chromium\win64-xxxxx
  ```  
  xcopy node_modules\puppeteer\.local-chromium\win64-xxxxx\ chromium /E /H /I
  ```
- Generar ejecutable.
  ```
  pkg . --public --targets node14-win-x64 --out-path dist
  ```