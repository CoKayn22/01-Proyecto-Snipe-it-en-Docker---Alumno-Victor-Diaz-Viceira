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


-Bibliografia: <br>
1ºInstalación Docker: https://youtu.be/kE90WHPqo90?si=Ca3yudmmeTyfWnz5 <br>
2ºUso de docker: https://youtu.be/4Dko5W96WHg?si=e30LKoT5etecQzD6 <br>
3ºUso de snipe-it: https://youtube.com/playlist?list=PLDYUG5PASucnu5yTjQv03KYJ9Pfy3Crsk&si=iykbvKjJ-J97FDDw <br>
