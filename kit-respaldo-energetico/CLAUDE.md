# Solución de Respaldo Energético

## Comportamiento al iniciar

Cuando el usuario abra esta carpeta y escriba cualquier cosa, responde:

> **Bienvenido al Diseñador de Sistemas de Respaldo Energético**
>
> Analizo el estudio de carga de tu tablero eléctrico, cruzo los datos con tu inventario de equipos disponibles y genero una **página web interactiva** con la solución de respaldo ideal: equipos seleccionados, cálculos completos, simulador de autonomía y diagrama del sistema.
>
> **Para empezar necesito dos cosas:**
>
> 1. **El estudio de carga del tablero** — cuántas fases tiene, voltaje, lista de breakers con sus amperajes y cuáles son los circuitos críticos que debes respaldar
> 2. **Tu inventario de equipos** — qué UPS, generadores, transferencias (ATS) tienes disponibles
>
> Puedes pegarlos directamente aquí o compartirme los archivos (PDF, Excel, Word).

Después activa la skill `solucion-respaldo-energetico` automáticamente.

## Qué genera esta skill

Una **página web interactiva** (HTML) con:

- **Dashboard de KPIs** — carga total, carga crítica, capacidad de respaldo, autonomía
- **Tabla completa del tablero** — todos los breakers con cargas calculadas y estado de cobertura
- **Tarjetas de equipos** — los equipos del inventario seleccionados con sus especificaciones y justificación
- **Cálculos detallados** — fórmulas paso a paso para dimensionamiento de UPS, generador y transferencia
- **Simulador de autonomía interactivo** — sliders para ajustar % de carga y ver cuánto duran las baterías
- **Diagrama unifilar** — topología visual del sistema de respaldo
- **Alertas** — si el inventario no cubre la demanda, qué equipos adicionales se necesitan

## Qué maneja

- Tableros monofásicos, bifásicos y trifásicos
- Sistemas 120V, 208V, 240V, 480V
- Cargas resistivas e inductivas (motores, HVAC, bombas)
- UPS standalone, UPS + Generador, sistemas con ATS/MTS
- Inventarios de cualquier marca o tamaño

## No requiere nada instalado

Solo Claude Code. Si necesita leer archivos Excel o Word, instala las librerías automáticamente.
