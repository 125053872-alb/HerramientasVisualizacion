# Herramientas de visualización

Dashboard con datos de Banxico.

## Instalación
pip install -r requirements.txt

## Ejecución
python -m streamlit run dashboard_banxico.py

## Cambios realizados
- Gráfica eliminada: mapa de calor "Promedio por mes y año". Repetía
  información que ya se ve en la gráfica de la serie con su media móvil y
  era difícil de leer con precisión.
- Gráfica agregada: "Volatilidad móvil" (desviación estándar de la variación
  diaria en una ventana móvil). Permite ver en qué momentos la serie fue más
  inestable, algo que la gráfica de cajas por año solo resume de forma anual.
  
## Integración con la API
Se consume la API REST del SIE de Banxico (series de tiempo) con requests,
usando un token guardado en secrets.toml (no se sube al repositorio).

## Transformación de los datos
- Los valores llegan como texto y se convierten a número (los días "N/E" se tratan como faltantes).
- Se calcula media móvil, cambio mensual, variación diaria y volatilidad móvil.
- Si se consultan varias series, se normalizan a base 100 para compararlas.

## Dashboard
Indicadores, gráficas con filtros de fechas y series, y descarga de los datos en CSV.
