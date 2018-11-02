# <h1 align='center'>Instalação do Arch Linux (i3-gaps) - Parte 2</h1>

### "Observação: Todos os pacotes e configurações aqui postados são necessários para executar a instalação do I3-GAPS." ###

## 1° Passo: Logar como root: ##
```...```  

## 2° Passo: Deixar teclado em pt_BR: ##
```loadkeys br-abnt2```  
```nano /etc/X11/xorg.conf.d/10-evdev.conf```
```
Section “InputClass”
	Identifier “evdev keyboard catchall”
	MatchIsKeyboard “on”
	MatchDevicePath “/dev/input/event*”
	Driver “evdev”
	Option “XkbLayout” “br”
	Option “XkbVariant” “abnt2"
EndSection
```

## 3° Passo: Testar e ativar conexão com a internet: ##
```ping -c3 google.com.br```  
```systemctl enable dhcpcd.service```  
```systemctl start dhcpcd```  
```systemctl status dhcpcd```  

## 4° Passo: Instalar os seguintes pacotes: ##
```
pacman -S alsa-utils ark compton expac fakeroot feh git gvfs i3-gaps jshon leafpad p7zip pulseaudio pulseaudio-alsa rofi sddm terminus-font termite thunar thunar-archive-plugin thunar-media-tags-plugin thunar-volman ttf-dejavu tumbler unzip xf86video-intel xfce4-panel xorg-server xorg-xinit xorg-xrandr zip
```

## 5° Passo: Sair do root e logar como usuário: ##
```...```

## 6° Passo: Instalar o PACKER: ##
```wget https://aur.archlinux.org/cgit/aur.git/plain/PKGBUILD?h=packer```  
```mv PKGBUILD\?h\=packer PKGBUILD```  
```makepkg```  
```sudo pacman -U packer-*.pkg.tar.xz```  

## 7° Passo: Instalar os seguintes pacotes: ##
```
packer -S google-chrome neofetch polybar telegram-desktop ttf-font-awesome ttf-font-awesome-4 visual-studio-code-bin --noconfirm
```

## 8° Passo: Instalar o ZSH: ##
```sudo pacman -S zsh```  
```sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"```  
```git clone https://github.com/powerline/fonts.git```  
```cd fonts```  
```./install.sh```  
```Agora é só editar o arquivo .zshrc no home do usuário e editar a seguinte linha -> ZSH_THEME="agnoster".```  

## 9° Passo: Ativar o gerenciador de login: ##
```sudo systemctl enable sddm.service```  

## 10° Passo: Reiniciar: ##
```sudo reboot```  

## 11° Passo: Continuação sugerida: ##
[FINALIZAR INSTALAÇÃO DO ARCH LINUX COM O I3-GAPS](https://github.com/jirrezdex/archlinux-i3)
