## 🪓 TÓPICO 9: SUBNETINGGGGGGG ACA VAMOS... 🪓
*🤪* ¡YA VAMOS A TERMINAR, no se preocupen! Ahora a lo que todos vinieron: el subneteo.

> 🚨 **¡¡Si de verdad quieres entender, lee todo lo de arriba porque va a estar bastante complicado no saberte nada, campeón o campeona, vos podéis!!**

Acá la verdad va a estar algo difícil. ¿Por dónde empezamos?

### ❓ ¿QUÉ ES EL SUBNETEO?
El subneteo en sí no modifica la clase como tal ni la hace más grande, solo recorta o crea muros para que cada red sea diferente. Es como un edificio con secciones. Al crear 2 subredes o colocar 1 bit en host, creas 2 subredes nuevas. Es como cuando cambias la máscara de una clase, solo que agregándole más secciones. Mira este ejemplo:

¿Recuerdas desde dónde empieza una red?
* `192.168.0.0` = **Red**
* Desde `192.168.0.1` hasta `192.168.0.254` = Es la cantidad de **hosts** que tiene.
* `192.168.0.255` = Es el **broadcast**.
* `192.168.1.0` = Esto es un **cambio de red**, pero sigue en la misma Clase C.

Ahora tengamos el ejemplo de si partimos a la mitad esa red `192.168.0.0`. No vamos a tocar el `192.168.1.0`, solo `192.168.0.0`:

* 🧱 **Primera Mitad (Subred A):** Esta sección ocupa los primeros 128 números (del 0 al 127).
    * *IP de Red (ID):* `192.168.0.0` (Identifica a esta primera mitad).
    * *Primera IP utilizable:* `192.168.0.1` (Para tu primera computadora).
    * *Última IP utilizable:* `192.168.0.126` (Para tu última computadora).
    * *IP de Broadcast:* `192.168.0.127` (El límite donde choca el muro).
* 🧱 **Segunda Mitad (Subred B):** Esta sección ocupa los siguientes 128 números (del 128 al 255).
    * *IP de Red (ID):* `192.168.0.128` (Identifica a esta segunda mitad).
    * *Primera IP utilizable:* `192.168.0.129` (Para la primera computadora de este lado).
    * *Última IP utilizable:* `192.168.0.254` (Para la última computadora de este lado).
    * *IP de Broadcast:* `192.168.0.255` (El final absoluto de esta red).

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
* **2:** Porque es base 2 el binario.
* **^:** Potencia, porque así es como trabaja la suma de los octetos.
* **n:** Es una variable. Eso quiere decir que no sabemos cuál es el número que debemos colocar. Debemos colocar en la potencia un número que dé un resultado similar o mayor a la cantidad de subredes que me piden. O sea, $2^3$ porque $2^3 = 8$. Ahora con esto sabemos que debemos robar 3 bits y se convertirá en 8 subredes, y los 3 bits encendidos en decimal suman 224, que esa será nuestra nueva máscara `:)`.

O sea, reemplazamos la `n` por el número 3. Fórmula: $2^n$ -> Quedaría: **$2^3$**

#### 💡 Truquiño de Elhsup `>:D`:
También podemos usar la tabla... Vamos a usar potencias, ¿verdad? En este caso podemos ver el resultado de las potencias que es la tabla:

* **Posiciones de los bits (orden en que te robas los bits y los sumaras):** `1 | 2 | 3 | 4 | 5 | 6 | 7 | 8`
* **Tabla de los bits (valores decimales):** `128 + 64 + 32 + 16 + 8 + 4 + 2 + 1`
* **Potencia de los bits:** `2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0`

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
* **2:** Porque es base 2 el binario.
* **^:** Potencia, porque así es como trabaja la suma de los octetos.
* **h (la h representa al host):** También es una variable. Acá colocaremos el número de ceros (hosts) que nos quedan. Ejemplo con el caso de arriba: robamos 3 bits. Al hacer ese robo, ¿cuántos ceros nos quedan?
    * *Inicio:* `00000000` (Tenemos 8 ceros).
    * *Con el robo de bits:* `11100000` (Nos quedan 5 ceros). Ese 5 va a ser lo que colocaremos en la `h`.

$$2^5 = 32$$
Tendremos un espacio de **32 direcciones en total**, contando red y broadcast `:b`. Oe, ¿pero tú quieres saber solo los hosts? Pues réstale 2 a tu resultado y ya, jajaja. *(Explicación abajo).*

---

### 3️⃣ Fórmula para calcular los Hosts Utilizables (IPs para equipos)
¡ESTA FORMULA! Te dice cuántas computadoras reales puedes conectar en cada subred, cobrando el "impuesto" de la dirección de red y el broadcast.

> **Fórmula:** $$2^h - 2$$
*(Es la misma fórmula de arriba, nada más réstale 2 al resultado final y ya).* Cabe recalcar que es el resultado menos 2.

* *Ejemplo:* Usando el caso anterior de 5 ceros ($2^5 = 32$), le restas 2, el resultado es que puedes conectar exactamente **30 computadoras reales**.
* *¿Por qué?* Ahí estás es restando la red en sí y el broadcast. Eso no son hosts, no es algo utilizable para un dispositivo ya que la red le indica al router dónde comienza todo y el broadcast es el megáfono.

---

### 4️⃣ Fórmula del "Salto Mágico" (En Decimal)
Si no quieres pasar todo a binario para saber dónde empieza la siguiente subred, usas esta resta matemática simple en decimal:

> **Fórmula:** $$\text{Tamaño del salto} = 256 - \text{El número de la nueva máscara}$$
*(O sea, la que modificaste p, en este caso el último octeto porque es Clase C).*

Tú puedes robar la cantidad de bits que quieras y pasar por encima de 1, 2 o hasta 3 octetos si es necesario. Pero al momento de calcular el salto en decimal, tu mirada debe ir directo al **último octeto donde pusiste un número diferente a 255 y a 0**. Ese es tu "octeto de frontera" y ahí es donde haces la resta.

* Si tu nueva máscara calculada termina en `.192`, haces la operation `(256 - 192)`. El resultado es **64**. Tus subredes saltarán de 64 en 64 (ej. `.0`, `.64`, `.128`, `.192`).
* Para nuestro ejemplo sería: `256 - 224 = 32`. Ejemplo: empieza en 0 y termina en 31; la otra empieza en 32 y termina en 63; la otra empieza en 64... Si te dio 32, súmale otros 32 y ahí te da el salto. Ve sumándole 32, pendiente de no confundirte ahí; los resultados son donde empieza cada red.

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
* *Último octeto de izquierda a derecha (el 4° octeto p):* `11100000`

Ahora calculamos el valor decimal de esa máscara usando nuestra tabla del octeto:
* **Posiciones de los bits:** `1 | 2 | 3 | 4 | 5 | 6 | 7 | 8`
* **Tabla de los bits:** `128 + 64 + 32 + 16 + 8 + 4 + 2 + 1`

* El primer bit vale **128**.
* Sumando los 2 bits valen **192** -> ($128 + 64 = 192$).
* Sumando los 3 bits valen **224** -> ($128 + 64 + 32 = 224$).

Tu nueva máscara decimal será: **`255.255.255.224`** En notación corta (CIDR): como la máscara original tenía 24 unos y le sumamos 3 nuevos, ahora es **`/27`**.

#### 🔄 Cómo cambia visualmente:
* *La máscara original así:* `255.255.255.0`
* *La máscara modificada se verá así:* `255.255.255.224`  
*(Nada más le cambias el octeto al final CUANDO ES CLASE C).*

La verdad, todas las clases trabajan con el mismo principio, solo que como bien sabes, empiezan en otros octetos por la forma en que están construidas. Ya sabes:
* **Clase A (R.H.H.H):** Empiezas a robar desde el 2° octeto.
* **Clase B (R.R.H.H):** Empiezas a robar desde el 3° octeto.
* **Clase C (R.R.R.H):** Empiezas a robar desde el 4° octeto.

¡Y ya, jaja!

---

## 👋 DESPEDIDA Y AGRADECIMIENTOS 👋

SEÑORAS Y SEÑORES, HEMOS TERMINADO. Gracias por estar acá. Un salud

---
<br>

* [📚 Volver al Índice](README.md)
* [⬅️ Página anterior](03_mascaras_subredes.md)
