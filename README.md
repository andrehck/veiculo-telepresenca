# veiculo-telepresenca

Este veículo de tele presença tem como objetivo de possibilitar uma pessoa caminhar e interagir virtualmente com outro ambiente via áudio e vídeo se locomovendo no ambiente. Com o próprio navegador nativo acessamos um servidor de vídeo conferência Jitsi.

Este veículo tem que ter acesso a uma rede WiFi para chegar até o servidor de vídeo conferência e receber os comandos para se locomover no ambiente.

Materiais necessários:

1 - Display 7" 1024x600 touch
1 - Raspberry PI 4 B
1 - WebCam Logitech C920
1 - Caixa de som
1 - Conjunto de rodas Mecanum, comprado na China já com arduino e placa de controle que recebe via serial os comandos de movimentos.
1 - Bateria 12V 7Ah chumbo ácido
1 - Adaptador USB TP-Link WiFi com antena de 4dB, não foi utilizado o WiFi da própria Raspberry em função do baixo ganho de recepção.
1 - Carregador de baterias
1 - Conversor DC-DC
1 - Cartão Micro-SD 8GB Classe 10

Passos para instalação:

Utilizado um 2020-02-13-raspbian-buster

Como utilizei adaptador USB WiFi, tive que desativar a WiFi On-Board e configurar a externa:

vi /boot/config.txt

dtoverlay=pi3-disable-wifi

vi /etc/modprobe.d/raspi-blacklist.conf

#wifi
blacklist brcmfmac
blacklist brcmutil



vi interfaces
# interfaces(5) file used by ifup(8) and ifdown(8)

# Please note that this file is written to be used with dhcpcd
# For static IP, consult /etc/dhcpcd.conf and 'man dhcpcd.conf'

# Include files from /etc/network/interfaces.d:
source-directory /etc/network/interfaces.d

auto lo
iface lo inet loopback
iface eth0 inet manual
allow-hotplug wlan0
iface wlan0 inet manual
        wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf


Atualize os Raspbian

sudo apt-get update
sudo apt-get upgrade





