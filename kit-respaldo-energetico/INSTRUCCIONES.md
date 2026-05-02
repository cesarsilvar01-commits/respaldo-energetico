# Cómo usar el Diseñador de Respaldo Energético

## Requisitos

1. **Visual Studio Code** instalado (https://code.visualstudio.com)
2. **Extensión de Claude Code** instalada (busca "Claude Code" en el marketplace de VS Code)

## Paso 1 — Abrir el proyecto

1. Abre VS Code
2. Archivo → Abrir carpeta → selecciona la carpeta `kit-respaldo-energetico`
3. Abre Claude Code desde el panel lateral de VS Code

## Paso 2 — Proporcionar el estudio de carga

Puedes darle los datos de dos maneras:

**Opción A — En el chat directamente:**
```
Tablero principal planta 2
- Sistema: Trifásico, 208V
- Breakers:
  1. 3P / 30A / Chillers (CRÍTICO)
  2. 2P / 20A / Iluminación planta (CRÍTICO)
  3. 1P / 15A / Tomas de corriente oficina
  4. 3P / 60A / Compresor (CRÍTICO)
  5. 1P / 20A / Cafetería
- Autonomía requerida: 45 minutos
```

**Opción B — Compartir el archivo:**
- PDF, Excel (.xlsx), o Word (.docx) con el estudio de carga

## Paso 3 — Proporcionar el inventario de equipos

```
Inventario disponible:
- UPS APC Symmetra LX, 16 kVA, entrada trifásica, salida trifásica, 15 min autonomía
- Generador Kohler 60 kW, trifásico, diesel
- ATS Russelectric 100A, trifásico
- UPS APC Smart-UPS 3000VA monofásico
```

O comparte tu archivo de inventario en cualquier formato.

## Paso 4 — Recibir la solución

Claude analiza los datos, calcula la carga crítica, selecciona los equipos del inventario y genera automáticamente:

```
solucion_respaldo_[nombre-tablero].html
```

Abre el archivo en tu navegador para ver el dashboard interactivo completo.

## Lo que verás en el dashboard

| Pestaña | Contenido |
|---------|-----------|
| Resumen | KPIs principales, estado de cobertura, alertas |
| Tablero | Todos los breakers con cargas calculadas |
| Equipos Seleccionados | Tarjetas con specs de cada equipo del inventario |
| Cálculos | Fórmulas paso a paso, dimensionamiento completo |
| Simulador Autonomía | Slider interactivo para ver duración de baterías |
| Diagrama | Topología unifilar del sistema de respaldo |

## Preguntas frecuentes

**¿Funciona si no tengo todos los datos exactos?**
Sí. Si falta el amperaje exacto de algún breaker, usa el valor nominal del breaker como estimado conservador. Si no sabes el factor de potencia, se usa 0.85 por defecto.

**¿Qué pasa si el inventario no cubre la demanda?**
La página muestra exactamente cuánto le falta (kVA / kW) y qué tipo de equipo adicional se necesita, sin inventar nada.

**¿Puedo pedir que cambie qué breakers son críticos?**
Sí, simplemente dile cuáles quieres incluir o excluir y regenera.

**¿El archivo HTML es editable?**
Sí, es un archivo auto-contenido que puedes compartir, imprimir o abrir en cualquier navegador sin conexión a internet.

## Estructura del kit

```
kit-respaldo-energetico/
├── CLAUDE.md                            <- Claude lo lee automáticamente
├── INSTRUCCIONES.md                     <- Este archivo
└── .claude/
    └── skills/
        └── solucion-respaldo-energetico.md  <- La skill
```
