# <h1 align='center'>Arch Linux com o I3-GAPS</h1>
<br>
<br>
<p><b>"Observação: Todos os pacotes e configurações aqui postados são necessários para executar a instalação do I3-GAPS."</b>
<br>
<br>
<b>1° Passo: Logar com o root.</b><br><br>
<b>2° Passo: Deixar teclado em pt_BR.</b><br>
loadkeys br-abnt2<br>
nano /etc/X11/xorg.conf.d/10-evdev.conf<br><br>
Section “InputClass”<br>
&nbsp;&nbsp;&nbsp;&nbsp;Identifier “evdev keyboard catchall”<br>
&nbsp;&nbsp;&nbsp;&nbsp;MatchIsKeyboard “on”<br>
&nbsp;&nbsp;&nbsp;&nbsp;MatchDevicePath “/dev/input/event*”<br>
&nbsp;&nbsp;&nbsp;&nbsp;Driver “evdev”<br>
&nbsp;&nbsp;&nbsp;&nbsp;Option “XkbLayout” “br”<br>
&nbsp;&nbsp;&nbsp;&nbsp;Option “XkbVariant” “abnt2"<br>
EndSection<br><br>
<b>3° Passo: Testar conexão com a internet e ativar.</b><br>
ping -c3 google.com.br<br>
systemctl enable dhcpcd.service<br>
systemctl start dhcpcd<br>
systemctl status dhcpcd<br><br>
<b>4° Passo: Instalar os seguintes pacotes.</b><br>
pacman -S alsa-utils ark compton expac fakeroot feh git gvfs i3-gaps jshon leafpad p7zip pulseaudio pulseaudio-alsa rofi sddm terminus-font termite thunar thunar-archive-plugin thunar-media-tags-plugin thunar-volman ttf-dejavu tumbler unzip xf86video-intel xfce4-panel xorg-server xorg-xinit xorg-xrandr zip<br><br>
<b>5° Passo: Sair do root e logar com o usuário.</b><br><br>
<b>6° Passo: Instalar o PACKER.</b><br>
wget https://aur.archlinux.org/cgit/aur.git/plain/PKGBUILD?h=packer<br>
mv PKGBUILD\?h\=packer PKGBUILD<br>
makepkg<br>
sudo pacman -U packer-*.pkg.tar.xz<br><br>
<b>7° Passo: Instalar os seguintes pacotes.</b><br>
packer -S google-chrome neofetch polybar telegram-desktop ttf-font-awesome ttf-font-awesome-4 visual-studio-code-bin --noconfirm<br><br>
<b>8° Passo: Instalar o ZSH.</b><br>
sudo pacman -S zsh<br>
sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"<br>
git clone https://github.com/powerline/fonts.git<br>
cd fonts<br>
./install.sh<br>
Agora é só editar o arquivo .zshrc no home do usuário e editar a seguinte linha -> ZSH_THEME="agnoster".<br><br>
<b>9° Passo: Ativar o gerenciador de login.</b><br>
sudo systemctl enable sddm.service<br><br>
<b>10° Passo: Reiniciar.</b><br>
sudo reboot<br><br>
<b>11° Passo: Continuação sugerida.</b><br>
<a href='https://github.com/jirrezdex/archlinux-i3'>FINALIZAR INSTALAÇÃO DO ARCH LINUX COM O I3-GAPS</a></p>