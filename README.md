# 🌐 EL MEGA MANUAL DEL SUBNETEO 🌐
> **Autor:** @Elhsup 🚀  
> *Dure como 3 dias haciendo esta wea DIOSSSSSSSSSSSSS SUPER LADILLA PERO TERMINE JEJAJAJAJ*

---
---

## 🔌 TÓPICO 1: EL SISTEMA BINARIO Y HEXADECIMAL 🔌

Las computadoras son circuitos electrónicos. Ellas no entienden qué es un 192, ni un 168, ni la letra A. Ellas solo entienden si pasa luz/electricidad (**1**) o si no pasa (**0**), y así es como se comunican entre sí.

### 🔢 Los Binarios 
Tienen por base 2 porque en los números binarios solo está el 0 y el 1. Las computadoras trabajan con esos estados porque es rápido o/y sencillo procesar la información para las PC (sé que sería difícil de entender, pero imagina Y ES SU lenguaje). Con esos 2 es que trabajan las computadoras y otros dispositivos como **>routers y modems<** 🛑 *¡Acuérdate de eso!*

---

## 📬 TÓPICO 2: IPV4 (El Servicio Postal del Internet) 📬

Ahora vamos con las redes. ¿Tenemos el **IPV4** kjeso? Es una forma de administrar las redes. El IPv4 vendría a ser como un identificador de las casas, avenidas, etc., y la red un servicio postal donde mandas una carta. Para la red saber a quién le va a llegar la info, utilizan el IPv4, o sea, revisan el número de casa, quién la mandó, etc. Recordemos que una carta se la tiene que enviar una persona a otra, en este caso sería un dispositivo a otro.

### 💼 ¿Cómo trabaja esa vaina? ¡Con 32 bits! 
¿Por qué trabaja con 32 bits? Porque le da la gana xxddxxd. En realidad, por medio de unos estándares y muchas otras cositas fue que terminó así.

> 📝 **El Bit:** Es la unidad mínima de información, o sea, guarda datos que no pesen mucho como un voltaje `:b`. El bit funciona igual que los números binarios: solo puede haber 1 y 0. En este caso guarda la información eléctrica (cuántas veces llegó el 1 y el 0). 
> 
> 📦 **El Byte:** Pasa algo curioso: si agrupas **8 bits** forman un **Byte**, que es un estado más grande y guarda más información. Tranquilo, esa forma en que guarda la información la PC lo hace sola por medio de procesos de llegada, métodos para guardar la información, etc. ¡Y ya eso es todo del bit pirobo!

### 🧱 Los 4 Bloques (Octetos)
¿Ahora por qué te conté todo eso? Porque una dirección IPv4 tiene 32 bits (32 ceros y unos), divididos en 4 grupos de 8 bits. O sea, tipo = `8 + 8 + 8 + 8 = 32`. El primer 8 es un grupo, el segundo 8 es un grupo y así hasta llegar al 4...

Por si no lo entiendes, ¿te acuerdas que te hablé del Byte? También, dicho de otra forma, serían: **4 Bytes**. Trata de analizar la info. Por si no lo entiendes o para que lo entiendas de otra manera, serían: `1 byte . 1 byte . 1 byte . 1 byte`. Así serían 4 bytes diferentes, no serían los mismos porque si no sería una información repetida.

*   Cada grupo de 8 bits se llama **Octeto**.
*   Cuando tú escribes 255, la computadora ve `11111111` (8 unos encendidos). *<-- Eso creo que lo explicaré más adelante...*

#### 🌎 Ejemplo de cómo se ve:
Una IP sería = `255.255.255.255` *(Ojo: esto no es una red, es la dirección de Limited Broadcast, un broadcast universal).* 

Entonces serían los 4 grupos, que son los 4 "255" de arriba. El primer 255 es un grupo y así p. 
*   Si juntas esos 4 grupos, son **32 bits**.
*   En bytes, me dan **4 bytes** pa k entiendas mucho más mejor...

---

## 📈 TÓPICO 3: LA MATEMÁTICA DEL OCTETO 📈

El número máximo de un octeto es **255** porque matemáticamente:
$$2^7 + 2^6 + 2^5 + 2^4 + 2^3 + 2^2 + 2^1 + 2^0 = 255$$

Tú te preguntarás: *¿De dónde salió el 2? ¿Por qué lo estamos elevando? No entiendo watafak por qué hacemos eso.*

La questioneishion es que trabajamos con el binario 1 y 0, o sea, **2 estados**. De ahí sale la base 2. ¿Y empezamos a hacer las potencias empezando por el cero? ¿Y por qué? Porque por el cero se puede representar el estado de apagado en la informática. Nosotros empezamos por el 0 en este caso; aunque es un valor nulo, nosotros lo tomamos por lo general como un número positivo. 

Ok, aquí lo que estamos haciendo es el **<<sistema posicional de los números binarios>>**, o sea, que si $2^7 + 2^6$ etc. etc. En este caso es cómo los datos se agrupan y las computadoras guardan la información. (No se cuenta el 8 porque nosotros contamos desde el cero y porque el número límite es el 255).

¡Ahora te vas a caer pa atrás cuando te des cuenta de que en decimales (o sea, los números normales) es! =
`128 + 64 + 32 + 16 + 8 + 4 + 2 + 1` 👈 La tabla esa de los octetos. *(Estos números nos van a ayudar más adelante >:D).*

Para terminar, esa es la forma principal con la que las redes trabajan su orden y al mismo tiempo nos ayuda para otras cosas importantes en redes brrrrrrrrrrrrr.

---
---

## 🏠 TÓPICO 4: LA RED Y EL HOSTTTTT WASAAAAAAAAAAAAA 🏠

Si tienes la IP: `192.168.10.5`
*   `192.168.10.` ➡️ **RED**
*   `.5` ➡️ **HOST**

Tenemos la IP. En la IP tenemos la red y el host. La red es para comunicarse con el mundo y el host con los dispositivos de tu casa. Hablaremos más adelante de eso.

*   **La Red:** Es cómo los dispositivos se conectan al mundo, por decirlo así, el cómo tu router se conecta al mundo por medio de tu distribuidor de internet (que si Inter, Thundernet, etc., etc.). Entonces, en nuestras casas todos tenemos la IP más común: `192.168.0.1`.

Recordemos que hay varias clases y tipos de red:

### 🏙️ << Redes Públicas >>
*   **Clase A:** `1.0.0.0` hasta `126.255.255.255` *(quitando el bloque del 10).*
*   **Clase B:** `128.0.0.0` hasta `191.255.255.255` *(quitando el pedacito de la 172.16 a la 172.31).*
*   **Clase C:** `192.0.0.0` hasta `223.255.255.255` *(quitando el bloque 192.168.0).* ¡Pa la casa!

### 🔄 << Esta se salta las reglas >>
Pilla aquí: la **<127>** no está disponible porque `127.0.0.1` (o localhost) no es ni pública ni privada, porque está reservada exclusivamente para el bucle local (**loopback**). Su única función es permitir que tu dispositivo se comunique consigo mismo, o sea, mandas un dato y lo recibes.

### 🔐 << Redes Privadas >>
*   **Clase A:** Desde `10.0.0.0` hasta `10.255.255.255`
*   **Clase B:** Desde `172.16.0.0` hasta `172.31.255.255`
*   **Clase C:** Desde `192.168.0.0` hasta `192.168.255.255`

---

## 📊 TÓPICO 5: EXPLICACIÓN DE LAS CLASES DE REDES 📊

*   **En la Clase A (`1.0.0.0`):** El primer octeto de izquierda a derecha es red y esto no cambia (el 1). Es para empresas grandes. Entonces en la A tendrías RED y los demás son HOSTS. Es decir, ¡muchisiiiiimos dispositivos pa conectarte!
    *   *Gráficamente:* `RED . HOST . HOST . HOST`
*   **En la Clase B (`172.16.0.0`):** El primer y segundo octeto de izquierda a derecha es red y esto no cambia (el 172.16). Para empresas medianas. En este caso es lo mismo que la A, pero ya no tienes tantos hosts; sin embargo, todavía te quedan muchísimas.
    *   *Gráficamente:* `RED . RED . HOST . HOST`
*   **En la Clase C (`192.168.0.0`):** El primer, segundo y tercer octeto de izquierda a derecha es red y esto no cambia (el 192.168.0). Este sirve pa la casa porque son poquitos hosts.
    *   *Gráficamente:* `RED . RED . RED . HOST`

---

## 💻 TÓPICO 6: EL HOSTTTTTTTTTTTTTTTTTTT (La Casa) 💻

Identifica al dispositivo específico dentro de esa calle (tu PC, el teléfono, la impresora). Este número **tiene que ser único** en esa calle; si clonas un Host, da conflicto de IP. 

Creo que se entiende, ya que colócate que el `192.168.0.0` es la calle por decirlo así, y tu dispositivo es `192.168.0.1`. Lo único que cambió en la IP es el host, o sea, ese 1. Ejemplo: que en tu compu está asignada así y tu teléfono también se conecte a la red, ejemplo, entonces sería `192.168.0.2` y tu impresora `192.168.0.3` y así sucesivamente. Ese número te indica si está conectado y es el host.

### 💥 El problema de la Clase C (La muy desgraciada)
Acá pasa algo con esta red ya que es un poquito diferente. Como verás, no tenemos tantos hosts acá, solo **254**. Lo que hacemos es agarrar y cambiar el número de un octeto de red, el tercero para ser específico, y tenemos 254 hosts más. ¿Por qué hacemos esto? Para tener más espacios para más hosts (que son dispositivos), pero la desventaja es que está totalmente aislada de la otra red.
*   *Red 1:* `192.168.0.1` ➡️ Por acá pasa una información.
*   *Red 2:* `192.168.1.1` ➡️ Por acá pasa otra. *(No se comunican entre sí).*

¡Pero de esta "desventaja" sale otra ventaja! Y es que están aisladas y no se comparten información. Se puede tener una red para algo y otra para otro algo, o sea, una red para los profes y otra para los estudiantes. No se pasa información que no se quiere. Además, si se quiere que se comuniquen entre sí, tenemos los **routers** que los podemos configurar, tonce desventaja como tal no hay `:b`. *(Esto también lo podemos hacer para las otras redes y sirven como control y más cositas pa las redes).*

---

## 🧠 TÓPICO 7: LO QUE APRENDÍ EL 11/6/2026 (Red, Host y Broadcast brrrrr) 🧠

### 🤔 ¿Cómo se ve la red en una IP y qué vendría siendo?
La red se ve así:
*   `10.0.0.0` , `11.0.0.0` , `12.0.0.0` ➡️ Es una red.
*   `172.18.0.0` , `172.19.0.0` , `173.1.0.0` ➡️ Es una red.
*   `192.168.0.0` - `192.168.1.0` - `195.163.9.0` ➡️ Es una red.

#### 🅰️ << En Clase A >>
El primer octeto (los primeros 8 bits) define la identidad de la red. Es decir, que si agarramos `10.0.0.0` es una identidad de red. La red `11.0.0.0` es otra identidad de red totalmente diferente. ¿Por qué? 

Porque existe la **máscara de subred** (hablaré más adelante de la subred y la máscara) y esta tiene como parámetro o criterio (por medio de cómo está configurada gracias a las compuertas lógicas OR, AND, etc.) que cuando una red tenga el primer octeto diferente al otro, no se puedan comunicar entre sí. O sea: `10.0.0.0` y `11.0.0.0`. Claro, la máquina no funciona así, se guía por medio del binario:
*   `00001010` = `10.0.0.0`
*   `00001011` = `11.0.0.0`

> ✨ *O sea, más sencillo: acá lo importante es que si no están en cero los 3 últimos números, no es red.*

*(Sin embargo, si no tuvieran la máscara de subred, sí se podrían comunicar entre sí como si todo fueran hosts, y se pueden comunicar red con red sin ningún problema retóricamente, ya que se usa la subred para más control y que no se dañen las computadoras porque evita que haya demasiada información de una sola vez. Sin embargo, la forma en que se conecta una red con otra es por medio del router).*

#### 🔄 ¿Cómo se hace el cambio?
La red `10.0.0.0` es una identidad de red. El número `11.0.0.0` es otra identidad de red totalmente diferente. O sea, son redes diferentes. ¿Cómo se hace este cambio o cómo llegamos del `10.0.0.0` al `11.0.0.0`? **Llenando toda la red de hosts**, o sea:

Por el tamaño y la capacidad de los bits, en este caso son 8 agrupados en 4 grupos que cuentan con 256 combinaciones, pero podemos utilizar 255. En este caso, si ves en la red, empezamos a contar de los hosts de derecha a izquierda, que los números se van llenando poco a poco. O sea: `10.0.0.0` ➡️ `10.0.0.1` ➡️ `10.0.0.2`. Técnicamente estás sumando. Si le sumas 1 a `10.0.0.2` te va a dar `1 + 10.0.0.2 = 10.0.0.3` hasta llegar a los `10.255.255.255` y si le sumamos uno más nos daráaaaaaaaaaa **`11.0.0.0`**.

#### 🅱️ << El 172.16 ahí es red >>
Lo sabemos porque en la **Clase B** agarramos los 2 octetos y el sistema tiene de forma automática de saber que a partir de 128 todo es diferente a partir del 128. No necesita leer toda la IP ni adivinar, o sea, es automático que sabe el cambio de la clase. No tendríamos que hacer nada en ese caso, solo aprendernos cuándo hay un cambio de clase y de ahí empieza a contar el primer y segundo octeto. Además, le basta con ver que el primer bit de la izquierda se encendió en 1.

*   El número 127 se escribe: `01111111` *(El primer bit de la izquierda está apagado en 0).*
*   El número 128 se escribe: `10000000` *(El primer bit de la izquierda se enciende en 1).*

Ese simple cambio eléctrico en el primer bit es la seña universal que redefine por completo cómo la tarjeta de red va a interpretar los octetos a partir de ese momento. Para saber de forma binaria usamos la tabla `(128 + 64 + 32 + 16 + 8 + 4 + 2 + 1)`. Con esta tabla podemos calcular en binario si es 10; sumamos los números que nos den 10, o sea, `00001010` ($8 + 2 = 10$). Mira las posiciones de la tabla y de los ceros y unos, y literalmente esos ceros y unos son los bits. Cuenta cuántos ceros y unos son..... exacto, **8 bits**.

> ✨ *O sea, más sencillo: acá lo importante es que si no están en cero los 2 últimos números, no es red.*

#### 🆃 << Lo mismo pasa con la Clase C >>
P, me imagino que ya lo entiendes. Nada más en vez de 2 son 3 octetos. Ejemplo: `192.168.0.0` and `192.170.0.0`.

> ✨ *O sea, más sencillo: acá lo importante es que si no está en cero el último número, no es red.*

---

### 💻 Ahora el Host:
Es sencillamente todos los dispositivos que se pueden conectar a una red. En la **Clase A** se pueden conectar muchoosotototoetettes, o sea, en la IP `10.255.255.254` ahí se pueden conectar. En esa IP contamos todos los hosts (dispositivos), o sea: `.255.255.254`. Ese numerote se puede conectar de dispositivos, ahora son **16,777,214**.

¿POR QUÉ NO EL `10.255.255.255`? ¡Porque eso es broadcast `:b`!

### 📢 El Broadcast:
El broadcast es por medio del cual la red envía la información a toooodoooos los hosts. Es como un altavoz. La red es el papá de los pollitos, los hosts son los pollitos y el broadcast es con lo que el papá pollo usa para comunicarse con todos, así p. Se ve: `192.168.255.255` o `192.168.1.255`.

---
---

## 😷 TÓPICO 8: MÁSCARA Y SUBRED (Adivina adivinador) 😷

Verán, en este caso les hablaré de la máscara. Arriba me traté de enfocar en todo sin necesidad de meter la máscara porque necesitábamos lo básico. Ahora sí vamos con la mascariña...

*   **La Máscara es la herramienta de corte:** Es ese filtro matemático de unos y ceros que le instalas a la tarjeta de red. O sea, la máscara está **HECHA PARA CREAR LAS SUBREDES**.
*   **La Subred es el territorio creado:** Es el vecindario de IPs que nace después de aplicar ese corte con la máscara, tipo cambia el tamaño de la red. En vez de 16,777,214 hosts, solo utilizarás los 255. Pero reales y usables son 254 hosts de la Clase C. O sea, el dónde empieza y termina la red. **OJO: ESCRIBI LA RED, NO HOST. LA SUBRED SE CREA GRACIAS A LA MÁSCARA**.

No sé si se acuerdan de que anteriormente les dije que las clases de las IP eran muy grandes y la única que era muy poquita era la C (si hablamos en términos privados, obvio). Entonces, al no haber un tipo estándar para que las empresas o personas tengan suficientes IPs o que no tuvieran tantas IPs innecesarias, se volvió un problema (y la empresa que creó esas IPs pues... se le estaban acabando, k peo chico).

*   **Antes (Sin máscara):** Si tenías la red `10.0.0.0`, estabas atrapado en un único vecindario gigante de 16 millones de hosts. No podías dividirlo. Si intentabas usar `10.10.0.0`, como aprendiste al principio, el sistema se confundía y lo veía como un simple dispositivo más, no como otra red.
*   **¡Y PUM! Se creó la máscara:** Para poder dividir las direcciones IP y tener los hosts que necesitemos, ni más ni menos. Esto se hace porque se configura en la tarjeta de red, al mismo tiempo que la dirección IP -> (eso lo hacemos nosotros). Tipo: a partir de ahora, el primer octeto ya no define el tamaño de la red. Tú puedes elegir la IP que quieras (así empiece por 10, por 172 o por 192) y, usando la máscara, podrás cortar los bits exactamente donde te dé la gana.
*   **Después (Con máscara):** Gracias a que se inventó la máscara, pudiste agarrar ese bloque gigante del `10.0.0.0` y, aplicando máscaras como `255.255.255.0` (`/24`) —mira que acá estamos usando la máscara de la red Clase C—, pudiste "picar" ese territorio en miles de subredes independientes (como la `10.1.1.0`, la `10.1.2.0`, etc. Checa, ¡está funcionando como la red Clase C WAJAJAJA de locosh!).

> 💡 Gracias a la máscara de subred creas una nueva funcionalidad de la red. Aunque sea Clase A, B o C, una B puede funcionar como C y así. Si a cualquier IP (incluso la C que es `192.168.0.0`) le configuras manualmente la máscara `255.0.0.0` (`/8`), el chip de la tarjeta de red obedecerá ciegamente esa máscara.

---

### 🎭 Las 3 formas de la máscara
Ok, así como las IP tienen clases de red (la Clase A = 0 a 126), también tienen su máscara que nos indica el rango. Podemos verla en 3 formas:
1.  **Decimal:** `255.0.0.0`
2.  **En bits:** `/8`
3.  **En binario (mi broski):** `11111111.00000000.00000000.00000000`

¿Por qué? Si leíste la primera parte de este archivo (o texto donde lo estés leyendo), estas 3 formas de escribir la máscara quieren decir lo mismo porque tiene 8 espacios (los 8 bits individuales). Y esos 8 espacios encendidos suman un valor máximo de 255 porque la base es 2 y entre más bits haya, más cantidad se puede utilizar. O sea, empezamos con $2^0$, después $2^1$, $2^2$ y así hasta $2^7$ que nos da el 128; y sumado todo eso nos da 255, generando **256 combinaciones posibles en total (contando el cero)**. 

*(Acá esto del 256 es curioso. Verás, en realidad son 256, pero las computadoras empiezan a contar desde el 0, no como nosotros que contamos desde el 1. Entonces es como que tenga 10 dedos y el primer dedo que empiece a contar sea cero: no voy a llegar a 10 nunca aunque tenga 10 dedos. Es más que todo una perspectiva).*

> **PA HABLARTE MAS CLARO:** Para nuestra perspectiva como humanos, con esos 8 bits (del $2^0$ al $2^7$) ya tenemos matemáticamente las 256 combinaciones. No necesitas un bit más. Lo que pasa es que al empezar a contar desde el cero, el número más alto que podemos *escribir* en decimal es el 255. ¡Pero las 256 opciones están ahí, mi broski!

Son espacios donde guardar la información. Esos 8 bits forman el primer octeto. ¿And cómo se escriben esos 8 bits activos o que les llega el pulso eléctrico? Así = `11111111`.

Y los números binarios no son otra cosa que esta tabla: `128 + 64 + 32 + 16 + 8 + 4 + 2 + 1`. Entonces, si tú sumas todos esos números, te dan 255. ¿Y cómo lo colocamos o calculamos en binario? Ok, en esta tabla lo que harás es sumar los números necesarios para llegar a una determinada cantidad. Ejemplo: para llegar al 255 necesitas sumar todos los números. Los números que usaste para sumar serán 1 y los que no usaste serán ceros. Y como sumaste todos los números, te da = `11111111`.

¿And por qué? Esa tabla tiene 8 cantidades mijo, esos son los bits que estamos agarrando, los 8 bits de arriba. Piensa mijo. Y como nosotros usamos los números decimales (o sea, los de toda la vida), escribimos 255 y ya. Eso es todo pirobo. *(No puedes alcanzar otra cantidad más grande que 255, piensa el porqué xd).*

---

### 📋 Clasificación rápida (Pa que se te haga más fácil, pero ya es lógica)

| Clase | Decimal | Octeto (CIDR) | En Binario |
| :--- | :--- | :--- | :--- |
| **Clase A** | `255.0.0.0` | `/8` | `11111111.00000000.00000000.00000000` |
| **Clase B** | `255.255.0.0` | `/16` | `11111111.11111111.00000000.00000000` |
| **Clase C** | `255.255.255.0` | `/24` | `11111111.11111111.11111111.00000000` |

¿Por qué hay tantos ceros? Mijo, son 4 grupos de 8. Solo hay grupos de 8 bits encendidos, o sea, un octeto encendido p, pa que entendais...

#### 🧠 También podemos entender que:
*   **Por qué se usa 255:** El número 255 representa un octeto que tiene sus 8 bits completamente encendidos en binario (`11111111`). Para el hardware, ver un 255 es una orden física que significa: *"Este octeto completo está congelado y blindado, es el nombre de la red, ningún host puede tocarlo"*.
*   **Por qué se usa 0:** El número 0 representa un octeto con sus 8 bits apagados (`00000000`). Para el hardware significa: *"Este octeto está completamente libre para asignar números de casa (hosts)"*.

El colocar la máscara es la intervención para llegar a la subred, pero nos falta algo importante que es el **Subnetting**, que son los procesos lógicos y matemáticos para calcular cómo se verá la red de ahí. Lo hacemos por medio de la máscara y dará el resultado de la subred.

---
---

## 🪓 TÓPICO 9: SUBNETINGGGGGGG ACA VAMOS... 🪓
*(Una carita de loco 🤪)* ¡YA VAMOS A TERMINAR, no se preocupen! Ahora a lo que todos vinieron: el subneteo.

> 🚨 **¡¡Si de verdad quieres entender, lee todo lo de arriba porque va a estar bastante complicado no saberte nada, campeón o campeona, vos podéis!!**

Acá la verdad va a estar algo difícil. ¿Por dónde empezamos?

### ❓ ¿QUÉ ES EL SUBNETEO?
El subneteo en sí no modifica la clase como tal ni la hace más grande, solo recorta o crea muros para que cada red sea diferente. Es como un edificio con secciones. Al crear 2 subredes o colocar 1 bit en host, creas 2 subredes nuevas. Es como cuando cambias la máscara de una clase, solo que agregándole más secciones. Mira este ejemplo:

¿Recuerdas desde dónde empieza una red?
*   `192.168.0.0` = **Red**
*   Desde `192.168.0.1` hasta `192.168.0.254` = Es la cantidad de **hosts** que tiene.
*   `192.168.0.255` = Es el **broadcast**.
*   `192.168.1.0` = Esto es un **cambio de red**, pero sigue en la misma Clase C.

Ahora tengamos el ejemplo de si partimos a la mitad esa red `192.168.0.0`. No vamos a tocar el `192.168.1.0`, solo `192.168.0.0`:

*   🧱 **Primera Mitad (Subred A):** Esta sección ocupa los primeros 128 números (del 0 al 127).
    *   *IP de Red (ID):* `192.168.0.0` (Identifica a esta primera mitad).
    *   *Primera IP utilizable:* `192.168.0.1` (Para tu primera computadora).
    *   *Última IP utilizable:* `192.168.0.126` (Para tu última computadora).
    *   *IP de Broadcast:* `192.168.0.127` (El límite donde choca el muro).
*   🧱 **Segunda Mitad (Subred B):** Esta sección ocupa los siguientes 128 números (del 128 al 255).
    *   *IP de Red (ID):* `192.168.0.128` (Identifica a esta segunda mitad).
    *   *Primera IP utilizable:* `192.168.0.129` (Para la primera computadora de este lado).
    *   *Última IP utilizable:* `192.168.0.254` (Para la última computadora de este lado).
    *   *IP de Broadcast:* `192.168.0.255` (El final absoluto de esta red).

Eso que está arriba es el subneteo. Lo quise explicar en menor medida para que se entienda. Acá vamos a encender los bits de izquierda a derecha del último octeto, estamos hablando en binario acuérdate.

---

## 🧮 TÓPICO 10: LAS 4 FÓRMULAS DEL SUBNETEO 🧮
Bueno, hay en total 4 fórmulas que me he visto (la IA me ha dado) para calcular las redes brrrrrrrr.

### 1️⃣ Fórmula para calcular la Cantidad de Subredes
Lo primero es recordar que cada octeto de una IP tiene 8 bits. De izquierda a derecha, cada bit tiene un "peso" o valor en decimal que se duplica, o sea la tabla: `128 + 64 + 32 + 16 + 8 + 4 + 2 + 1`. Para crear subredes, tienes que encender bits de izquierda a derecha en el último octeto.

Acá lo que hacemos es robar `>:D`. En este caso estamos en la Clase C, pero para crear las subredes necesitamos robar bits del host. ¿Te acuerdas de lo que hicimos con la máscara? Cambiamos los límites de las redes a nuestro antojo, una C la convertimos en una B o A. Acá es lo mismo y, además de poder cambiar la forma como trabaja, podemos modificar el espacio de las mismas, o sea, crea muros.

> **Fórmula:** $$2^n$$  
> Donde **n** es la cantidad de bits que vas a robar, y el resultado debe ser igual o mayor a las subredes que necesitas.

Sirve para saber cuántos mini-vecindarios vas a crear. Acá nos referimos a dividir una IP en otra. Ejemplo: a la red `192.168.0.0 /24` <-- máscara, y nos piden que hagamos **8 subredes**. 

*(Aprovechando este ejemplo, he de decir que no se pueden obtener redes o hosts impares, así que siempre redondea hacia arriba `:b`, o sea, buscar un número par que sea mayor al que estábamos buscando, porque el binario trabaja con base 2 que son solo 2 números: el 1 y el 0).*

Entonces tenemos esta fórmula: $2^n$
*   **2:** Porque es base 2 el binario.
*   **^:** Potencia, porque así es como trabaja la suma de los octetos.
*   **n:** Es una variable. Eso quiere decir que no sabemos cuál es el número que debemos colocar. Debemos colocar en la potencia un número que dé un resultado similar o mayor a la cantidad de subredes que me piden. O sea, $2^3$ porque $2^3 = 8$. Ahora con esto sabemos que debemos robar 3 bits y se convertirá en 8 subredes, y los 3 bits encendidos en decimal suman 224, que esa será nuestra nueva máscara `:)`.

O sea, reemplazamos la `n` por el número 3. Fórmula: $2^n$ -> Quedaría: **$2^3$**

#### 💡 Truquiño de Elhsup `>:D`:
También podemos usar la tabla... Vamos a usar potencias, ¿verdad? En este caso podemos ver el resultado de las potencias que es la tabla:

*   **Posiciones de los bits (orden en que te robas los bits y los sumaras):**  
    `1 | 2 | 3 | 4 | 5 | 6 | 7 | 8`
*   **Tabla de los bits (valores decimales):**  
    `128 + 64 + 32 + 16 + 8 + 4 + 2 + 1`
*   **Potencia de los bits:**  
    `2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0`

Abajo la potencia, en medio el resultado (ejemplo: $2^6 = 64$), y en la primera fila el orden, tenemos las posiciones. Recuerda: los números que usaste para sumar se convierten en 1.

Ok, ahora les mostraré cómo se ve en bits y en decimal para que se entienda mejor. Ejemplo IP: `192.168.0.0`

| Elemento | En Decimal | En Binario |
| :--- | :--- | :--- |
| **La Red** | `192.168.0.0` | `11000000.10101000.00000000.00000000` |
| **Máscara Subred** | `255.255.255.224` | `11111111.11111111.11111111.11100000` |

Acá mira cómo nos metimos en el 4° octeto y robamos 3 bits del host (`|111|00000`). El host son los ceros, la red son los 1. Ok, ahí modificamos la máscara y es técnicamente crear más muros. Ahora ya sabemos cuántos bits robamos y cuántas subredes creamos. En el siguiente paso les mostraré cómo modificar la máscara de subred `:b`.

> ⚠️ **Recordatorio de seguridad:** Nunca puedes robar ni 7 ni 8 bits en una Clase C, porque te quedarías sin espacio para poner equipos (hosts). El límite sano es hasta 6 bits.

---

### 2️⃣ Fórmula para calcular las IPs Totales por Subred
Sirve para conocer el tamaño completo de cada bloque, incluyendo los espacios reservados. Ok, esta "fórmula", que es más como un atajo, te dirá qué tamaño tiene cada bloque o sección; o sea, desde dónde es red, host y broadcast.

> **Fórmula:** $$2^h$$
*   **2:** Porque es base 2 el binario.
*   **^:** Potencia, porque así es como trabaja la suma de los octetos.
*   **h (la h representa al host):** También es una variable. Acá colocaremos el número de ceros (hosts) que nos quedan. Ejemplo con el caso de arriba: robamos 3 bits. Al hacer ese robo, ¿cuántos ceros nos quedan?
    *   *Inicio:* `00000000` (Tenemos 8 ceros).
    *   *Con el robo de bits:* `11100000` (Nos quedan 5 ceros). Ese 5 va a ser lo que colocaremos en la `h`.

$$2^5 = 32$$
Tendremos un espacio de **32 direcciones en total**, contando red y broadcast `:b`. Oe, ¿pero tú quieres saber solo los hosts? Pues réstale 2 a tu resultado y ya, jajaja. *(Explicación abajo).*

---

### 3️⃣ Fórmula para calcular los Hosts Utilizables (IPs para equipos)
¡ESTA FORMULA! Te dice cuántas computadoras reales puedes conectar en cada subred, cobrando el "impuesto" de la dirección de red y el broadcast.

> **Fórmula:** $$2^h - 2$$
*(Es la misma fórmula de arriba, nada más réstale 2 al resultado final y ya).* Cabe recalcar que es el resultado menos 2.

*   *Ejemplo:* Usando el caso anterior de 5 ceros ($2^5 = 32$), le restas 2, el resultado es que puedes conectar exactamente **30 computadoras reales**.
*   *¿Por qué?* Ahí estás es restando la red en sí y el broadcast. Eso no son hosts, no es algo utilizable para un dispositivo ya que la red le indica al router dónde comienza todo y el broadcast es el megáfono.

---

### 4️⃣ Fórmula del "Salto Mágico" (En Decimal)
Si no quieres pasar todo a binario para saber dónde empieza la siguiente subred, usas esta resta matemática simple en decimal:

> **Fórmula:** $$\text{Tamaño del salto} = 256 - \text{El número de la nueva máscara}$$
*(O sea, la que modificaste p, en este caso el último octeto porque es Clase C).*

Tú puedes robar la cantidad de bits que quieras y pasar por encima de 1, 2 o hasta 3 octetos si es necesario. Pero al momento de calcular el salto en decimal, tu mirada debe ir directo al **último octeto donde pusiste un número diferente a 255 y a 0**. Ese es tu "octeto de frontera" y ahí es donde haces la resta.

*    Si tu nueva máscara calculada termina en `.192`, haces la operation `(256 - 192)`. El resultado es **64**. Tus subredes saltarán de 64 en 64 (ej. `.0`, `.64`, `.128`, `.192`).
*   Para nuestro ejemplo sería: `256 - 224 = 32`. Ejemplo: empieza en 0 y termina en 31; la otra empieza en 32 y termina en 63; la otra empieza en 64... Si te dio 32, súmale otros 32 y ahí te da el salto. Ve sumándole 32, pendiente de no confundirte ahí; los resultados son donde empieza cada red.

> **Lo que yo hago:** Primer resultado es 32, me voy un paso atrás: 31. Ese es mi final (de la primera subred). Coloco de una vez el principio de la otra que es 32 para saber dónde empieza. Luego de eso borro todo en la calculadora, coloco `32 + 32` y me da el siguiente, y así p.

---

### 📌 En resumen para hacer un subneteo así bien sabroso calidad nene 10/10 obra maestra:
1.  **Calcular cuántas redes nos piden:** Fórmula $2^n$ (un número que sea igual o más grande a las subdivisiones que nos piden).
2.  **Tamaño de las IPs totales:** Fórmula $2^h$ (los hosts que nos quedan en ceros).
3.  **Calcular los hosts utilizables:** Fórmula $2^h - 2$ (cabe recalcar que es el resultado menos 2).
4.  **El salto de cada IP:** $\text{Tamaño del salto} = 256 - \text{el número de la nueva máscara}$ (pendiente acá que es el octeto que modificaste).

---
---

## 🛠️ TÓPICO 11: EJEMPLO DE CÓMO CALCULAR Y CAMBIAR LA MÁSCARA brrrrr 🛠️

Miramos nuestro último octeto en binario. Originalmente eran puros ceros (`00000000`) porque obviamente no habíamos tocado o cambiado la máscara. Como decidimos robar 3 bits, encendemos los 3 primeros bits de la izquierda:
*   *Último octeto de izquierda a derecha (el 4° octeto p):* `11100000`

Ahora calculamos el valor decimal de esa máscara usando nuestra tabla del octeto:
*   **Posiciones de los bits:** `1 | 2 | 3 | 4 | 5 | 6 | 7 | 8`
*   **Tabla de los bits:** `128 + 64 + 32 + 16 + 8 + 4 + 2 + 1`

*   El primer bit vale **128**.
*   Sumando los 2 bits valen **192** -> ($128 + 64 = 192$).
*   Sumando los 3 bits valen **224** -> ($128 + 64 + 32 = 224$).

Tu nueva máscara decimal será: **`255.255.255.224`**  
En notación corta (CIDR): como la máscara original tenía 24 unos y le sumamos 3 nuevos, ahora es **`/27`**.

#### 🔄 Cómo cambia visualmente:
*   *La máscara original así:* `255.255.255.0`
*   *La máscara modificada se verá así:* `255.255.255.224`  
*(Nada más le cambias el octeto al final CUANDO ES CLASE C).*

La verdad, todas las clases trabajan con el mismo principio, solo que como bien sabes, empiezan en otros octetos por la forma en que están construidas. Ya sabes:
*   **Clase A (R.H.H.H):** Empiezas a robar desde el 2° octeto.
*   **Clase B (R.R.H.H):** Empiezas a robar desde el 3° octeto.
*   **Clase C (R.R.R.H):** Empiezas a robar desde el 4° octeto.

¡Y ya, jaja!

---
---

## 📜 PROPIEDAD INTELECTUAL Y DERECHOS DE AUTOR
Este documento y todo su contenido ha sido creado y documentado por **@Elhsup**. Queda totalmente prohibido su uso comercial sin consentimiento. Cualquier copia o distribución total o parcial de este material debe incluir obligatoriamente los créditos correspondientes enlazando a: [https://github.com/Elhsup](https://github.com/Elhsup)

## 👋 DESPEDIDA Y AGRADECIMIENTOS 👋

SEÑORAS Y SEÑORES, HEMOS TERMINADO. Gracias por estar acá. Un saludo a mi mamá, mi abuela, mi hermana, mi papá. Gracias por todo. Si pueden aporten money por ahí, tengo PayPal, me invitan un perro 🌭 o como quieran. ¡Me cansé, chao! ✌️


Personas que han revisado este documento:
Dios, yo, Mi IA (que la quiero mucho), Goku, Juan, Diego Maradona, La mortadela intergalactica, Firulais, Mishu mishu, Patroclo, El rey Boo y otros mas 
