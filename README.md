# <h1 align='center'>Arch Linux com o I3-GAPS</h1>
<br>
<br>
<p><b>"Observação: Todos os pacotes e configurações aqui postados, são necessários para executar a instalação, feita por mim, do I3-GAPS."</b>
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
systemctl status dhcpcd<br><br></p>