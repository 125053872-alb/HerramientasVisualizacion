# Herramientas de visualización

Dashboard con datos de Banxico.

## Instalación
pip install -r requirements.txt

## Ejecución
streamlit run dashboard_banxico.py

## Cambios realizados
- Gráfica eliminada: mapa de calor "Promedio por mes y año". Repetía
  información que ya se ve en la gráfica de la serie con su media móvil y
  era difícil de leer con precisión.
- Gráfica agregada: "Volatilidad móvil" (desviación estándar de la variación
  diaria en una ventana móvil). Permite ver en qué momentos la serie fue más
  inestable, algo que la gráfica de cajas por año solo resume de forma anual.
