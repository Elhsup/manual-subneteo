## 🏠 TÓPICO 4: LA RED Y EL HOSTTTTT WASAAAAAAAAAAAAA 🏠

Si tienes la IP: `192.168.10.5`
* `192.168.10.` ➡️ **RED**
* `.5` ➡️ **HOST**

Tenemos la IP. En la IP tenemos la red y el host. La red es para comunicarse con el mundo y el host con los dispositivos de tu casa. Hablaremos más adelante de eso.

* **La Red:** Es cómo los dispositivos se conectan al mundo, por decirlo así, el cómo tu router se conecta al mundo por medio de tu distribuidor de internet (que si Inter, Thundernet, etc., etc.). Entonces, en nuestras casas todos tenemos la IP más común: `192.168.0.1`.

Recordemos que hay varias clases y tipos de red:

### 🏙️ << Redes Públicas >>
* **Clase A:** `1.0.0.0` hasta `126.255.255.255` *(quitando el bloque del 10).*
* **Clase B:** `128.0.0.0` hasta `191.255.255.255` *(quitando el pedacito de la 172.16 a la 172.31).*
* **Clase C:** `192.0.0.0` hasta `223.255.255.255` *(quitando el bloque 192.168.0).* ¡Pa la casa!

### 🔄 << Esta se salta las reglas >>
Pilla aquí: la **<127>** no está disponible porque `127.0.0.1` (o localhost) no es ni pública ni privada, porque está reservada exclusivamente para el bucle local (**loopback**). Su única función es permitir que tu dispositivo se comunique consigo mismo, o sea, mandas un dato y lo recibes.

### 🔐 << Redes Privadas >>
* **Clase A:** Desde `10.0.0.0` hasta `10.255.255.255`
* **Clase B:** Desde `172.16.0.0` hasta `172.31.255.255`
* **Clase C:** Desde `192.168.0.0` hasta `192.168.255.255`

---

## 📊 TÓPICO 5: EXPLICACIÓN DE LAS CLASES DE REDES 📊

* **En la Clase A (`1.0.0.0`):** El primer octeto de izquierda a derecha es red y esto no cambia (el 1). Es para empresas grandes. Entonces en la A tendrías RED y los demás son HOSTS. Es decir, ¡muchisiiiiimos dispositivos pa conectarte!
    * *Gráficamente:* `RED . HOST . HOST . HOST`
* **En la Clase B (`172.16.0.0`):** El primer y segundo octeto de izquierda a derecha es red y esto no cambia (el 172.16). Para empresas medianas. En este caso es lo mismo que la A, pero ya no tienes tantos hosts; sin embargo, todavía te quedan muchísimas.
    * *Gráficamente:* `RED . RED . HOST . HOST`
* **En la Clase C (`192.168.0.0`):** El primer, segundo y tercer octeto de izquierda a derecha es red y esto no cambia (el 192.168.0). Este sirve pa la casa porque son poquitos hosts.
    * *Gráficamente:* `RED . RED . RED . HOST`

---

## 💻 TÓPICO 6: EL HOSTTTTTTTTTTTTTTTTTTT (La Casa) 💻

Identifica al dispositivo específico dentro de esa calle (tu PC, el teléfono, la impresora). Este número **tiene que ser único** en esa calle; si clonas un Host, da conflicto de IP. 

Creo que se entiende, ya que colócate que el `192.168.0.0` es la calle por decirlo así, y tu dispositivo es `192.168.0.1`. Lo único que cambió en la IP es el host, o sea, ese 1. Ejemplo: que en tu compu está asignada así y tu teléfono también se conecte a la red, ejemplo, entonces sería `192.168.0.2` y tu impresora `192.168.0.3` y así sucesivamente. Ese número te indica si está conectado y es el host.

### 💥 El problema de la Clase C (La muy desgraciada)
Acá pasa algo con esta red ya que es un poquito diferente. Como verás, no tenemos tantos hosts acá, solo **254**. Lo que hacemos es agarrar y cambiar el número de un octeto de red, el tercero para ser específico, y tenemos 254 hosts más. ¿Por qué hacemos esto? Para tener más espacios para más hosts (que son dispositivos), pero la desventaja es que está totalmente aislada de la otra red.
* *Red 1:* `192.168.0.1` ➡️ Por acá pasa una información.
* *Red 2:* `192.168.1.1` ➡️ Por acá pasa otra. *(No se comunican entre sí).*

¡Pero de esta "desventaja" sale otra ventaja! Y es que están aisladas y no se comparten información. Se puede tener una red para algo y otra para otro algo, o sea, una red para los profes y otra para los estudiantes. No se pasa información que no se quiere. Además, si se quiere que se comuniquen entre sí, tenemos los **routers** que los podemos configurar, tonce desventaja como tal no hay `:b`. *(Esto también lo podemos hacer para las otras redes y sirven como control y más cositas pa las redes).*

---

## 🧠 TÓPICO 7: LO QUE APRENDÍ EL 11/6/2026 (Red, Host y Broadcast brrrrr) 🧠

### 🤔 ¿Cómo se ve la red en una IP y qué vendría siendo?
La red se ve así:
* `10.0.0.0` , `11.0.0.0` , `12.0.0.0` ➡️ Es una red.
* `172.18.0.0` , `172.19.0.0` , `173.1.0.0` ➡️ Es una red.
* `192.168.0.0` - `192.168.1.0` - `195.163.9.0` ➡️ Es una red.

#### 🅰️ << En Clase A >>
El primer octeto (los primeros 8 bits) define la identidad de la red. Es decir, que si agarramos `10.0.0.0` es una identidad de red. La red `11.0.0.0` es otra identidad de red totalmente diferente. ¿Por qué? 

Porque existe la **máscara de subred** (hablaré más adelante de la subred y la máscara) y esta tiene como parámetro o criterio (por medio de cómo está configurada gracias a las compuertas lógicas OR, AND, etc.) que cuando una red tenga el primer octeto diferente al otro, no se puedan comunicar entre sí. O sea: `10.0.0.0` y `11.0.0.0`. Claro, la máquina no funciona así, se guía por medio del binario:
* `00001010` = `10.0.0.0`
* `00001011` = `11.0.0.0`

> ✨ *O sea, más sencillo: acá lo importante es que si no están en cero los 3 últimos números, no es red.*

*(Sin embargo, si no tuvieran la máscara de subred, sí se podrían comunicar entre sí como si todo fueran hosts, y se pueden comunicar red con red sin ningún problema retóricamente, ya que se usa la subred para más control y que no se dañen las computadoras porque evita que haya demasiada información de una sola vez. Sin embargo, la forma en que se conecta una red con otra es por medio del router).*

#### 🔄 ¿Cómo se hace el cambio?
La red `10.0.0.0` es una identidad de red. El número `11.0.0.0` es otra identidad de red totalmente diferente. O sea, son redes diferentes. ¿Cómo se hace este cambio o cómo llegamos del `10.0.0.0` al `11.0.0.0`? **Llenando toda la red de hosts**, o sea:

Por el tamaño y la capacidad de los bits, en este caso son 8 agrupados en 4 grupos que cuentan con 256 combinaciones, pero podemos utilizar 255. En este caso, si ves en la red, empezamos a contar de los hosts de derecha a izquierda, que los números se van llenando poco a poco. O sea: `10.0.0.0` ➡️ `10.0.0.1` ➡️ `10.0.0.2`. Técnicamente estás sumando. Si le sumas 1 a `10.0.0.2` te va a dar `1 + 10.0.0.2 = 10.0.0.3` hasta llegar a los `10.255.255.255` y si le sumamos uno más nos daráaaaaaaaaaa **`11.0.0.0`**.

#### 🅱️ << El 172.16 ahí es red >>
Lo sabemos porque en la **Clase B** agarramos los 2 octetos y el sistema tiene de forma automática de saber que a partir de 128 todo es diferente a partir del 128. No necesita leer toda la IP ni adivinar, o sea, es automático que sabe el cambio de la clase. No tendríamos que hacer nada en ese caso, solo aprendernos cuándo hay un cambio de clase y de ahí empieza a contar el primer y segundo octeto. Además, le basta con ver que el primer bit de la izquierda se encendió en 1.

* El número 127 se escribe: `01111111` *(El primer bit de la izquierda está apagado en 0).*
* El número 128 se escribe: `10000000` *(El primer bit de la izquierda se enciende en 1).*

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
<br>

* [📚 Volver al Índice](README.md)
* [⬅️ Página anterior](01_conceptos_basicos.md)
* [➡️ Siguiente página](03_mascaras_subredes.md)
