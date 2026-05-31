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
En esta sección se describen los pasos que debes seguir para preparar tu entorno doméstico e instalar las herramientas necesarias en tu ordenador antes de proceder a iniciar el servidor o conectarte al juego.

Nota para el lector: Este documento funciona exclusivamente como un Manual de Usuario enfocado en la operación práctica. Si deseas consultar los detalles técnicos del despliegue, comandos avanzados o el proceso completo de configuración desde cero, por favor remítete a la Guía de Implementación, donde se encuentra toda la documentación técnica detallada de forma exhaustiva. [Guía de Implementación](https://servergerapi.notion.site/Gu-a-de-Implementaci-n-Servidor-Minecraft-Java-Bedrock-a6ea90fe4b4d4bb3be1cd23b60c13b5d?source=copy_link)

2.1. Conexión física del hardware
El dispositivo se entrega completamente configurado dentro de su carcasa de protección. Para encenderlo por primera vez, sigue estos pasos:

Conecta el cable de la fuente de alimentación oficial al puerto USB-C de la Raspberry Pi y enchúfalo a la toma de corriente. El dispositivo se iniciará de forma automática.

<img width="700" height="466" alt="cable-power" src="https://github.com/user-attachments/assets/21901bc0-ae7d-4bb8-a1cb-8d8d4fa3c381" />


Conecta un cable de red Ethernet desde cualquiera de los puertos LAN libres de tu router doméstico al puerto Ethernet de la Raspberry Pi. Esto garantizará la máxima estabilidad y velocidad para el servidor.
    * Para conectar tu Raspberry Pi a una red cableada, inserta un cable Ethernet en el puerto Ethernet de tu Raspberry Pi hasta que oigas un clic. Si tu modelo de       Raspberry Pi no incluye un puerto Ethernet, puedes usar un adaptador Ethernet USB. 

<img width="700" height="466" alt="ETHERNET" src="https://github.com/user-attachments/assets/200082ec-1459-4e1d-9919-b0210f08254b" />


Para extraer el cable Ethernet, presione el clip situado en la parte inferior del conector y deslice suavemente el cable para extraerlo del puerto.



2.2. Preparación de la Red Privada (Tailscale)
Antes de proceder a abrir Minecraft:

Localiza la dirección IP que se asigna al instalar y registrar una cuenta Gmail (personal o dedicada directamente al servidor) en Tailscale en la Raspberry y esa será la IP del servidor en Tailscale.

Entrar con SSH a la Raspberry, se coloca el comando "tailscale ip" y dará la IP Tailscale asignada a la Raspberry.
Hecho esto proseguimos.

Descarga e instala la aplicación oficial de Tailscale en tu ordenador habitual o en tu dispositivo móvil desde su página web (https://tailscale.com/download). Está disponible para sistemas Windows, Linux, macOS, Android e iOS.

Inicia sesión en la aplicación instalada utilizando tu cuenta de Gmail.

Asegúrate de que el interruptor de la aplicación de Tailscale aparezca en estado Connected (Conectado).

💡Puedes iniciar sesión con este mismo correo electrónico en todos los dispositivos que quieras (como tu ordenador de juegos y tu teléfono móvil) simultáneamente. En cuanto lo hagas, todos ellos quedarán interconectados de forma segura y directa a la Raspberry Pi a través de internet, permitiéndote jugar o administrar el servidor desde cualquier lugar del mundo de manera inmediata.


2.3. Instalación de herramientas de administración remota (SSH)
Para poder gestionar el servidor en el futuro (por ejemplo, para mandarle comandos o apagarlo de forma segura sin dañar el sistema operativo), necesitas tener preparado un cliente SSH en tu ordenador habitual. Dependiendo de tu sistema operativo, realiza la siguiente preparación:

Si utilizas Windows (Instalación de PuTTY):

Abre tu navegador web y descarga el instalador oficial de PuTTY desde su página web (https://www.putty.org/).

Ejecuta el archivo descargado y sigue el asistente de instalación dejando las opciones que vienen por defecto.

Una vez finalizado el proceso, ya tendrás la herramienta disponible en el menú de inicio de Windows para cuando necesites usarla en los siguientes apartados.

Si utilizas Linux (Uso de la Terminal nativa):
No necesitas instalar ningún software adicional. Los sistemas operativos basados en Linux cuentan con un cliente SSH integrado directamente en el sistema.

Simplemente localiza y abre la aplicación Terminal (puedes usar el atajo rápido Ctrl + Alt + T).

Mantén la ventana abierta para comprobar que responde correctamente a los comandos.

---

### 3. Cómo conectarse al servidor (Minecraft Bedrock)
Para poder entrar a jugar, asegúrate de tener la aplicación de Tailscale encendida en tu dispositivo y el servidor físico conectado. Dependiendo de la versión de Minecraft que utilices (Bedrock o Java), sigue los pasos correspondientes:

3.1. Si juegas en Minecraft Bedrock (Móviles, Tablets y Consolas)

A) Si estás en la misma casa que el servidor (Red Local)

Si estás conectado al mismo Wi-Fi o router que la Raspberry Pi, entrar es automático y no necesitas escribir ninguna dirección IP:

Abre Minecraft en tu dispositivo y pulsa en Jugar.

Entra en la pestaña de Amigos.

Baja hasta el final de la pantalla y busca la sección llamada "Partidas en LAN".

Verás que el servidor aparece ahí solo con el nombre del mundo.

¡Simplemente pulsa sobre él y entrarás directo a la partida!


B) Si vas a jugar desde fuera de casa (Solo para Móviles y Tablets)

Si vas a jugar usando tus datos móviles o desde el Wi-Fi de otra casa, Minecraft bloquea estas conexiones por seguridad. Para solucionarlo, haz este pequeño ajuste en tu juego por única vez:

Abre Minecraft, entra en el menú de Ajustes y selecciona el apartado Perfil (en algunos dispositivos se llama Cuenta).

Busca la opción "Usar datos móviles" (o Permitir datos celulares) y actívala.

En la pestaña de "Configuración de red", asegúrate de marcar la opción "Con Wi-Fi o datos móviles".

Nota: Si juegas desde un ordenador con Windows 10 o Windows 11, puedes saltarte este paso; en el ordenador funciona a la primera sin tocar nada.


C) Pasos para conectarte (Fuera de casa / Con la app de Tailscale)

Una vez hecho el ajuste anterior, sigue estos pasos para añadir el servidor a tu lista de juego:

Abre Minecraft Bedrock y haz clic en el botón Jugar.

<img width="1600" height="740" alt="INICIO BEDROCK" src="https://github.com/user-attachments/assets/ef689637-c436-40b9-ad5b-753532b24254" />


Dirígete a la pestaña  derecha llamada DESCUBRIR.
Luego haz clic en el botón Añadir servidor.

<img width="1600" height="740" alt="BEDROCK 2" src="https://github.com/user-attachments/assets/77f75d62-82b1-4281-ac8c-3847b5bd1c4e" />


Rellena los tres campos obligatorios que te solicita el formulario con los siguientes datos exactos:

<img width="1600" height="740" alt="BEDROCK 3" src="https://github.com/user-attachments/assets/cd1c1f66-4b8b-453a-b790-567de5317cad" />


Nombre del servidor: Introduce el nombre identificativo que prefieras (por ejemplo: Mi Servidor Pi).

Dirección IP / Dirección: Introduce la IP de Tailscale que la app te dió al vinvularla con el correo electrónico.

Puerto: Mantén el puerto por defecto de Minecraft Bedrock, que es el 19132.

Haz clic en el botón Guardar (esto fijará el servidor en tu lista para siempre) y, finalmente, selecciónalo y pulsa en Entrar al servidor.

Con estos pasos, el juego iniciará la carga de texturas y te conectará de forma segura a la partida alojada en la Raspberry Pi.


3.2. Si juegas en Minecraft Java Edition (Ordenadores)

Si utilizas la versión tradicional para ordenadores (Windows, Mac o Linux), sigue estos pasos utilizando la red de Tailscale:

Acceso al menú: Inicia el juego y, en el menú principal, haz clic en el botón Multijugador.

<img width="1600" height="899" alt="JAVA 1" src="https://github.com/user-attachments/assets/e066378d-f5c9-40c7-89de-ae57e833baeb" />


Agregar el servidor: Desplázate hacia abajo en el menú y haz clic en la opción Añadir servidor para guardarlo de forma permanente.

<img width="1600" height="899" alt="JAVA 2" src="https://github.com/user-attachments/assets/ac2a4c0d-04a6-4506-9016-279dcf5af76d" />


Introducir datos de conexión: Rellena los dos campos obligatorios que te solicita el formulario con los siguientes datos exactos:

<img width="1600" height="899" alt="JAVA 3" src="https://github.com/user-attachments/assets/e3afb4c5-c018-462f-b726-f5a02665b781" />


Nombre del servidor: Introduce el nombre identificativo que prefieras (por ejemplo: Mi Servidor Java).

Dirección del servidor: Introduce la IP de Tailscale. En Java Edition no es necesario añadir ningún puerto al final de la dirección.

¡A jugar!: Haz clic en el botón Aceptar, selecciona el servidor que acaba de aparecer en tu lista y pulsa en Entrar al servidor.

---

### 4. Uso del servidor

Una vez dentro, el entorno funciona exactamente igual que cualquier servidor estándar de Minecraft. A partir de aquí, puedes realizar las siguientes acciones de forma directa:

Crear mundos y jugar con otros jugadores: El servidor está alojado de forma permanente en la Raspberry Pi. Esto permite que tú y tus amigos podáis entrar a jugar juntos en el mismo mundo las 24 horas, sin depender de que nadie más tenga su ordenador encendido.

Construir y explorar: Todo el progreso del mapa, tus construcciones y los inventarios se guardan automáticamente en el almacenamiento de la Raspberry Pi en tiempo real, garantizando que el mundo no se pierda al salir.

Invitar a otros usuarios: Puedes añadir a más amigos al servidor compartiendo con ellos la IP de Tailscale. Solo necesitarán estar unidos a tu red virtual y abrir la misma versión del juego para empezar a jugar contigo.

---

### 5. Recomendaciones de uso

Para garantizar que el servidor funcione con la máxima fluidez y evitar pérdidas de datos o tirones (lag) durante el juego, se recomienda seguir estas pautas básicas:

Conexión por cable (Raspberry Pi): Siempre que sea posible, mantén la Raspberry Pi conectada al router mediante un cable Ethernet en lugar de usar Wi-Fi. Esto reduce drásticamente la latencia y mejora la estabilidad de la conexión para todos los jugadores.

Límite de jugadores simultáneos: El hardware de la Raspberry Pi es compacto. Para mantener un rendimiento óptimo y sin ralentizaciones, se recomienda un máximo de 6 a 8 jugadores conectados al mismo tiempo aunque está configurado para 12 que aún así sigue dando un buen rendimiento.

Distancia de simulación moderada: En los ajustes del servidor (o desde el menú de juego si eres administrador), mantén la distancia de renderizado de fragmentos (chunks) entre 4 y 8. Valores más altos obligan a la placa a procesar demasiado mapa a la vez, lo que puede causar tirones.

Apagado y reinicios limpios: No desconectes nunca la Raspberry Pi de la corriente de golpe. Si necesitas apagarla, hazlo siempre de forma segura a través de los comandos de la consola para evitar que el mapa de juego se corrompa. 

---

## 6. Desconexión y apagado seguro

Para garantizar que el progreso de tus construcciones e inventarios se guarde correctamente y el servidor físico no sufra ningún daño, sigue estos sencillos pasos al finalizar tus sesiones de juego:

### 6.1. Salida de los jugadores y guardado del progreso

1. Antes de cerrar el servidor, avisa a todos los usuarios conectados para que guarden sus objetos y abandonen la partida.
2. Abre el menú de pausa de Minecraft y haz clic en **"Guardar y salir"** (en Bedrock) o **"Desconectarse"** (en Java).
3. Al salir del juego, el servidor detectará que no quedan usuarios y mantendrá el mapa en un estado de suspensión seguro, listo para la próxima conexión.

### 6.2. Apagado físico de la Raspberry Pi

Necesitas apagar por completo el equipo físico (por ejemplo, para moverlo de sitio o limpiarlo), realiza el procedimiento en este orden:

1. Asegúrate de que **ningún jugador** esté dentro del mundo para evitar pérdidas de datos de última hora.
2. Apagado controlado de forma remota.
3. Observa las luces de la Raspberry Pi: verás una **luz verde** parpadear rápidamente, lo que significa que el servidor está guardando los últimos archivos en el disco.
4. **Espera obligatoria:** No retires el cable de corriente mientras la luz verde parpadee. Una vez que el parpadeo se detenga por completo y solo quede la luz roja fija (o se apaguen ambas), podrás desenchufar el cable de alimentación de la pared con total seguridad.

---

### 7. Solución de problemas comunes (FAQ)
Si experimentas algún inconveniente menor durante tu partida, puedes solucionarlo directamente modificando los ajustes desde la propia interfaz de Minecraft:

7.1. El juego se ralentiza o va "a tirones" al explorar el mapa
Causa: Tu dispositivo está intentando procesar demasiados bloques visuales a la vez.

Solución desde el juego: Entra al menú de Ajustes, ve al apartado de Video y busca la opción Distancia de renderizado (o Render Distance). Reduce el valor a un rango entre 4 y 8 fragmentos (chunks). El juego se volverá fluido al instante.

7.2. No puedo ver la lista de amigos conectados ni interactuar con el chat
Causa: Tienes las opciones de interfaz o el chat desactivados por error en los ajustes locales de tu perfil.

Solución desde el juego: Ve a Ajustes, selecciona Ajustes de chat y asegúrate de que la opción Chat esté configurada en Mostrado (o Visible). Si juegas en Bedrock, revisa también en el apartado de Perfil que la opción de "Unirse a partidas multijugador" esté activada.

7.3. No aparecen monstruos ni animales en el mundo, o el juego es demasiado difícil
Causa: La dificultad del mundo no está ajustada al gusto de los jugadores de la sesión.

Solución desde el juego: Abre el chat de texto dentro de la partida y escribe directamente el comando /difficulty peaceful (para modo pacífico), /difficulty easy (fácil) o /difficulty normal. La dificultad del servidor cambiará en tiempo real sin necesidad de reiniciar.

---

### 8. Mantenimiento
Para garantizar que el servidor funcione correctamente a largo plazo y que la Raspberry Pi no sufra desgaste innecesario, sigue estas tres reglas básicas de mantenimiento:

Reiniciar el sistema periódicamente: Al igual que un ordenador o un móvil, es recomendable reiniciar el servidor una vez a la semana (o después de sesiones de juego muy largas). Esto limpia la memoria interna acumulada, elimina procesos fantasma y hace que el juego vuelva a ir al 100% de velocidad.

Evitar apagados bruscos: Nunca desconectes el cable de alimentación de la corriente mientras el servidor esté en uso. Apagar la placa de golpe puede corromper el archivo del mapa, haciendo que perdáis vuestras construcciones o que el servidor no vuelva a arrancar. Sigue siempre el orden de apagado correcto.

Mantener el dispositivo bien ventilado: La Raspberry Pi procesa mucha información mientras juegas y puede calentarse. Asegúrate de que la carcasa no esté guardada en un cajón cerrado, cerca de un radiador o tapada con objetos. Mantenerla en un lugar fresco y despejado evitará que el juego vaya lento por exceso de temperatura.

---

### 9. Soporte
En caso de experimentar problemas técnicos complejos que no se hayan podido resolver a través de los ajustes internos de Minecraft (como caídas del servidor, problemas con la dirección IP o errores de conexión persistentes), debes ponerte en contacto:

Para reportar una incidencia, utiliza cualquiera de los siguientes canales oficiales:

Correo electrónico de soporte: gerardo025s@gmail.com

Información necesaria para el reporte: Al enviar tu mensaje, indica tu nombre de usuario en el juego (Gamertag) y, si es posible, una captura de pantalla con el mensaje de error exacto que te muestra Minecraft.

---

##  Autor

Juan Gerardo González Santos

---

##  Nota

Este servidor está pensado para grupos pequeños de jugadores, debido a las limitaciones de la Raspberry Pi.
