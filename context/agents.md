# Agents Prompt - Simulador Micromouse Modular en Python

Este documento define el **prompt refinado** para guiar la creación del simulador modular de un **Micromouse** en Python.  
El objetivo es que el simulador sea la base del **taller intensivo de 6 módulos** de control y algoritmos aplicados a microrrobots.

---

## Prompt principal

Quiero que generes un **simulador modular en Python** para un micromouse en un laberinto estilo IEEE.  
El diseño debe estar **orientado a objetos**, escalable y permitir que los estudiantes puedan modificar y probar distintos algoritmos de control y exploración.  

### Requerimientos del simulador

1. **Estructura modular** con carpetas organizadas:
   - `core/` → clases base (Micromouse, Maze, Cell, Sensor, Actuator, RobotState).
   - `algorithms/` → implementación de algoritmos de control y exploración (PID, LQR, Kalman, BFS, DFS, Flood-Fill, etc.).
   - `simulation/` → motor de simulación (gestión del tiempo, física simple, actualización de estados).
   - `visualization/` → renderizado simple en 2D (usando `matplotlib` o `pygame`).
   - `utils/` → utilidades como carga/guardado de mapas, logs, métricas.
   - `examples/` → ejemplos de uso y pruebas rápidas.

2. **Clases principales**:
   - `Micromouse` → Representa al robot, maneja sensores, actuadores y controlador.
   - `Maze` → Representa el laberinto IEEE (16x16 o tamaño variable).
   - `Sensor` → Simulación de sensores básicos (pared, distancia).
   - `Controller` → Diferentes estrategias de control (PID, LQR, RL, etc.).
   - `Simulator` → Encargado de correr la simulación paso a paso.
   - `Visualizer` → Dibuja el estado actual del laberinto y el micromouse.

3. **Características clave**:
   - Modularidad: fácil cambiar entre algoritmos de control.
   - Dinámico: permitir cambiar forma del robot (circular, cuadrado, rectangular).
   - Parametrizable: configurar cantidad y tipo de sensores.
   - Compatible con experimentación de algoritmos avanzados (Kalman, RL, etc.).
   - Registro de métricas: tiempo, energía, pasos, exploración.

4. **Funcionalidades mínimas**:
   - Generación de laberintos aleatorios y definidos por archivo.
   - Movimiento básico del micromouse con colisiones simples.
   - Simulación paso a paso y en tiempo real.
   - Comparación de algoritmos (ej: PID vs. LQR vs. RL).
   - Guardado de resultados y gráficas.

### Estilo de implementación

- Lenguaje: **Python 3.10+**  
- Paradigma: **POO (Programación Orientada a Objetos)**  
- Librerías recomendadas: `numpy`, `pygame` o `matplotlib` (para visualización), `random`, `json` (para mapas).  
- Código documentado con **docstrings y comentarios claros**.  
- Seguir buenas prácticas de diseño: **SOLID y modularidad**.

---

## Ejemplo de interacción

1. Crear un micromouse con sensores básicos y controlador PID.
2. Cargar un laberinto IEEE de 16x16.
3. Ejecutar simulación con visualización en 2D.
4. Cambiar dinámicamente a un algoritmo Flood-Fill sin reescribir el simulador.
5. Guardar métricas en JSON para análisis posterior.

---

Este prompt será entregado al modelo en **Firebase Studio** para generar la primera versión del simulador, que luego se irá extendiendo en cada módulo del taller.
