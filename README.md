# 01-Proyecto-Snipe-it-en-Docker---Alumno-Victor-Diaz-Viceira

-Anteproyecto (Enlace):
https://pinto-brand-343.notion.site/Anteproyecto-V-ctor-D-az-Viceira-32ab77c9c9fb808e8a31f811534ce2b0


Instalación de herramientas: <br>
-Visual Studio Code: <br>
Esta herramienta nos va a servir para scripts o archivos de configuración. <br>
Para instalarla podemos hacerlo desde la microsoft store (Windows) o desde la pagina oficial (Otros SO) mediante este enlace:
https://code.visualstudio.com/ 
<br> <br> 
Desde aqui podemos ver como es la interfaz de Visual Studio Code y como accedemos al directorio donde vamos a trabajar "tfg-snipeit" <br>
<img width="1243" height="748" alt="image" src="https://github.com/user-attachments/assets/b9b1656a-d739-40be-bbbc-46285392f083" />

<br> <br> 
-Docker Desktop:
Instalamos el instalador(.exe) de Docker desde su pagina oficial:  https://docs.docker.com/desktop/setup/install/windows-install/ 

Para que Docker Desktop funcione necesita los siguientes requisitos: <br> <br>
1ºTener W11 actualizado y desde la BIOS tener habiliado "Hyper-V"<br> <br>
2ºNecesitas instalar WSL2 y tener un subsistema de linux instalado.<br>
Los comandos en powershell serian: <br>
  Actualizar:"wsl --update" <br>
  Instalar:"wsl --install -d Ubuntu" <br>
  Versión:"wsl --list --verbose"<br> <br>
3ºHabilitar las caracteristicas mediantes comandos en powershell: <br>
  Habilitar Hyper-V: "dism.exe /online /enable-feature /featurename:Microsoft-Hyper-V-All /all /norestart" <br>
  Habilitar WSL: "dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart"<br>
  Habilitar Paltaforma de Maquina Virtual: "dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart"<br> <br> 
<img width="1270" height="720" alt="image" src="https://github.com/user-attachments/assets/ef8e04ea-528c-4917-94d5-6f3a42e0c006" />

Preparación de contenedor: <br>
-Creación de carpetas: <br>
Creamos el directorio "tfg-snipeit" que sera el directorio principal y despues las subcarpetas que son "logs", "myslq" y "snipe-it" <br>
Para crearlos se puede hacer desde la termina CMD con los comandos "cd" y "mkdir". Ejemplo: "cd C:\tfg-snipeit" "mkdir mysql" <br>
<img width="705" height="297" alt="image" src="https://github.com/user-attachments/assets/8f302f43-9e9a-4e39-9416-e51b901ca9f1" />

-Creación de archivos de configuración: <br>
Primero se crea el archivo .env , que es donde se especifican las variables de entorno, aqui podemos especificar datos que no seria apropiado que estuvieran en el codigo principal <br>
Ejemplos: Contraseñas de la base de datos y la APP_Key <br>
El codigo esta subido al repositorio con el nombre: ".env" <br>

Segundo se crea el archivo .yaml , que sirve para definir la estructura. <br>
Ejemplos: Datos de como va a ser la base de datos, la imagen y como la vamos a configurar y el entorno. <br>
El codigo esta subido al repositorio con el nombre: "Docker-compose.yml" <br>

Que es una APP_KEY ? <br>
-Por estas razones es importante que tu aplicación tenga una APP_KEY: <br>
1ºCifra los datos Sensibles, es decir protege la informacion que se almacena en ella como datos internos o contraseñas. <br>
2ºFirma las sesiones y cookies, es decir otro usuario no puedo influir en la sesion de otro usuario. <br>
3ºSeguridad general de Laravel, utiliza para generar hashes y validar ciertos datos internos <br>

Conceptos:<br>
Laravel: Es una herramienta que tiene contenido de base, como por ejemplo para no crear una pagina de web desde cero, como la de snipe-it <br>
Hashes: Esto sirve para convertir un dato en una cadena fija de caracteres. Ej: hola123  →  3d91b585 <br>

Como sacamos la APP_KEY? <br>
Pues necesitamos tener nuestro docker-desktop abierto y preparado y ejecutar el siguiente comando: "docker run --rm snipe/snipe-it php artisan key:generate --show" y nos mostrara esta imagen: <br>
<img width="1113" height="626" alt="image" src="https://github.com/user-attachments/assets/67309330-dcf2-42ab-b16a-c36528bd8391" /> <br>
Guardamos la APP_KEY y la ponemos en el archivo de ".env" en su correspondiente variable. <br> 
<img width="771" height="106" alt="image" src="https://github.com/user-attachments/assets/47c440dd-3d56-4076-8566-7573d63e608d" /> <br> 

-Inicio de contenedor: <br>
Vamos a nuestra terminal, en mi caso estoy utilizando powershell y ejecutamos el comando "docker compose up -d" , que esto levanta los contenedores en ese directorio, es importante ejecutarlo en el directorio donde tenemos los archivos de configuración. <br>
Al ejecutar se hace lo que hemos especificado en el archivo .yml , por lo que se descarga la imagen de mysql y de snipet de la url que especificamos en el archivo. <br>
<img width="1097" height="187" alt="image" src="https://github.com/user-attachments/assets/0912caf1-c1b5-4932-a89b-20938ae33bcb" /> <br>

Nos conectamos de manera local para terminar de configurar snipe-it, desde un navegado nos conectamos a "http://localhost:8000/" y empezamos con la creación de la base de datos. <br> 
<img width="1899" height="1027" alt="image" src="https://github.com/user-attachments/assets/b6373507-34e5-4e53-b96e-52e547cb7f05" /> <br>

Especificamos que queremos crear la base de datos y continuar para crear el Usuario Admin <br>
<img width="930" height="519" alt="image" src="https://github.com/user-attachments/assets/14fc4f20-4bc1-4624-8b32-f8826bcc03e9" /> <br>

Ahora especificamos la configuracón de nuestro admin user y apartados de snipe-it como el idioma o la divisia. <br>
<img width="918" height="858" alt="image" src="https://github.com/user-attachments/assets/32ce1e0c-5168-4b51-97c9-4f02d2c5d495" /> <br>

Una vez creado ya tendriamos la primera versión de snipe-it, ahora tendriamos que añadir inventario y adaptarlo a la empresa para comprobar sus capacidades. <br>
<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/d6fd03c0-4d4e-418e-afe3-b71d56a8e8e3" /> <br>


Bibliografia: <br>
1ºInstalación Docker: https://youtu.be/kE90WHPqo90?si=Ca3yudmmeTyfWnz5 <br>
2ºUso de docker: https://youtu.be/4Dko5W96WHg?si=e30LKoT5etecQzD6 <br>
3ºUso de snipe-it: https://youtube.com/playlist?list=PLDYUG5PASucnu5yTjQv03KYJ9Pfy3Crsk&si=iykbvKjJ-J97FDDw <br>


