# Project Log — Banking DS Project

## 2026-04-18 — Fase 0: Setup completado

### Decisiones tomadas
- Dataset seleccionado: Give Me Some Credit (Kaggle)
- Gestor de entornos: Conda (banking-ds, Python 3.11)
- Data Warehouse: DuckDB local (migración a BigQuery en Fase 6)
- Stack principal: pandas, scikit-learn, duckdb, jupyter

### Estructura del repositorio
Creada según convenciones de Data Science profesional.
Datos excluidos del repositorio por privacidad (.gitignore).

### Próximo paso
Fase 1: Descarga del dataset y primer análisis exploratorio en DuckDB.



## 2026-04-20 — Fase 1: EDA en progreso

### Lo completado hoy
- Carga del dataset cs-training.csv (150.000 filas × 11 columnas)
- Análisis de nulos: MonthlyIncome (19.82%) y NumberOfDependents (2.62%)
- Inspección de tipos: todas las variables son numéricas (int/float)
- Estadísticas descriptivas completas
- Detección de outliers críticos

### Hallazgos clave
- MonthlyIncome tiene distribución right-skewed — usar mediana para imputar
- Variables de mora (30-59, 60-89, 90 días) tienen valor 98 con 264 ocurrencias
  → Probable código especial del sistema origen, tratar como nulo en Fase 2
- NumberOfDependents es float por presencia de nulos (comportamiento de pandas)

### Pendiente para próxima sesión
- Distribución de la variable objetivo (SeriousDlqin2yrs)
- Histogramas de variables numéricas
- Heatmap de correlaciones
- Relación entre variables y variable objetivo