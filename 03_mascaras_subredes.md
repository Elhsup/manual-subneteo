## 😷 TÓPICO 8: MÁSCARA Y SUBRED (Adivina adivinador) 😷

Verán, en este caso les hablaré de la máscara. Arriba me traté de enfocar en todo sin necesidad de meter la máscara porque necesitábamos lo básico. Ahora sí vamos con la mascariña...

* **La Máscara es la herramienta de corte:** Es ese filtro matemático de unos y ceros que le instalas a la tarjeta de red. O sea, la máscara está **HECHA PARA CREAR LAS SUBREDES**.
* **La Subred es el territorio creado:** Es el vecindario de IPs que nace después de aplicar ese corte con la máscara, tipo cambia el tamaño de la red. En vez de 16,777,214 hosts, solo utilizarás los 255. Pero reales y usables son 254 hosts de la Clase C. O sea, el dónde empieza y termina la red. **OJO: ESCRIBI LA RED, NO HOST. LA SUBRED SE CREA GRACIAS A LA MÁSCARA**.

No sé si se acuerdan de que anteriormente les dije que las clases de las IP eran muy grandes y la única que era muy poquita era la C (si hablamos en términos privados, obvio). Entonces, al no haber un tipo estándar para que las empresas o personas tengan suficientes IPs o que no tuvieran tantas IPs innecesarias, se volvió un problema (y la empresa que creó esas IPs pues... se le estaban acabando, k peo chico).

* **Antes (Sin máscara):** Si tenías la red `10.0.0.0`, estabas atrapado en un único vecindario gigante de 16 millones de hosts. No podías dividirlo. Si intentabas usar `10.10.0.0`, como aprendiste al principio, el sistema se confundía y lo veía como un simple dispositivo más, no como otra red.
* **¡Y PUM! Se creó la máscara:** Para poder dividir las direcciones IP y tener los hosts que necesitemos, ni más ni menos. Esto se hace porque se configura en la tarjeta de red, al mismo tiempo que la dirección IP -> (eso lo hacemos nosotros). Tipo: a partir de ahora, el primer octeto ya no define el tamaño de la red. Tú puedes elegir la IP que quieras (así empiece por 10, por 172 o por 192) y, usando la máscara, podrás cortar los bits exactamente donde te dé la gana.
* **Después (Con máscara):** Gracias a que se inventó la máscara, pudiste agarrar ese bloque gigante del `10.0.0.0` y, aplicando máscaras como `255.255.255.0` (`/24`) —mira que acá estamos usando la máscara de la red Clase C—, pudiste "picar" ese territorio en miles de subredes independientes (como la `10.1.1.0`, la `10.1.2.0`, etc. Checa, ¡está funcionando como la red Clase C WAJAJAJA de locosh!).

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
* **Por qué se usa 255:** El número 255 representa un octeto que tiene sus 8 bits completamente encendidos en binario (`11111111`). Para el hardware, ver un 255 es una orden física que significa: *"Este octeto completo está congelado y blindado, es el nombre de la red, ningún host puede tocarlo"*.
* **Por qué se usa 0:** El número 0 representa un octeto con sus 8 bits apagados (`00000000`). Para el hardware significa: *"Este octeto está completamente libre para asignar números de casa (hosts)"*.

El colocar la máscara es la intervención para llegar a la subred, pero nos falta algo importante que es el **Subnetting**, que son los procesos lógicos y matemáticos para calcular cómo se verá la red de ahí. Lo hacemos por medio de la máscara y dará el resultado de la subred.

---
<br>

* [📚 Volver al Índice](README.md)
* [⬅️ Página anterior](02_estructura_redes.md)
* [➡️ Siguiente página](04_subnetting_practico.md)
