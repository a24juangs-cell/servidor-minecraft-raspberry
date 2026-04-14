# servidor-minecraft-raspberry
Manual del usuario. Proyecto Servidor Minecraft

# 🖥️ Servidor de Minecraft en Raspberry Pi

Este proyecto consiste en un servidor de Minecraft configurado en una Raspberry Pi, diseñado para que cualquier usuario pueda utilizarlo sin necesidad de conocimientos técnicos.

---

##  Manual de usuario


### 1. Contenido del producto

Al adquirir el servidor, se incluye:

- Raspberry Pi configurada como servidor de Minecraft  
- Tarjeta microSD con el sistema instalado  
- Fuente de alimentación  
- Guía básica de uso  

El servidor ya viene listo para funcionar, por lo que no es necesario instalar nada adicional.

---

### 2. Puesta en marcha

Para comenzar a utilizar el servidor:

1. Conectar la Raspberry Pi a la corriente  
2. Conectarla al router mediante cable Ethernet  
3. Esperar aproximadamente 60 segundos  

El servidor se iniciará automáticamente.

---

### 3. Cómo conectarse al servidor
1. Abrir Minecraft  
2. Acceder a “Multijugador”  
3. Seleccionar “Añadir servidor”  
4. Introducir la dirección IP  
5. Conectarse
   
#### Paso 1: Obtener la dirección IP

La dirección IP se puede consultar:

- En la etiqueta del dispositivo  
- Desde la configuración del router
  Pasos:
Abrir el navegador web
Acceder al router escribiendo en la barra de direcciones:
192.168.1.1
Iniciar sesión con el usuario y contraseña del router
(suelen estar en una pegatina del propio router)
Buscar una sección como:
“Dispositivos conectados”
“Clientes DHCP”
“Lista de dispositivos”
Localizar la Raspberry Pi en la lista
(suele aparecer como “raspberrypi” o similar)
Anotar la dirección IP asignada
(ejemplo: 192.168.1.123)


## Acceso desde fuera de la red (conexión remota)

Para conectarse al servidor desde fuera de la red local, es necesario configurar el router.

1. Acceder al router (normalmente 192.168.1.1 en el navegador)
2. Buscar la opción de “Port Forwarding” o “Redirección de puertos”
3. Añadir una nueva regla:
   - Puerto: 25565
   - IP: dirección IP local de la Raspberry Pi
   - Protocolo: TCP
4. Guardar los cambios

Una vez hecho esto, los jugadores podrán conectarse utilizando la IP pública de la red.
 

🔐 Acceso remoto alternativo con Tailscale

En caso de no poder configurar el router o abrir puertos, se puede utilizar Tailscale como alternativa para acceder al servidor de forma remota.

Tailscale permite conectar dispositivos como si estuvieran en la misma red local, sin necesidad de abrir puertos.

Instalación en la Raspberry Pi
Abrir una terminal en la Raspberry Pi
Ejecutar el siguiente comando:

curl -fsSL https://tailscale.com/install.sh | sh

3. Iniciar Tailscale:
   sudo tailscale up

4. Se mostrará un enlace. Ábrelo en el navegador e inicia sesión con tu cuenta (Google, GitHub, etc.)


📱 Acceso desde dispositivos con Tailscale

Además de instalar Tailscale en la Raspberry Pi, es necesario instalarlo en el dispositivo desde el que te vas a conectar (ordenador o móvil).

Instalación en ordenador
Ir a la página oficial:
👉 https://tailscale.com/download
Descargar la versión correspondiente (Windows, macOS o Linux)
Instalar el programa
Iniciar sesión con la misma cuenta utilizada en la Raspberry Pi
Instalación en móvil
Abrir la tienda de aplicaciones:
Android → Google Play
iPhone → App Store
Buscar: Tailscale
Instalar la aplicación
Iniciar sesión con la misma cuenta

- Cómo conectarse al servidor

Una vez que Tailscale esté activo en todos los dispositivos:

Abrir la aplicación de Tailscale
Ver la lista de dispositivos conectados
Localizar la Raspberry Pi
Copiar su dirección IP (formato 100.x.x.x)
Uso en Minecraft
Abrir Minecraft
Ir a “Multijugador”
Añadir servidor
Introducir la IP de Tailscale de la Raspberry Pi
Conectarse

Con Tailscale, el servidor funciona como si estuviera en la misma red, aunque estés en otra ubicación, sin necesidad de configurar el router.

---

### 4. Uso del servidor

Una vez conectado, el usuario puede:

- Crear mundos y jugar con otros jugadores  
- Construir y explorar  
- Invitar a otros usuarios  

El funcionamiento es el mismo que cualquier servidor de Minecraft.

---

### 5. Recomendaciones de uso

Para un funcionamiento óptimo:

- No superar los 8-10 jugadores simultáneos  
- No instalar modificaciones sin conocimientos previos  
- Apagar el dispositivo cuando no se utilice  

---

### 6. Apagado del servidor

Para evitar errores, no se debe desconectar directamente.

Se recomienda:

- Acceder al sistema

Para evitar errores, no se debe desconectar directamente el dispositivo.

Para apagar el servidor correctamente:

1. Acceder al sistema desde un ordenador:
   - Usar SSH (por ejemplo con el programa PuTTY en Windows)
   - Introducir la IP de la Raspberry Pi

2. Una vez dentro, ejecutar:
   stop

3. Después apagar el sistema con:
   sudo shutdown now

En caso de no poder acceder, se puede desconectar, aunque no es lo recomendable.
 
- Apagar la Raspberry Pi (En el último caso)

---

### 7. Problemas comunes

**No se puede conectar:**

- Verificar que la Raspberry Pi está encendida  
- Comprobar la dirección IP  
- Revisar la conexión a internet  

**El servidor funciona lento:**

- Reducir el número de jugadores  
- Reiniciar el sistema  

---

### 8. Mantenimiento

Para mantener el servidor en buen estado:

- Reiniciar el sistema periódicamente  
- Evitar apagados bruscos  
- Mantener el dispositivo bien ventilado  

---

### 9. Soporte

En caso de problemas técnicos, se recomienda contactar con el proveedor del servidor.

---
10. ## 🖼️ Ejemplos visuales

![Añadir servidor en Minecraft](images/agregarservidor.png)

![Configuración del router](images/raspberrypuertosytodo.png)


##  Autor

Juan Gerardo González Santos

---

##  Nota

Este servidor está pensado para grupos pequeños de jugadores, debido a las limitaciones de la Raspberry Pi.
