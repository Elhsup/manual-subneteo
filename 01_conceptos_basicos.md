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

* Cada grupo de 8 bits se llama **Octeto**.
* Cuando tú escribes 255, la computadora ve `11111111` (8 unos encendidos). *<-- Eso creo que lo explicaré más adelante...*

#### 🌎 Ejemplo de cómo se ve:
Una IP sería = `255.255.255.255` *(Ojo: esto no es una red, es la dirección de Limited Broadcast, un broadcast universal).* Entonces serían los 4 grupos, que son los 4 "255" de arriba. El primer 255 es un grupo y así p. 
* Si juntas esos 4 grupos, son **32 bits**.
* En bytes, me dan **4 bytes** pa k entiendas mucho más mejor...

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
<br>

* [📚 Volver al Índice](README.md)
* [➡️ Siguiente página](02_estructura_redes.md)
