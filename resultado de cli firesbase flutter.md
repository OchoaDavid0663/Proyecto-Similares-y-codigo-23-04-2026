¡Hola! Configurar el entorno de desarrollo para **Flutter** y **Firebase** es un paso crucial. No te preocupes, el proceso con `npm` y Node.js es bastante directo en Windows.

Aquí tienes la guía paso a paso para dejar todo listo:

---

## 1. Software necesario para instalar npm y Node.js
Para instalar Node.js y su gestor de paquetes (`npm`) de forma global en Windows, solo necesitas:
* **El instalador oficial (.msi):** Descargado desde [nodejs.org](https://nodejs.org/).
* **Permisos de Administrador:** Para poder registrar las variables de entorno (PATH) y que los comandos funcionen en cualquier terminal.
* **Conexión a internet:** Para descargar los paquetes de Firebase posteriormente.

---

## 2. Procedimiento de Instalación y Verificación

### Cómo verificar si ya está instalado
Antes de instalar nada, abre una terminal (**CMD** o **PowerShell**) y escribe:
```bash
node -v
npm -v
```
* **Si aparecen números de versión** (ej. `v20.12.0` y `10.5.0`), ya lo tienes.
* **Si dice "no se reconoce como un comando"**, procede a la instalación:

### Instalación paso a paso (Si no lo tienes)
1.  **Descarga:** Ve a [nodejs.org](https://nodejs.org/) y descarga la versión **LTS** (es la más estable).
2.  **Ejecución:** Abre el archivo `.msi` descargado.
3.  **Configuración:** Sigue el asistente ("Next, Next...").
    * **IMPORTANTE:** Asegúrate de que la opción **"Add to PATH"** esté seleccionada (viene marcada por defecto). Esto es lo que permite que sea "global".
4.  **Finalizar:** Haz clic en *Install* y luego en *Finish*.
5.  **Reinicio:** Cierra y vuelve a abrir tu terminal para que reconozca los cambios.

---

## 3. Instalación de Firebase CLI (firebase-tools)
Una vez que `npm` funciona, instalaremos las herramientas de Firebase para que Flutter pueda comunicarse con la consola.

### Instalación Global
Ejecuta el siguiente comando en tu terminal:
```bash
npm install -g firebase-tools
```
> El parámetro `-g` indica que la instalación es **global**, permitiéndote usar el comando `firebase` en cualquier carpeta de tu computadora.

---

## 4. Cómo usar los comandos principales

### Cómo acceder a Firebase con tu Cuenta de Google
Para que la CLI sepa quién eres y a qué proyectos tienes acceso, debes iniciar sesión:
1.  En la terminal, escribe:
    ```bash
    firebase login
    ```
2.  Se abrirá automáticamente una ventana en tu navegador.
3.  Selecciona tu cuenta de Google y otorga los permisos necesarios.
4.  Al terminar, verás un mensaje en la terminal confirmando el éxito: *Success! Logged in as [tu-correo@gmail.com]*.

### Cómo usar firebase-tools (Comandos útiles)
* **Ver tus proyectos:** `firebase projects:list` (Muestra todos los proyectos creados en tu consola de Firebase).
* **Inicializar Firebase en tu app Flutter:**
    1.  Navega hasta la carpeta raíz de tu proyecto Flutter.
    2.  Ejecuta: `firebase init`
    3.  Usa las flechas y la barra espaciadora para elegir qué servicios quieres (Hosting, Functions, Firestore, etc.).

---

## 5. El toque final para Flutter: FlutterFire CLI
Para que Flutter reconozca automáticamente tu configuración de Firebase (generando el archivo `firebase_options.dart`), es recomendable instalar esta herramienta adicional:

1.  **Instalar FlutterFire CLI:**
    ```bash
    dart pub global activate flutterfire_cli
    ```
2.  **Configurar el proyecto:**
    ```bash
    flutterfire configure
    ```
    *Este comando te preguntará a qué proyecto de Firebase quieres conectar tu app de Flutter y configurará Android, iOS y Web por ti automáticamente.*

¿Ya tienes creado tu proyecto en la Consola de Firebase o necesitas ayuda para crearlo desde cero?
