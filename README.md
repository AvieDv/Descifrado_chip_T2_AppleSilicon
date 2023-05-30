# Descifrado_chip_T2_AppleSilicon

# ¿Qué es el chip de seguridad T2?

El Apple T2 es un chip de seguridad de confianza. Asegura funciones esenciales, como Arranque
seguro, Bloqueo de activación, Touch ID y almacenamiento de datos cifrados. etc.

#¿Cómo funciona el chip de seguridad Apple T2?
El chip T2 tiene control sobre el procedimiento de arranque de MacOS. Se asegura de que todo lo que
se ejecuta en el hardware de el Mac esté aprobado por Apple. Su trabajo comienza tan pronto como se
presiona el botón de encendido en su computadora Mac y dura hasta que ve el escritorio de MacOS.
En otras palabras, una de sus funciones principales es verificar que Apple haya firmado su sistema
operativo y cargador de arranque. 
El chip T2, que ejecuta un software interno llamado BridgeOS (versión muy
modificada de WatchOS) nunca se apaga, excepto cuando la batería/pila está muerta (obviamente).

El T2 también es responsable de todos los datos de cifrado en la unidad flash. En versiones anteriores
de Mac, esta función la realizaba la CPU con intel y chip vBios, lo que ralentizaba la Mac en su conjunto. Al trasladar estas
funciones al chip T2, Apple ha mejorado significativamente el rendimiento de las nueva Mac de Apple Silicon, además de
permitir la seguridad de TouchlD. El escáner de huellas digitales en estos dispositivos brinda al usuario
una opcion de inicio de sesion rapido y aprueba las solicitudes de nivel de administrador.
También maneja las solicitudes de verificación de diferentes aplicaciones. El chip T2 se asegura de que
ninguna aplicación tenga acceso a la información de su huella digital a través de Touch ID. 
Cuando se solicita la verificación, el chip Apple T2 Security compara la huella digital con los datos asegurados en
el cobrocesador de enclave v notifica el resutado.
El chip T2 se basa en el procesador ARM del iPhone Chip A9, lo que lo hace vulnerable al mismo exploit
de checkm8, que los dispositivos Apple con procesadores A6 hasta el A11. 

Cómo hacer Jailbreak al chip T2 usando Checkra1n
Antes de hacer jailbreak al chip T2, primero necesita:
• Mac con chip T2 capaz de hacer jailbreak
• Otra computadora con MacOS
• Cable USB-C a USB-C

# Procedimiento:

Paso1. Descargue el último software checkra1n en MacOS que no está haciendo jailbreak. Esto se
puede hacer visitando el sitio oficial aquí 164, o, si usa la terminal debe instalar Homebrew, simplemente escribiendo:

# /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

Luego colocamos nuestra password.
y continua escribiendo:
brew install --cask checkraln

Paso 2. Pon tu Mac en modo DFU. Este es un proceso manual que puede tomar algo de tiempo y
esfuerzo para hacerlo bien. Creé una guía rápida.

Paso 3. A partir de ahora, la versión GUI de checkra1n no es compatible con T2 jailbreak. Como tal,
tenemos que usar la versión cli. Para hacerlo, abre la terminal y
escribe /Applications/checkra1n.app/Contents/MacOS/checkraln-c
Esto abrirá checkra1n en modo cli y comenzará a buscar un dispositivo DFU. 
Una vez que se encuentra uno, completará el jailbreak y tendrá acceso de root a su chip T2. 
A veces, checkra1n arroja el código de error 20. Si es así, simplemente reinicie checkra1n hasta que diga Bootstrap already installed.

Paso 4. SSH en su chip T2 por iproxy. 
iproxy 2222 44 
NO cierre la ventana, simplemente abra una nueva y escriba:
ssh root@localhost -p 2222
con la contraseña de root. ¡Ahora tiene un shell SSH en su chip!

¿Qué puedo hacer con esto?
Ahora es el momento de algunos ejemplos prácticos de lo que se puede hacer con un jailbreak de chip
T2. El problema es que aquí es donde está TODA la seguridad de Mac, lo que significa que la unidad
se puede descifrar, se puede instalar un EFI malicioso, etc. Dado que MacOS lo consideraba completamente
confiable, el usuario no podría detectarlo. Estoy investigando!


