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
pacman -S alsa-utils ark compton dunst expac fakeroot feh git gvfs i3-gaps jshon notify-osd p7zip pulseaudio pulseaudio-alsa qbittorrent rofi scrot sddm terminus-font termite thunar thunar-archive-plugin thunar-media-tags-plugin thunar-volman ttf-dejavu tumbler unzip vlc xf86video-intel xfce4-panel xorg-server xorg-xinit xorg-xrandr zip
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
packer -S google-chrome mailspring neofetch polybar telegram-desktop ttf-font-awesome ttf-font-awesome-4 visual-studio-code-bin wps-office --noconfirm
```

## 8° Passo: Instalar o ZSH: ##
```sudo pacman -S zsh```  
```sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"```  
```git clone https://github.com/powerline/fonts.git```  
```cd fonts```  
```./install.sh```  

## 9° Passo: Ativar o gerenciador de login: ##
```sudo systemctl enable sddm.service```  

## 10° Passo: Reiniciar: ##
```sudo reboot```  

## 11° Passo: Recomendações: ##
[Instalação do Arch Linux (i3-gaps) - Parte 1](https://github.com/jirrezdex/sistema)  
[Instalação do Arch Linux (i3-gaps) - Parte 3](https://github.com/jirrezdex/archlinux-i3)
