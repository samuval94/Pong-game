Claude


Readme · MD
# Pong en Jack — Organización de Computadores
 
Videojuego retro **Pong** desarrollado en **Jack**, el lenguaje orientado a objetos de Nand2Tetris, para el reto de Organización de Computadores (Universidad EAFIT, Ingeniería de Sistemas).
 
> **Estado actual: Tercer Parcial (Hito 1) — Tablero y Objetos Gráficos.**
> En este hito se dibuja la cancha (red central), los dos bates, la pelota y el marcador. La dinámica completa (movimiento de la pelota, colisiones, puntaje, Game Over y reinicio) corresponde al Proyecto Final.
 
## Integrantes
 
- Samuel Valencia Montoya
- Matias Zapata Rojas
- Jeronimo Jaramillo Agudelo
## Enlaces
 
- Repositorio: https://github.com/samuval94/Pong-game
## Requisitos
 
- Suite oficial de **Nand2Tetris** (incluye `JackCompiler` y el **VM Emulator**).
## Estructura del proyecto
 
| Archivo | Descripción |
| --- | --- |
| `Main.jack` | Punto de entrada: crea el objeto `Juego` y lo ejecuta |
| `Juego.jack` | Agrupa todas las entidades y contiene el ciclo principal con la lectura de teclado |
| `Tablero.jack` | Dibuja la red central de la cancha |
| `Bate.jack` | Raqueta de un jugador (dibujar, borrar y mover) |
| `Pelota.jack` | Pelota del juego (dibujar y borrar) |
| `Marcador.jack` | Muestra el puntaje de ambos jugadores con `Output` |
 
Al compilar se genera un archivo `.vm` por cada clase, en la misma carpeta.
 
## Compilación y ejecución
 
1. Descarga la suite de Nand2Tetris y ubica la carpeta `tools`.
2. Compila la carpeta del proyecto con el compilador de Jack:
   - Windows: `JackCompiler.bat <ruta-a-la-carpeta-del-proyecto>`
   - Linux / macOS: `JackCompiler.sh <ruta-a-la-carpeta-del-proyecto>`
   También puedes abrir `JackCompiler` y seleccionar la carpeta desde su interfaz.
3. Abre el **VM Emulator** (`VMEmulator`).
4. Carga la carpeta del proyecto con **File → Load Program**.
5. Selecciona **Animate: No animation** para mayor fluidez.
6. Presiona **Run**.
Deberías ver la cancha con la red central, un bate a cada lado, la pelota en el centro y el marcador en `0` y `0`.
 
## Controles
 
| Jugador | Subir | Bajar |
| --- | --- | --- |
| Izquierdo | `W` | `S` |
| Derecho | `↑` (flecha arriba) | `↓` (flecha abajo) |
 
Los bates se mueven de 2 en 2 píxeles y no pueden salirse de la pantalla.
 
## Diseño de la pantalla (512×256)
 
| Elemento | Posición | Tamaño |
| --- | --- | --- |
| Red central | x = 255–256 | Segmentos de 8 px cada 16 px |
| Bate izquierdo | (0, 96) | 9×62 px |
| Bate derecho | (503, 96) | 9×62 px |
| Pelota | (252, 124) | 8×8 px |
| Marcador | Fila 1, columnas 28 y 35 | Texto de `Output` |
 
## Arquitectura
 
```
Main
 └── Juego
      ├── Tablero
      ├── Bate (jugador izquierdo)
      ├── Bate (jugador derecho)
      ├── Pelota
      └── Marcador
```
 
Cada entidad gráfica es una clase independiente con su constructor y sus métodos de renderizado; `Juego` solo coordina a los objetos.
 
## Próximos pasos (Proyecto Final)
 
- Movimiento de la pelota y game loop sincronizado.
- Colisiones con los bates y los límites del tablero.
- Puntaje dinámico y HUD en tiempo real.
- Pantalla de inicio, Game Over y reinicio de partida.
- Liberación explícita de memoria con `dispose()`.
## Créditos
 
Desarrollado por Samuel Valencia Montoya, Matias Zapata Rojas y Jeronimo Jaramillo Agudelo.
Curso: Organización de Computadores — Universidad EAFIT, 2026.
 

Claude finished the response
