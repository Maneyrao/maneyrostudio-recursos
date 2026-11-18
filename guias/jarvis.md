# Tu propio Jarvis en 30 minutos

Un asistente al que le hablás («Hey Jarvis») y que hace cosas con tus herramientas, con una interfaz holográfica en el navegador. El proyecto es de código abierto: https://github.com/adewaskar/jarvis (licencia MIT, de su autor Adewaskar; esta guía es una explicación en español).

**Cuánto cuesta:** el proyecto es gratis. El «cerebro» es Claude Code, así que usa **tu cuenta de Claude** (no hacen falta claves de API ni otro abono). La voz de ElevenLabs es opcional.

---

## Paso 1 · Lo que necesitás (una sola vez)
1. **Claude Code** instalado y con tu cuenta iniciada. Guía oficial: https://docs.claude.com/en/docs/claude-code. Abrí la terminal, escribí `claude` y completá el inicio de sesión.
2. **Node.js 20 o más nuevo**: https://nodejs.org (instalador de un clic).
3. **Google Chrome** (o Edge).

## Paso 2 · Que Claude lo instale por vos
Abrí Claude Code en una carpeta vacía y pegale esto:

> Cloná https://github.com/adewaskar/jarvis, instalalo en mi máquina siguiendo su README (npm install) y corré `npm run setup` para comprobar que tengo todo. Explicame en criollo si falta algo.

Si preferís hacerlo a mano:
```bash
git clone https://github.com/adewaskar/jarvis
cd jarvis
npm install
npm run setup
```

## Paso 3 · Encenderlo
```bash
npm start
```
Abrí **http://localhost:5173 en una ventana normal de Chrome** (no en una vista previa dentro de un editor: ahí el micrófono no funciona). Tocá **INITIALISE**, aceptá el micrófono y decí **«Hey Jarvis»**.

Probá: *«¿Qué está pasando con la IA esta semana?»*

## Paso 4 · Una voz mejor (opcional)
Con una clave de ElevenLabs (el plan gratis alcanza para probar), Jarvis habla y escucha mejor. Antes de encenderlo:
```bash
export ELEVENLABS_API_KEY=tu_clave
npm start
```
Sin clave funciona igual, con la voz del navegador.

## Paso 5 · Conectale tus herramientas
Jarvis usa las mismas conexiones (MCP) que tengas en Claude Code: búsqueda web, navegador, generación de imágenes, etc.
- Tu **mail y calendario** conectados en tu cuenta de claude.ai entran sólo si lo encendés así:
  ```bash
  JARVIS_ACCOUNT_CONNECTORS=1 npm start
  ```
- Para elegir qué conexiones puede usar: `JARVIS_MCP_SERVERS=nombre1,nombre2`.

## Paso 6 · Límites (leé esto antes de darle acceso a todo)
Jarvis arranca en **modo sólo lectura**: busca, consulta y genera, pero **no envía, no borra, no paga, no instala**. Está bien que sea así.
- Para permitirle acciones (mandar mensajes, manejar el navegador o el celular) existe `npm start -- --writes`. **No lo actives** hasta tener claro qué puede tocar.
- Dale sólo las conexiones que necesita, una por tarea.
- Nunca le conectes la cuenta del banco ni la de pagos.
- Probalo primero con datos de prueba.
- Antes de darle permisos de escritura, hacé una copia de seguridad de lo que pueda tocar.

## Paso 7 · Usarlo desde el celular
El proyecto corre en tu compu. Para hablarle desde el celular hace falta un canal (Telegram, WhatsApp) conectado a tu asistente: no viene armado en este proyecto.

---

## Si algo falla
- **No me escucha / no lo escucho:** tocá **D** para ver el panel de diagnóstico. Casi siempre es porque se abrió en una vista previa y no en Chrome.
- **Error de Node:** revisá que tengas Node 20+ (`node -v`).
- **No responde:** comprobá que `claude` funcione solo en la terminal (sesión iniciada).

## ¿No querés armarlo vos?
Lo armamos para tu negocio: conectado a tus herramientas, con tu información (precios, clientes, cómo hablás) y con límites para que no haga nada sin tu OK. Escribí **NEGOCIO** por privado o reservá una llamada corta: https://calendly.com/maneyro-achievements/30min?utm_source=instagram&utm_medium=dm&utm_campaign=recursos
