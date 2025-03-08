library(dplyr)
library(tseries)

# 1. Cargar el dataset
data("AirPassengers")

# Inspeccionar la estructura del dataset
print(class(AirPassengers))   # Es una serie temporal (ts)
print(summary(AirPassengers)) # Resumen estadístico
print(start(AirPassengers))   # Inicio de la serie
print(end(AirPassengers))     # Fin de la serie
print(frequency(AirPassengers)) # Frecuencia: 12 (mensual)

# 2. Exploración inicial
plot(AirPassengers, main="Número de pasajeros entre 1949 y 1960", ylab = "Pasajeros", xlab="Año")

print("Media de la serie temporal:")
print(mean(AirPassengers))

print("Desviación estándar de la serie temporal:")
print(sd(AirPassengers))

# 3. Análisis de tendencia y estacionalidad
st_decomp <- decompose(AirPassengers)
plot(st_decomp)

# 4. Análisis de estacionariedad
acf(AirPassengers, main="Autocorrelación de AirPassengers")
pacf(AirPassengers, main = "Autocorrelación parcial de AirPassengers")

adf.test(AirPassengers)
# El p-value es menor que 0.05, así que podemos rechazar la hipótesis nula y concluir
# que la serie temporal es estacionaria

# 5. Detección de valores atípicos
boxplot(AirPassengers)
# No hay valores atípicos

# 6. Interpretación de resultados
# La tendencia de la serie temporal se mantiene positiva a lo largo del tiempo, creciendo de forma continua.
# En relación con las estacionalidades, se puede observar, tanto con el análisis de la estacionalidad como con el 
# gráfico correspondiente, que existe una estacionalidad visible, que se repite a lo largo de los años.
# Con los ciclos sucede de igual forma, se van repitiendo los ciclos a lo largo de los años, no teniendo necesariamente
# la misma longitud pero sí similar forma.
# Estos patrones podrían ayudar en la interpretación de los datos, ya que se han observado las mismas tendencias a lo largo de
# varios años, lo que podría ayudar a predecir futuros comportamientos, esperando que la estacionalidad se repita y la tendencia
# continúe siendo positiva.