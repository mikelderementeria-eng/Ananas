# 菠萝 EL PIÑA TRAINING SYSTEM

Sistema de entrenamiento modular y fácilmente personalizable.

## 📁 Estructura del Proyecto

```
/workspace/
├── index.html              # HTML principal (solo markup)
├── css/
│   └── styles.css          # Todos los estilos
├── js/
│   └── app.js              # Lógica de la aplicación
├── data/
│   ├── system-config.json  # Configuración general del sistema
│   ├── boxing-rounds.json  # Rounds de boxeo
│   └── plio-exercises.json # Ejercicios pliométricos
└── templates/              # Plantillas para nuevas versiones
```

## 🚀 Crear Nueva Versión

### Opción 1: Copiar configuración existente
```bash
cp data/system-config.json data/config-santiago.json
cp data/boxing-rounds.json data/boxing-santiago.json
cp data/plio-exercises.json data/plio-santiago.json
```

### Opción 2: Editar configuración
Modifica `data/system-config.json`:
- Cambia `version`, `coach`, `theme`
- Ajusta `pinaThresholds` y `pinaNames`

### Opción 3: Personalizar ejercicios
Edita los archivos JSON en `/data`:
- `boxing-rounds.json`: Agrega/quita rounds
- `plio-exercises.json`: Modifica ejercicios por día

## 🔧 Configuración Principal

### system-config.json
```json
{
  "version": "valparaiso-v1",
  "systemName": "EL PIÑA TRAINING SYSTEM",
  "coach": "EL PROFE",
  "theme": { ... },
  "pinaThresholds": [2, 4, 7, 10, 14],
  "pinaNames": ["¡PRIMERA PIÑA!", ...]
}
```

### boxing-rounds.json
```json
{
  "rounds": [
    {"id": 0, "title": "Jab - Cross", "duration": 180},
    {"id": 1, "title": "Hook - Uppercut", "duration": 180}
  ],
  "baseExercises": [...]
}
```

### plio-exercises.json
```json
{
  "diaA": {
    "calent": {"rounds": 8, "workSec": 30, "restSec": 20, "exs": [...]},
    "dev": {...},
    "finish": {...}
  },
  "diaB": {...}
}
```

## 🎯 Ventajas de esta Arquitectura

1. **Edición sin código**: Cambia ejercicios editando JSON
2. **Versiones ilimitadas**: Copia archivos de configuración
3. **Mantenimiento fácil**: Core común, configuraciones específicas
4. **Control de versiones**: Trackea cambios en archivos separados
5. **Temas personalizables**: Cambia colores desde config

## 🛠️ Desarrollo

### Agregar nueva funcionalidad
1. Edita `js/app.js`
2. Agrega funciones modulares
3. Prueba con diferentes configs

### Crear tema personalizado
1. Copia `data/system-config.json`
2. Modifica valores de `theme`
3. Referencia el nuevo archivo en HTML

## 📝 Notas

- El sistema carga configuraciones vía fetch()
- Funciona offline una vez cargado
- Usa localStorage para persistencia
- Compatible con todos los navegadores modernos

## 🍍 Piña Level System

El sistema de niveles se configura en `pinaThresholds`:
- Nivel 1: 2 sesiones
- Nivel 2: 4 sesiones
- Nivel 3: 7 sesiones (activa modo Piña)
- Nivel 4: 10 sesiones
- Nivel 5: 14 sesiones (Piña Suprema)

---
**Creado para hacer muchas versiones "El Piña"** 🍍
