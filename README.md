# telecom-analysis
📊 Proyecto de analítica de datos en Python para optimizar la oferta comercial y detectar patrones de uso de clientes en la empresa de telecomunicaciones ConnectaTel (México y Colombia).


# 📞 ConnectaTel: Análisis del Comportamiento de Clientes Móviles

## 🎯 1. Objetivo del Proyecto
El objetivo principal de este proyecto es evaluar y comprender el comportamiento real de consumo de los clientes de la empresa de telecomunicaciones **ConnectaTel** en México y Colombia. 

A través de este análisis se busca:
* Identificar patrones de uso en los servicios de llamadas y mensajes.
* Detectar comportamientos atípicos (*outliers*) o posibles errores de registro.
* Crear segmentaciones de clientes basadas en edad y nivel de consumo.
* Proponer recomendaciones comerciales estratégicas para optimizar la oferta de planes y mejorar la retención de usuarios.

---

## 📁 2. Datasets Utilizados
El análisis se basa en la integración de tres fuentes de datos (archivos CSV):
* **`plans.csv`**: Catálogo maestro de los planes actuales (Básico y Premium), incluyendo precios base, beneficios incluidos (minutos y mensajes) y costos por excedentes.
* **`users_latam.csv`**: Información demográfica y contractual de 4,000 clientes (identificador, nombre, edad, ciudad, fecha de registro y fecha de cancelación o *churn*).
* **`usage.csv`**: Bitácora de actividad real con 40,000 registros detallados de los eventos de consumo (tipo de servicio, fecha, duración de llamadas en minutos y longitud de mensajes).

---

## ⚙️ 3. Etapas del Análisis Realizadas
El proyecto se desarrolló siguiendo un flujo de pensamiento programático dividido en las siguientes fases:
1. **Carga y Exploración Inicial:** Lectura de datos y revisión de estructuras generales mediante `.shape` e `.info()`.
2. **Identificación de Problemas de Calidad:** Detección de valores nulos, registros duplicados y valores trampa o centinelas (como edades en `-999` o ciudades con `'?'`).
3. **Limpieza Básica de Datos:** Imputación de edades con la mediana, unificación de ciudades faltantes como `"Desconocido"`, eliminación de registros huérfanos sin fecha y manejo de nulos estructurales de consumo.
4. **Resumen Estadístico (Summary Statistics):** Construcción de una tabla maestra agregada por usuario (`user_profile`) y cálculo de métricas descriptivas (media, mediana, percentiles).
5. **Visualización y Detección de Outliers:** Creación de histogramas y gráficos de distribución para entender visualmente los sesgos y consumos extremos.
6. **Segmentación de Clientes:** Clasificación de usuarios en grupos específicos por nivel de uso (Bajo, Medio y Alto Uso) y por rangos generacionales (Joven, Adulto y Adulto Mayor).
7. **Insight Ejecutivo:** Traducción de los hallazgos en conclusiones accionables y sugerencias estratégicas para los tomadores de decisiones.

---

## 🚀 4. Cómo Ejecutar el Notebook (en Google Colab)
Para abrir, revisar y ejecutar este proyecto de forma interactiva en la nube, sigue estos sencillos pasos:

1. Entra a [Google Colab](https://google.com).
2. Inicia sesión con tu cuenta de Google.
3. En la ventana emergente, selecciona la pestaña **GitHub**.
4. Pega la URL de este repositorio de GitHub y presiona la tecla *Enter*.
5. Haz clic sobre el archivo `.ipynb` del proyecto (por ejemplo, `proyecto_6.ipynb`) para abrirlo directamente en el entorno de Colab.

---

## 🔄 5. Guía de Reproducción del Análisis
Si deseas descargar el proyecto y ejecutarlo en tu computadora local o asegurar su correcta reproducción, sigue esta guía:

### Prerrequisitos
Asegúrate de tener instalado Python (versión 3.8 o superior) junto con las siguientes librerías de ciencia de datos:
```bash
pip install pandas numpy matplotlib seaborn
```

### Pasos para replicar:
1. **Clonar el repositorio o descargar los archivos:** Descarga el archivo del Notebook (`.ipynb`) y la carpeta con los tres archivos CSV (`plans.csv`, `users_latam.csv`, `usage.csv`).
2. **Estructura de carpetas:** Para que las rutas de lectura funcionen correctamente, asegúrate de colocar los archivos CSV dentro de una carpeta llamada `datasets` en el mismo directorio donde guardes tu notebook:
   ```text
   ├── tu_notebook.ipynb
   └── datasets/
       ├── plans.csv
       ├── users_latam.csv
       └── usage.csv
   ```
3. **Ejecutar las celdas:** Abre el notebook desde tu entorno local (Jupyter Notebook, JupyterLab o VS Code) y ejecuta las celdas en orden secuencial (de arriba hacia abajo) utilizando el botón `Run` o el atajo `Shift + Enter`.
