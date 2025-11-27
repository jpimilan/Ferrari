# Ferrari
Caso de estudio Ferrari: exclusividad, innovación y valor residual en el lujo.
Protocolo de Validación Experimental para que cualquier investigador o lector pueda replicar tu modelo Sankey-MCDM desde este repositorio en GitHub: https://github.com/jpimilan/Ferrari y ejecutarlo visualmente en CodePen (https://codepen.io/), asegurando la reproducibilidad de tu prueba de Validación (2024–2025).

🧩 Protocolo de Validación – Repositorio GitHub “Ferrari”

Repositorio fuente:
https://github.com/jpimilan/Ferrari

Objetivo:
Garantizar que cualquier investigador pueda reproducir el experimento de validación del modelo multicriterio ponderado (MCDM) aplicado al caso Ferrari N.V. y visualizar el Sankey dinámico con los datos y parámetros del bloque de Validación 2024–2025 en CodePen.io.

1. Estructura general del repositorio

   Carpetas recomendadas:
    Carpeta	Contenido	Descripción
    /data/	evaluacion_3_7_v0.5.xlsx	Dataset base con criterios, vías, ponderaciones, pesos y referencias APA7.

2. Archivos principales
    Archivo	Propósito
    sankey.html	Define la estructura base (divs, controles, paneles de selección, etc.).
    sankey.css	Define los estilos visuales (colores, disposición, tipografía, márgenes, paleta de azules).
    sankey.js	Contiene la lógica de renderizado D3.js, el procesamiento del dataset y las interacciones.
    evaluacion_3_7_v0.5.xlsx	Contiene la matriz completa de criterios-vías-KPIs con años 2011–2025.
    README.md	Describe brevemente cómo abrir el experimento en CodePen y cómo interpretar la visualización.

3. Dependencias externas
    Para ejecutar el código en CodePen o cualquier entorno web sin backend, asegúrate de incluir en Settings → JS externals las siguientes bibliotecas:
    JS externals las siguientes bibliotecas:
    https://unpkg.com/d3@7
    https://unpkg.com/d3-sankey@0.12.3

4. Proceso de validación reproducible
    Paso 1. Acceso y descarga
     a) Ir al repositorio público:
        https://github.com/jpimilan/Ferrari
    
     b) Descargar como archivo .zip o clonar con:
        git clone https://github.com/jpimilan/Ferrari.git
    
    Paso 2. Carga en CodePen
      a) Crear una cuenta gratuita en https://codepen.io
      b) Abrir un nuevo Pen.
      c) Copiar el contenido de los archivos:
        - sankey.html → pestaña HTML
        - sankey.css → pestaña CSS
        - sankey.js → pestaña JS
    
     En “Settings” → pestaña JS, agregar las dependencias D3.js mencionadas arriba.

      Paso 3. Carga del dataset
       a) Exportar el archivo evaluacion_3_7_v0.5.xlsx como CSV (por ejemplo, data.csv).
       b) Cargar el CSV en CodePen como variable o usar un enlace público de GitHub Raw:
       Ejemplo:
       js:
       const DATA_URL = "https://raw.githubusercontent.com/jpimilan/Ferrari/main/data/data.csv";

 5. Asegurar que el script de carga use:
  js:
  d3.csv(DATA_URL).then(data => {
  renderSankey(data);
   });

  Paso 4. Ejecución de la validación
   a) Ejecutar el Pen y seleccionar los años 2024 y 2025.
   b) Observar la estructura:
      . Columna izquierda: criterios ponderados.
      - Columna central: vías estratégicas (Electrificación selectiva, Escasez, Comunidad, Digital).
      - Columna derecha: KPIs (VR, margen, NPS, mix híbrido, tiempo de integración).
      - Activar los botones “Comprobar PI” para verificar flujos entre criterios y KPIs.

  6. Comparar los resultados esperados con los reportados en sección 3.7.7 del manuscrito.

  7. Validación del modelo
     El experimento se considera válido si al ejecutar los años 2024–2025:
       Los flujos principales del Sankey coinciden con:
         Electrificación selectiva ≈ 32.5 %
         Precio/personalización/escasez ≈ 32.5 %
         Comunidad y patrimonio ≈ 20 %
         Servicios digitales ≈ 15 %
       Los KPIs resultantes suman ≈ 100 %.
       El texto superior indica etapa: Validación (promedio).
       El panel lateral lista los insights 2024 y 2025.
       La lógica de las relaciones PI1–PI3 coincide con la descripción del manuscrito (3.7.7).

  8. Interpretación de resultados
       La correcta reproducción del Sankey confirma la validación de la hipótesis de que el modelo de escasez disciplinada y electrificación selectiva sostiene la rentabilidad.
       El VR y la transición tecnológica con control de riesgo y tiempo de integración.
       La coincidencia entre pesos, flujos y etiquetas de etapa certifica la validez interna y la replicabilidad del modelo en otros entornos visuales.

  9. Referencia para citar el protocolo
      Imilan, J. P. (2025). Protocolo de validación del modelo Sankey-MCDM Ferrari (2011–2025) [Repositorio GitHub]. Recuperado de https://github.com/jpimilan/Ferrari
