# Tamagotchi — Kamaboko Adoptame

Juego de mascotas virtuales por consola, escrito en Java. El jugador adopta un perro,
un gato o un pájaro, y cada mascota reacciona distinto a las mismas acciones.

## Mecánica

Cada mascota tiene tres estadísticas entre 0 y 100: **hambre**, **energía** y
**felicidad**. Se dibujan como barras ASCII en la consola.

Acciones disponibles:

- **Alimentar** — baja el hambre y sube un poco la felicidad.
- **Jugar** — sube la felicidad, gasta energía y da hambre.
- **Dormir** — restaura la energía completa.
- **Adrenalina** — subida fuerte de felicidad a cambio de energía.
- **Envejecer** — desgaste pasivo de las tres estadísticas.

Cada especie responde distinto: el gato come atún, el perro juega a la pelota, el
pájaro canta.

## Diseño

- `InterfaceMascota` define el contrato y los límites (`MIN_STAT`, `MAX_STAT`).
- `Mascota` es una clase abstracta que implementa la interfaz y centraliza las
  estadísticas y la barra de progreso.
- `Perro`, `Gato` y `Pajaro` heredan y sobrescriben cada acción con su propio
  comportamiento.
- `Duenio` administra la lista de mascotas y la interacción por consola.

## Ejecutar

Con NetBeans: abrir el proyecto y ejecutar `Main.java`.

Por consola:

```bash
javac -d out src/main/*.java src/modelo/*.java
java -cp out main.Main
```

## Estructura

```
src/
├── main/
│   └── Main.java
└── modelo/
    ├── Duenio.java
    ├── InterfaceMascota.java
    ├── Mascota.java
    ├── Perro.java
    ├── Gato.java
    └── Pajaro.java
```
