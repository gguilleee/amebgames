# AMEBGAMES

Web de juegos diarios para jugar con amigos (Palabra del día, Trivial, Sudoku, Conexiones, Mastermind, Encadenados, Pasapalabra y Ahorcado).

- `public/` — versión online con Firebase (login con Google, guardado en la nube, grupos, amigos, duelos y ranking). Se publica en https://amebgames.web.app
- `firestore.rules` — reglas de la base de datos.
- `artifact/index.html` — versión sin servidor (todo en un solo archivo, guarda en el navegador).
- `GUIA.md` — guía de despliegue.

## Seguir en otro ordenador
```
git clone https://github.com/gguilleee/amebgames
cd amebgames
npx -y firebase-tools@13 login
npx -y firebase-tools@13 deploy --project amebgames
```
Para probar en local: `npx -y firebase-tools@13 serve` y abre http://localhost:5000
