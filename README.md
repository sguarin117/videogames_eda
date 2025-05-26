# videogames_eda
# 📊 Proyecto Integrado: Análisis de Ventas de Videojuegos

Este proyecto tiene como objetivo identificar patrones que determinan el éxito de un videojuego, con el fin de detectar proyectos prometedores y planificar campañas publicitarias. Trabajamos con datos históricos de ventas, reseñas y plataformas desde 1980 hasta 2016.

## 🧰 Herramientas utilizadas

- Python
- Jupyter Notebook
- pandas, numpy
- matplotlib, seaborn
- scipy.stats

## 🗂️ Estructura del análisis

---

### 🧾 Paso 1: Carga y exploración inicial de los datos

- Se cargó el archivo `games.csv`.
- Se detectaron valores nulos, principalmente en `critic_score`, `user_score` y `rating`.

---

### 🔧 Paso 2: Preparación de los datos

- Se normalizaron los nombres de las columnas (minúsculas).
- Se convirtieron los tipos de datos según lo requerido.
- Se rellenaron valores nulos con `-1` en columnas numéricas para evitar distorsiones (por ejemplo, en `year_of_release`, `critic_score`, `user_score`).
- Los valores "TBD" en `user_score` se transformaron a `-1` para facilitar su conversión a tipo `float`.
- La columna `rating` se rellenó con `'RP'` (Rating Pending) cuando faltaba.
- Se creó una nueva columna `total_sales` como suma de `NA_sales`, `EU_sales`, `JP_sales` y `Other_sales`.

---

### 📈 Paso 3: Análisis exploratorio de los datos

- Se observó un incremento constante en el número de juegos lanzados hasta 2011, seguido de una caída.
- Las plataformas con mayores ventas históricas fueron:
  - PlayStation 2 (PS2)
  - PlayStation 3 (PS3)
  - Xbox 360
- Se determinó que el ciclo de vida promedio de una plataforma es de **7.6 años**.
- Se seleccionaron datos desde **2008 hasta 2016** para construir un modelo representativo.
- Se encontró que:
  - Las ventas estaban en descenso en 2016 (posiblemente por datos incompletos).
  - PS4 y Xbox One venían mostrando un crecimiento en ventas.
- Las plataformas con mayor dispersión y ventas promedio fueron PS3, X360, XOne y PS4.
- Correlación entre reseñas y ventas:
  - Las ventas de PS3 muestran **baja pero positiva correlación** con las reseñas.
  - La crítica profesional influye más que las reseñas de usuarios.

#### 🎮 Géneros más vendidos:

| Género     | Observación                      |
|------------|----------------------------------|
| Acción     | Más rentable                     |
| Shooter    | Muy popular                      |
| Deportes   | Altas ventas                     |
| Estrategia | Ventas bajas                     |
| Puzzle     | Ventas bajas                     |

---

### 🌍 Paso 4: Perfil de usuario por región

#### 📌 Norteamérica:
- Plataforma líder: **PS4** (27.8%)
- Género más popular: **Acción**
- ESRB más vendido: `M` (Mature)

#### 📌 Europa:
- Plataforma líder: **PS4** (40.8%)
- Género más popular: **Acción**
- ESRB más vendido: `M` (Mature)

#### 📌 Japón:
- Plataforma líder: **Nintendo DS** (28.6%)
- Género más popular: **Plataforma**
- ESRB más vendido: `E` (Everyone)

> Las clasificaciones ESRB tienen un impacto claro y diferente en cada región.

---

### 🧪 Paso 5: Pruebas de hipótesis

#### Hipótesis 1:
- **H₀**: Las calificaciones promedio de usuarios para Xbox One y PC son iguales.
- **Resultado**: Se rechaza H₀ → *Las calificaciones son diferentes*.

#### Hipótesis 2:
- **H₀**: Las calificaciones promedio de usuarios para los géneros Acción y Deportes son iguales.
- **Resultado**: No se rechaza H₀ → *No hay diferencia significativa*.

---

### ✅ Conclusiones

- Las plataformas con mayor potencial en 2017 son PS4 y Xbox One.
- El género Acción lidera el mercado, aunque el género más rentable varía según la región.
- Las reseñas tienen un impacto, pero no son determinantes del éxito.
- El ESRB rating es un factor clave en la decisión de compra dependiendo del mercado.

---

## 📂 Archivos

- `proyecto_videojuegos.ipynb`: Notebook con todo el código y visualizaciones.
- `games.csv`: Dataset original (no incluido por derechos de uso).
- `README.md`: Este archivo.

---

## 🧠 Autor

**Sebastián Camilo Guarín Novoa**  
Proyecto desarrollado como parte de la formación en análisis de datos.

---
