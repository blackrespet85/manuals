# **COMO CAMBIAR EL FONDO DE GRUB**

Mucha gente se pregunta como se puede cambiar ese aburrido fondo al gestor de arranque *GRUB*.

La Respuesta es sencilla y a su vez complicada. Necesitaremos unos requesisitos descritos a continuación.

---

## REQUISITOS PARA PROCESO

- [X] Imagen formato ```.png``` y de ligero tamaño (Preferible <1GB). 
- [X] Acesso a comando ```sudo``` o en su defecto a ```root```.
- [X] Acceso a ```nano``` o cualquier procesador de texto.

---

## NOTACIONES IMPORTANTES

GRUB NO admite imagenes renombradas al formato deseado.
En su defecto se debera utilizar un convertidor de formatos.

Tambien ser recomienda un nombre Sencillo para la imagen.

---

#### Una vez Visto los requisitos se procede a la edicion de _GRUB_

---
---

## PRIMER PASO - INSTALAR IMAGEN A ```/boot/grub/```

En este paso lo primero que hacemos es una copia de la imagen a instalar.

Nuestro metido será meniante ```cp``` pero puedes hacerlo por interfaz gráfica si lo deseas.

```bash
sudo cp /home/$USER/ruta_imagen.png /boot/grub
```
---
---

## SEGUNDO PASO - Editar ```/etc/default/grub```

En este paso lo primero que hacemos es abrir la ruta ```/etc/default/grub``` con nuestro editor de confianza, en mi caso ```nano```.


```bash
sudo nano /etc/default/grub
```

Se nos abrirá el menú de configuracion de _GRUB_ por defecto.

Aqui debemos añadir la siguiente linea de texto en una fila en blanco:

```bash
GRUB_BACKGROUND="/boot/grub/imagen.png"
```

Y seguido guardar con ```Ctrl+S``` o directamente saliendo con ```Ctrl+X``` y dandole a ```Y```.

---
---

## TERCER PASO - ACTUALIZAR GRUB

Nuestros cambios estan listos, pero no se haran visibles si no actualizamos _GRUB_, para ello empleamos el siguiente comando de terminal.

```bash
sudo update-grub
```
Con esto, nuestro _GRUB_ deberia contar con nuestra imagen como fondo.

---
---

## CUARTO PASO - REBOOT

Para comprobar la correcta instalacion hacemos un ```reboot```.


#### En el futuro se crearà un script para automatizar este proceso