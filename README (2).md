# Pádel & Birras 🎾🍺

Liga informal de pádel para el grupo: La Callejada (la app monta los partidos con las parejas o los jugadores que pongáis), resultados con foto, ranking individual y por parejas, el tercer set cervecero, rondas que se deben y banquillo de candidatos.

La app entera está en `index.html` y guarda los datos en Firebase (Firestore con sesión anónima). No necesita instalar nada ni compilar.

## Archivos

| Archivo | Para qué |
|---|---|
| `index.html` | La app completa. |
| `firestore.rules` | Reglas de seguridad para pegar en la consola de Firebase. |
| `README.md` | Este archivo. |

## Puesta en marcha (una sola vez)

### 1. Firebase
1. **Authentication → Método de acceso:** activa **Anónimo**.
2. **Firestore Database:** créala si no existe (modo producción, región `eur3`).
3. **Firestore → Reglas:** borra lo que haya, pega el contenido de `firestore.rules` y pulsa **Publicar**.
4. **Authentication → Configuración → Dominios autorizados:** añade `TU-USUARIO.github.io`. Sin esto, la app no puede iniciar sesión desde GitHub Pages.

### 2. GitHub Pages
1. Crea un repositorio (por ejemplo, `padel-y-birras`) y sube estos archivos.
2. **Settings → Pages → Build and deployment:** Source = *Deploy from a branch*, Branch = `main` y carpeta `/ (root)`. Guarda.
3. Al cabo de un minuto la app estará en `https://TU-USUARIO.github.io/padel-y-birras/`.

### 3. Al grupo
- Pasa el enlace por WhatsApp.
- En el móvil, "Añadir a pantalla de inicio" la deja como una app más.
- Cada uno elige quién es en el selector **"Soy…"** de arriba.

## Reglas de la liga

- Victoria: 3 puntos. Derrota: 1 punto, por presentarte.
- Siempre hay tercer set (o cuarto): cervezas. No puntúa, lo ganamos todos.
- Quien no juega en un mes natural debe una ronda. El mes en que te das de alta no cuenta.
- Quien pasa 3 meses sin jugar queda fuera del grupo y su plaza pasa al banquillo.

## Notas

- Cualquiera que tenga el enlace puede apuntar datos. Para un grupo de amigos es suficiente: no compartas el enlace fuera.
- Las fotos se guardan comprimidas dentro de Firestore, así que no hace falta Firebase Storage ni el plan de pago. El plan gratuito (1 GiB) da para miles de partidos.
- La clave `apiKey` que aparece en `index.html` es pública por diseño en Firebase. La seguridad la ponen las reglas de Firestore.
