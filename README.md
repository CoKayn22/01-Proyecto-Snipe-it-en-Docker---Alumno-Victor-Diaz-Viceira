# 01-Proyecto-Snipe-it-en-Docker---Alumno-Victor-Diaz-Viceira

-Anteproyecto (Enlace):
https://pinto-brand-343.notion.site/Anteproyecto-V-ctor-D-az-Viceira-32ab77c9c9fb808e8a31f811534ce2b0


Instalación de herramientas:
-Docker Desktop:
Instalamos el instalador(.exe) de Docker desde su pagina oficial https://docs.docker.com/desktop/setup/install/windows-install/ 

Para que Docker Desktop funcione necesita los siguientes requisitos:<br>
1ºTener W11 actualizado y desde la BIOS tener habiliado "Hyper-V"<br>
2ºNecesitas instalar WSL2 y tener un subsistema de linux instalado.<br>
Los comandos en powershell serian <br>
  Actualizar:"wsl --update"<br>  
  Instalar:"wsl --install -d Ubuntu" <br>
  Versión:"wsl --list --verbose"<br>
3ºHabilitar las caracteristicas mediantes comandos en powershell <br>
  Habilitar Hyper-V: "dism.exe /online /enable-feature /featurename:Microsoft-Hyper-V-All /all /norestart" <br>
  Habilitar WSL: "dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart"<br>
  Habilitar Paltaforma de Maquina Virtual: "dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart"<br>
<img width="1270" height="720" alt="image" src="https://github.com/user-attachments/assets/ef8e04ea-528c-4917-94d5-6f3a42e0c006" />

