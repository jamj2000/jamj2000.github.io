Pasos a seguir para instalar Clonezilla en el disco duro
========================================================


1. Iniciar USB de Clonezilla Live. Tiene 2 particiones:
    - sdb1 (MULTIBOOT)
    - sdb2 (DATA)

2. Montar partición que va a contener Clonezilla.

    - sudo su
    - mount  /dev/sda4  /mnt
    
3. Copiar archivos de Clonezilla

    - cp -r /lib/live/mount/medium/*  /mnt

4. Cambiar nombre /mnt/live a /mnt/live-hd

    - mv  /mnt/live  /mnt/live-hd
 
5. Montar sdb2, la cual tiene los archivos de configuración

    - mount /dev/sdb2 /media
    
6. Copiar archivos /media/grub.cfg y /media/background.png a /mnt/EFI/boot
  
    - cd  /mnt/EFI/boot
    - cp  /media/grub.cfg .
    - cp  /media/background.png .

7. Instalar grub2  

    - grub-install --root-directory=/mnt  /dev/sda 


## Información consultada

- http://joaalsai.com/index.php/2017/11/17/creacion-de-un-menu-de-restauracion/

