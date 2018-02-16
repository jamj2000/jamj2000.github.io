Pasos a seguir para instalar Clonezilla en el disco duro
========================================================


1. Iniciar CD de Clonezilla Live

2. Montar partición que va a contener Clonezilla.

    sudo su
    mount  /dev/sda4  /mnt
    
3. Copiar archivos de Clonezilla

    cp -r /lib/live/mount/medium/*  /mnt

4. Cambiar nombre /mnt/live a /mnt/live-hd

    mv  /mnt/live  /mnt/live-hd
 
5. Montar Pendrive con archivos de configuración

    mount /dev/sdb1 /media
    
6. Copiar archivo /media/clonezilla-hd/grub.cfg a /mnt/EFI/boot/grub.cfg (sobreescribir archivo anterior)
  
    cp  /media/clonezilla-hd/grub.cfg  /mnt/EFI/boot/grub.cfg

7. Instalar grub2  

    grub-install --root-directory=/mnt  /dev/sda 





## Información consultada

- http://joaalsai.com/index.php/2017/11/17/creacion-de-un-menu-de-restauracion/

