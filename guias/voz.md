# Tu recepcionista de IA por voz, en una tarde

Un agente que atiende el teléfono, responde, toma los datos y agenda. Se arma con **Dograh**, una plataforma de código abierto para agentes de voz (alternativa a Vapi y Retell): https://github.com/dograh-hq/dograh (licencia BSD-2; esta guía es una explicación en español). Documentación oficial: https://docs.dograh.com

**Cuánto cuesta:** Dograh es gratis si lo instalás vos. Para recibir llamadas reales necesitás un número (Twilio, Vonage, Telnyx u otro), que se paga aparte. Para probar no hace falta: se habla desde el navegador.

---

## Paso 1 · Lo que necesitás
- **Docker Desktop** instalado y abierto: https://www.docker.com/products/docker-desktop
- Una compu con espacio (la primera vez baja varias imágenes, tarda 2–3 minutos).
- Si no querés instalar nada: existe la versión en la nube de Dograh (https://www.dograh.com).

## Paso 2 · Instalarlo
**Opción fácil (con Claude Code):**
```text
/plugin marketplace add dograh-hq/dograh-plugins
/plugin install dograh@dograh
```
Abrí una sesión nueva y pedile: *«set up Dograh»*. El agente detecta tu sistema, instala y verifica.

**Opción manual:** en la terminal (un solo comando, del README oficial):
```bash
curl -o docker-compose.yaml https://raw.githubusercontent.com/dograh-hq/dograh/main/docker-compose.yaml && curl -o start_docker.sh https://raw.githubusercontent.com/dograh-hq/dograh/main/scripts/start_docker.sh && chmod +x start_docker.sh && ./start_docker.sh
```
Si no querés enviar datos de uso anónimos, antes corré `export ENABLE_TELEMETRY=false`.

## Paso 3 · Tu primera recepcionista
1. Abrí **http://localhost:3010** y creá tu cuenta.
2. Elegí **Inbound** (recibe llamadas), ponele nombre (p. ej. *Recepción Plomería*) y describí el uso en pocas palabras.
3. Tocá **Test Agent** y hablale con **Test Audio** desde el navegador (o probá rápido con **Test Chat**).

No hacen falta claves: viene con su propio modelo de voz y de texto. Después podés poner los tuyos.

## Paso 4 · El guion (copiá y adaptá)
Pegalo en las instrucciones del agente, cambiando lo que está entre corchetes:

> Sos la recepcionista de [NOMBRE DEL NEGOCIO], [rubro] en [zona]. Hablás en español rioplatense, amable y breve.
> Objetivo: entender qué necesita la persona y agendarle un turno.
> 1. Saludá: «Gracias por llamar a [NOMBRE]. ¿En qué lo puedo ayudar?»
> 2. Si es urgente, ofrecé el primer horario libre de hoy; si no, dos opciones.
> 3. Pedí nombre, teléfono y dirección (o lo que haga falta para el turno).
> 4. Confirmá en voz alta día, hora y dirección.
> 5. Si pregunta precios: [precios o «el técnico le confirma el precio antes de empezar»].
> 6. Si pide hablar con una persona o es algo que no sabés, decí que lo llaman en el día y tomá sus datos.
> Nunca prometas algo que no está en estas instrucciones.

## Paso 5 · Probala como en el video
Llamala desde Test Audio con una urgencia («¡se me explotó el inodoro!») y una consulta normal. Ajustá el guion hasta que agende bien las dos.

## Paso 6 · Conectar un número real
En Dograh conectás el proveedor de telefonía (Twilio, Vonage, Telnyx, Plivo, etc.) y le asignás el número al agente. Seguí la guía oficial: https://docs.dograh.com
Antes de ponerlo en un negocio real, revisá: que avise que es un asistente, qué datos guarda y quién los ve.

## Si querés venderla a negocios
1. Elegí un rubro (plomeros, dentistas, peluquerías).
2. Armá una recepcionista para un negocio real de ese rubro y grabá una llamada de prueba.
3. Mandale la grabación al dueño: «así atendería su negocio a las 11 de la noche».
La demo vende más que cualquier explicación.

## ¿La querés para tu negocio?
La armamos conectada a tu agenda y tu número, con tu forma de atender. Escribí **NEGOCIO** por privado o reservá una llamada corta: https://calendly.com/maneyro-achievements/30min?utm_source=instagram&utm_medium=dm&utm_campaign=recursos
