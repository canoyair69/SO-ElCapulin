Okay, I will replace the "Índice (Syllabus)" and the subsequent sections, adapting them to the "El Capulin Linux" theme and the tools you've specified for a Linux environment.

Here's the updated document:

-----

# **Guía de Instalación Rápida de Herramientas Esenciales para El Capulín Linux**

\<p align="center"\>
Esta guía proporciona comandos eficientes para instalar software clave en tu sistema Linux, centrándose en las herramientas necesarias para un entorno de desarrollo robusto y uso general.
\</p\>

-----

## **Índice (Syllabus)**

1.  **Gestores de Paquetes**
      * Nix Package Manager
      * Homebrew (Linuxbrew)
2.  **Navegadores Web**
      * Brave Browser
3.  **Paquetes Base y Requeridos para Linux**
4.  **Herramientas y Utilidades**
      * PeaZip
      * Herramientas de Booteo USB (Multibootusb, Ventoy)
5.  **Entorno de Desarrollo (Dev)**
      * Visual Studio Code
      * Git
      * Python (con Pip y NVM)
      * Node.js (con NPM y NVM)
      * Grub Customizer
6.  **Configuración de Terminal y Shell**
      * Kitty Terminal
      * Zsh (con Powerlevel10k, Autosuggestions, Autocomplete)
      * Tmux
      * Neofetch
7.  **Comandos de Instalación**

-----

## **Gestores de Paquetes**

Aprovecharemos gestores de paquetes modernos para una instalación y gestión eficiente del software.

### **Nix Package Manager**

**Descripción:** Nix es un gestor de paquetes puramente funcional y un sistema de construcción. Permite instalaciones reproducibles y declarativas, evitando conflictos de dependencias.

**Comando para Terminal Linux:**

```bash
# Para instalación multi-usuario (recomendado)
curl -L https://nixos.org/nix/install(https://nixos.org/nix/install) | sh

# Para instalación de un solo usuario
# curl -L https://nixos.org/nix/install(https://nixos.org/nix/install) | sh -s -- --no-daemon
# Después de la instalación, sigue las instrucciones en pantalla para configurar tu shell.
````


### **Homebrew (Linuxbrew)**

**Descripción:** El popular gestor de paquetes de macOS, adaptado para Linux. Ofrece una gran cantidad de software no disponible en los repositorios de tu distribución.

**Comando para Terminal Linux:**

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh(https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
# Sigue las instrucciones post-instalación para añadir Homebrew al PATH.
# Por ejemplo, para Bash: echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.bashrc
# Para Zsh: echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.zshrc
# source ~/.bashrc o source ~/.zshrc para aplicar los cambios.
````


---

## **Navegadores Web**

### **Brave Browser**

**Descripción:** Un navegador web rápido, privado y seguro, con un bloqueador de anuncios y protección de seguimiento incorporados.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu):**

```bash
sudo apt install curl

sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg(https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg)

echo "deb signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/(https://brave-browser-apt-release.s3.brave.com/) stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list

sudo apt update

sudo apt install brave-browser


````
**Comando para Terminal Linux (usando Homebrew):**

```bash
brew install --cask brave-browser
````



---

## **Paquetes Base y Requeridos para Linux**

**Descripción:** Estos comandos instalan paquetes esenciales y bibliotecas de desarrollo que son fundamentales para muchas de las herramientas listadas a continuación.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu):**

```bash
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y curl git unzip xz-utils zip libglu1-mesa
sudo apt-get install -y clang cmake git ninja-build pkg-config libgtk-3-dev liblzma-dev libstdc++-12-dev
````

````

---

## **Herramientas y Utilidades**

### **PeaZip**

**Descripción:** Un archivador y gestor de archivos multiplataforma de código abierto que soporta más de 200 formatos de archivo.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu - descarga de .deb):**

```bash
# Descarga la última versión .deb desde el sitio oficial de PeaZip o GitHub
# Por ejemplo, para la versión de 64 bits:
wget https://github.com/peazip/PeaZip/releases/download/9.8.0/peazip_9.8.0.LINUX.GTK2.deb(https://github.com/peazip/PeaZip/releases/download/9.8.0/peazip_9.8.0.LINUX.GTK2.deb)
sudo dpkg -i peazip_9.8.0.LINUX.GTK2.deb
sudo apt install -f # Para resolver dependencias si es necesario
# Reemplaza '9.8.0' con la versión más reciente si es diferente.

````
**Comando para Terminal Linux (usando Homebrew):**

```bash
brew install --cask peazip
````



### **Herramientas de Booteo USB**

**Descripción:** Utilidades para crear unidades USB booteables, esenciales para instalar sistemas operativos o ejecutar herramientas de recuperación.

#### **Multibootusb**

**Descripción:** Permite instalar múltiples sistemas operativos Live en una sola unidad USB sin formatear.

**Comando para Terminal Linux (Requiere Python 3 y PyQt5 - instalación de dependencias y luego instalación manual o desde PPA si disponible):**

```bash
# Generalmente no está en repositorios estándar, requiere instalación manual o PPA
# Por ejemplo, para Ubuntu/Debian (requiere PPA o descarga):
# sudo add-apt-repository ppa:usb-creator-team/ppa # Si existe un PPA de Multibootusb
# sudo apt update
# sudo apt install multibootusb
# Si no hay PPA, descarga el .deb o fuente y sigue las instrucciones de instalación.
echo "Multibootusb a menudo requiere una instalación manual o PPA. Busca la última información para tu distribución."


````

#### **Ventoy**

**Descripción:** Una solución de código abierto para crear USB booteable para archivos ISO/WIM/IMG/VHD(x)/EFI. Simplemente copia los archivos, ¡sin necesidad de extracción!

**Comando para Terminal Linux (Descarga el paquete y ejecuta el script):**

```bash
# Descargar la última versión de Ventoy desde GitHub
# Consulta [https://github.com/ventoy/Ventoy/releases](https://github.com/ventoy/Ventoy/releases) para la última versión
VENTOY_VERSION="1.0.98" # Reemplaza con la versión más reciente
wget [https://github.com/ventoy/Ventoy/releases/download/v$](https://github.com/ventoy/Ventoy/releases/download/v$){VENTOY_VERSION}/ventoy-${VENTOY_VERSION}-linux.tar.gz
tar -xf ventoy-${VENTOY_VERSION}-linux.tar.gz
cd ventoy-${VENTOY_VERSION}
# Asegúrate de identificar correctamente tu dispositivo USB antes de ejecutar.
# Ejecutar el script para instalar Ventoy en el USB (ej. /dev/sdX)
# sudo sh ventoy2disk.sh -i /dev/sdX # ¡Reemplaza /dev/sdX con tu unidad USB!
echo "Para instalar Ventoy en un USB, navega al directorio descargado y ejecuta 'sudo sh ventoy2disk.sh -i /dev/sdX' (¡cuidado con /dev/sdX!)"


````

---

## **Entorno de Desarrollo (Dev)**

### **Visual Studio Code**

**Descripción:** Un editor de código fuente ligero pero potente, gratuito y de código abierto desarrollado por Microsoft.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu):**

```bash
sudo apt-get install wget apt-transport-https
wget -qO- [https://packages.microsoft.com/keys/microsoft.asc](https://packages.microsoft.com/keys/microsoft.asc) | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] [https://packages.microsoft.com/repos/code](https://packages.microsoft.com/repos/code) stable main" | sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null
rm -f packages.microsoft.gpg
sudo apt update
sudo apt install code
````


**Comando para Terminal Linux (usando Homebrew):**

```bash
brew install --cask visual-studio-code


````

### **Git**

**Descripción:** Un sistema de control de versiones distribuido, esencial para el desarrollo de software.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu):**

```bash
sudo apt-get install git -y


````
**Comando para Terminal Linux (usando Homebrew):**

```bash
brew install git
````



### **Python (con Pip y NVM)**

**Descripción:** Un lenguaje de programación de propósito general. `pip` es su gestor de paquetes, y `nvm` (Node Version Manager) se confunde a menudo con `pyenv` para Python. Incluiremos la instalación básica de Python y pip. Para gestionar múltiples versiones de Python, se recomienda `pyenv`.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu):**

```bash
sudo apt-get install python3 python3-pip -y
# Para pyenv (gestor de versiones de Python)
curl [https://pyenv.run](https://pyenv.run) | bash
# Sigue las instrucciones de pyenv para añadirlo a tu shell.
````


**Comando para Terminal Linux (usando Homebrew):**
```bash
brew install python@3.10 # O la versión deseada
brew install pyenv
````



### **Node.js (con NPM y NVM)**

**Descripción:** Node.js es un entorno de ejecución de JavaScript. `npm` es su gestor de paquetes. `nvm` (Node Version Manager) permite gestionar múltiples versiones de Node.js.

**Comando para Terminal Linux (Instalar NVM primero, luego Node.js/NPM con NVM):**

```bash
# Instalar NVM (Node Version Manager)
curl -o- [https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh](https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh) | bash
# Después de instalar NVM, cierra y vuelve a abrir tu terminal o haz 'source ~/.bashrc'/'source ~/.zshrc'
# Luego, instala la versión LTS de Node.js (que incluye NPM)
# nvm install --lts
# nvm use --lts
````



### **Grub Customizer**

**Descripción:** Una herramienta gráfica para configurar y personalizar el menú de arranque GRUB2.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu - PPA):**

```bash
sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y
sudo apt-get update
sudo apt-get install grub-customizer -y
````


---

## **Configuración de Terminal y Shell**

### **Kitty Terminal**

**Descripción:** Un emulador de terminal rápido y rico en funciones, acelerado por GPU.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu):**

```bash
sudo apt-get install kitty -y
````

````
**Comando para Terminal Linux (usando Homebrew):**

```bash
brew install --cask kitty
````



### **Zsh (con Powerlevel10k, Autosuggestions, Autocomplete)**

**Descripción:** Zsh es un potente shell de línea de comandos. Lo configuraremos con temas y plugins para mejorar la productividad.

**Comando para Terminal Linux (Instalación de Zsh y sus complementos):**

```bash
# Instalar Zsh
sudo apt-get install zsh -y
chsh -s $(which zsh) # Cambiar shell por defecto a Zsh (requiere reiniciar sesión)

# Instalar Oh My Zsh (framework para Zsh)
sh -c "$(curl -fsSL [https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh](https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh))"

# Instalar Powerlevel10k (tema)
git clone --depth=1 [https://github.com/romkatv/powerlevel10k.git](https://github.com/romkatv/powerlevel10k.git) ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
# Luego, edita tu ~/.zshrc y establece ZSH_THEME="powerlevel10k/powerlevel10k"

# Instalar zsh-autosuggestions
git clone [https://github.com/zsh-users/zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
# Añade 'zsh-autosuggestions' a la lista de plugins en tu ~/.zshrc

# Instalar zsh-syntax-highlighting (para autocompletado y resaltado de sintaxis)
git clone [https://github.com/zsh-users/zsh-syntax-highlighting.git](https://github.com/zsh-users/zsh-syntax-highlighting.git) ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# Añade 'zsh-syntax-highlighting' a la lista de plugins en tu ~/.zshrc

# Edita ~/.zshrc para habilitar los plugins y el tema:
# plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
# ZSH_THEME="powerlevel10k/powerlevel10k"
````



### **Tmux**

**Descripción:** Un multiplexor de terminales, que te permite crear múltiples sesiones de terminal dentro de una sola ventana.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu):**

```bash
sudo apt-get install tmux -y
````

````
**Comando para Terminal Linux (usando Homebrew):**

```bash
brew install tmux
````



### **Neofetch**

**Descripción:** Una herramienta de línea de comandos que muestra información del sistema de manera concisa y atractiva, con el logo de tu distribución.

**Comando para Terminal Linux (para sistemas basados en Debian/Ubuntu):**

```bash
sudo apt-get install neofetch -y


````
**Comando para Terminal Linux (usando Homebrew):**

```bash
brew install neofetch
````



---

## **Comandos de Instalación**

**¡Importante!** Los comandos anteriores son específicos para cada herramienta. No hay un único script monolítico como el `WinScript.bat` para todas las instalaciones en Linux debido a la diversidad de métodos de instalación (apt, curl, git clone, brew) y la necesidad de interacción post-instalación para herramientas como Nix, Homebrew, NVM y Zsh.

**Para ejecutar los comandos, deberás copiarlos y pegarlos en tu terminal Linux uno por uno, o combinarlos cuidadosamente en un script de shell (`.sh`) si comprendes las dependencias y los pasos interactivos.**

**Ejemplo de cómo podrías combinarlos en un script `.sh` (solo para las instalaciones apt y algunas automáticas):**

**Archivo: `install_linux_tools.sh`**

```bash
#!/bin/bash

echo "Iniciando instalación de herramientas esenciales para El Capulín Linux..."
echo "Asegúrate de ejecutar este script con 'sudo' o de tener los permisos necesarios."

# Actualizar paquetes e instalar dependencias básicas
echo "--- Actualizando sistema e instalando dependencias base ---"
sudo apt-get update -y && sudo apt-get upgrade -y
sudo apt-get install -y curl git unzip xz-utils zip libglu1-mesa
sudo apt-get install -y clang cmake ninja-build pkg-config libgtk-3-dev liblzma-dev libstdc++-12-dev

# Instalar Zsh y Tmux
echo "--- Instalando Zsh y Tmux ---"
sudo apt-get install zsh tmux -y

# Instalar Python y Pip
echo "--- Instalando Python 3 y Pip ---"
sudo apt-get install python3 python3-pip -y

# Instalar Neofetch y Kitty
echo "--- Instalando Neofetch y Kitty Terminal ---"
sudo apt-get install neofetch kitty -y

# Instalar VS Code (usando el método recomendado para Debian/Ubuntu)
echo "--- Instalando Visual Studio Code ---"
sudo apt-get install wget apt-transport-https -y
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /etc/apt/keyrings/packages.microsoft.gpg > /dev/null
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null
sudo apt update
sudo apt install code -y

echo "--- Instalaciones de APT completadas ---"
echo "--- Pasos adicionales requieren intervención manual o scripts específicos ---"

echo "Puedes ejecutar los siguientes comandos para configurar otras herramientas:"
echo "-------------------------------------------------------------------------"
echo "### Nix Package Manager (Multi-usuario):"
echo "curl -L https://nixos.org/nix/install | sh"
echo ""
echo "### Homebrew (Linuxbrew):"
echo "/bin/bash -c \"$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)\""
echo "  (Recuerda seguir las instrucciones para añadirlo al PATH)"
echo ""
echo "### Brave Browser (APT):"
echo "  (Ver sección correspondiente para los comandos multi-línea)"
echo ""
echo "### NVM (Node Version Manager):"
echo "curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash"
echo "  (Luego, cierra/reabre terminal o source ~/.bashrc/.zshrc y usa 'nvm install --lts')"
echo ""
echo "### Oh My Zsh, Powerlevel10k, Autosuggestions, Syntax Highlighting:"
echo "  (Ver sección correspondiente para los comandos y la edición de ~/.zshrc)"
echo ""
echo "### Grub Customizer (PPA):"
echo "sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y"
echo "sudo apt update"
echo "sudo apt install grub-customizer -y"
echo ""
echo "### PeaZip (Descarga manual .deb o brew):"
echo "  (Ver sección correspondiente)"
echo ""
echo "### Ventoy (Descarga y script manual):"
echo "  (Ver sección correspondiente y ¡CUIDADO con el USB!)"
echo "-------------------------------------------------------------------------"

echo "Script completado. Algunos pasos requieren configuración manual o scripts específicos."

````


````

sudo apt update -y && sudo apt upgrade -y && \
sudo apt install -y curl git unzip xz-utils zip libglu1-mesa clang cmake ninja-build pkg-config libgtk-3-dev liblzma-dev libstdc++-12-dev zsh tmux neofetch python3 python3-pip wget apt-transport-https && \
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /etc/apt/keyrings/packages.microsoft.gpg > /dev/null && \
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null && \
sudo apt update && sudo apt install -y code && \
sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y && sudo apt update && sudo apt install -y grub-customizer && \
chsh -s $(which zsh) && \
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" "" --unattended && \
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k && \
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-autosuggestions && \
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting && \
(echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.bashrc; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.zshrc) && \
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" && \
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash && \
echo "Para Brave, Nix, PeaZip y Ventoy, consulta las secciones específicas de la guía. ¡Algunos requieren pasos manuales o precauciones!"

````

# El Capulin Linux

- pakcage manager
  nix
  homebrew


- web Browser
  Brave 

- requeried base linux
  sudo apt-get update -y && sudo apt-get upgrade -y;
sudo apt-get install -y curl git unzip xz-utils zip libglu1-mesa
sudo apt-get install \
      clang cmake git \
      ninja-build pkg-config \
      libgtk-3-dev liblzma-dev \
      libstdc++-12-dev
  
- tools utilies
  Peazip
  
- USB boot
 multibootusb 
  ventoy
  -----

## **Comando Único de Instalación para Herramientas de Desarrollo en Linux Mint**

Para instalar y configurar rápidamente **VS Code, Git, Python (con Pip), Node.js (con NPM y NVM), y Grub Customizer** en Linux Mint, puedes usar el siguiente comando unificado. Este comando agrupa la mayoría de las instalaciones basadas en `apt` y scripts `curl` para una configuración más fluida.

```bash
sudo apt update -y && sudo apt upgrade -y && \
sudo apt install -y curl git python3 python3-pip wget apt-transport-https && \
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /etc/apt/keyrings/packages.microsoft.gpg > /dev/null && \
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null && \
sudo apt update && sudo apt install -y code && \
sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y && sudo apt update && sudo apt install -y grub-customizer && \
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash && \
echo "Instalación de herramientas de desarrollo completada. Recuerda reiniciar tu terminal o ejecutar 'source ~/.bashrc'/'source ~/.zshrc' para que NVM esté disponible, y luego usa 'nvm install --lts' para instalar Node.js."
```

-----

### **Consideraciones Importantes Después de la Ejecución:**

  * **Node.js y NVM**: El comando instala **NVM (Node Version Manager)**. Para que **NVM** funcione correctamente y puedas instalar **Node.js** 
**Python y Pip**: Python 3 y Pip se instalarán por defecto. **Visual Studio Code**: Una vez instalado, puedes iniciarlo desde el menú de aplicaciones o escribiendo `code` en la terminal. **Grub Customizer**: Puedes encontrarlo en el menú de aplicaciones o ejecutarlo desde la terminal con `grub-customizer`.



## devevelopment  code 
 Para instalar y configurar rápidamente **VS Code**, **Git**, **Python (con Pip)**, **Node.js (con NPM y NVM)**, y **Grub Customizer** en Linux Mint, puedes usar el siguiente comando unificado. Este comando agrupa la mayoría de las instalaciones basadas en apt y scripts curl para una configuración más fluida.

```
sudo apt update -y && sudo apt upgrade -y && \
sudo apt install -y curl git python3 python3-pip wget apt-transport-https && \
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /etc/apt/keyrings/packages.microsoft.gpg > /dev/null && \
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null && \
sudo apt update && sudo apt install -y code && \
sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y && sudo apt update && sudo apt install -y grub-customizer && \
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash && \
echo "Instalación de herramientas de desarrollo completada. Recuerda reiniciar tu terminal o ejecutar 'source ~/.bashrc'/'source ~/.zshrc' para que NVM esté disponible, y luego usa 'nvm install --lts' para instalar Node.js."
```


  kitty 
    zsh 
    zsh-theme powerlevel10k
    zsh-autosugestion
    zsh-automplete
    tmux
    neoftech
