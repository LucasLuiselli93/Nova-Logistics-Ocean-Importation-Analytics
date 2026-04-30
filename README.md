# Nova Logistics: Ocean Importation & Performance Optimization

## 📊 Visualización de Paneles
### Dashboard de Optimización (CBM & HBL)
![Optimización Operativa](assets/dashboard_opt.png)

### Resumen de Importación Oceánica (Comparativa YOY)
![Resumen General](assets/dashboard_sum.png)

## 📌 Escenario de Negocio
El departamento de logística global de Nova Logistics requería una herramienta para medir la eficiencia en el uso de contenedores (CBM) y la gestión documental (HBL). El objetivo es identificar desviaciones en la carga y optimizar la rentabilidad de cada envío mediante el monitoreo de KPIs de cumplimiento con un benchmark objetivo del 75%.

## 🏗️ Arquitectura del Modelo Semántico
El núcleo de este proyecto es un modelo de datos complejo que integra múltiples procesos de negocio mediante tablas de hechos vinculadas a dimensiones compartidas.

![Modelo Semántico](assets/model.png)

*   **Granularidad:** El modelo opera a nivel de Operación / Embarque (Operation / Shipment).
*   **Tablas de Hechos:** 
    *   `FACT_EMPRESAS`: Métricas comerciales y de centros de costos.
    *   `FACT_HIM`: Métricas operativas de importación.
    *   `FACT_HIT`: Detalles transaccionales y de ruteo.
*   **Dimensiones Centrales:** Calendario, Agentes (Origin/LCL), Geografía y Compañías.

## 🛠️ Stack Tecnológico
*   **Power BI:** Modelado y visualización avanzada.
*   **DAX:** Implementación de lógica para medidores (Gauges) de performance y parámetros dinámicos de selección.
*   **SQL:** Procesamiento de la capa de datos para asegurar la integridad de los hechos `HIM` y `HIT`.

## 🚀 Desafíos Técnicos Resueltos
1.  **Arquitectura Multi-Fact:** Diseño de un modelo capaz de relacionar tres tablas de hechos distintas sin generar ambigüedad en los filtros cruzados.
2.  **Selección Dinámica de Dimensiones:** Implementación de parámetros de campo que permiten al usuario cambiar dinámicamente las filas y columnas de la matriz de resumen (Año, Mes, País, Cliente).
3.  **Visualización de Performance (Gauges):** Configuración de indicadores visuales condicionales basados en el cumplimiento de optimización de CBM y HBL por tipo de contenedor (20', 40', 40'HC).

## 💡 Impacto
*   **Benchmarking Temporal:** Visibilidad clara de la evolución del volumen de HBL de 2024 a 2026.
*   **Optimización de Carga:** Identificación de rutas y agentes con un cumplimiento de CBM inferior al 75%, permitiendo ajustes inmediatos en la consolidación de carga.
*   **Centralización Operativa:** Reducción de la latencia en la consulta de datos operativos distribuidos en múltiples nodos de la cadena de suministro.
