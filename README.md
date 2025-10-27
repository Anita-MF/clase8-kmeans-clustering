##Alumana Fernandez Ana Maria 
# Clase 8 — Clustering de clientes (K-Means)

## Objetivo
Segmentar clientes a partir de su comportamiento de compra para identificar perfiles accionables (ticket, frecuencia, tiempo en sitio, sensibilidad a descuentos y devoluciones).

## Datos y preparación
- 700 filas × 7 columnas: 5 variables de comportamiento + 2 de *noise* (ruido).
- Escalado con `StandardScaler` (media 0, desvío 1) para balancear magnitudes.

## Elección de k
- Codo (k=2..6): mejora fuerte hasta k=3, adicional en k=4, marginal luego.
- Silhouette: **pico ≈ 0.461 en k=6** → mejor separabilidad.
- **Elección final: k=6.**

### Gráficos (enlaces RAW para que siempre se vean)
![Codo](https://github.com/USER/REPO/blob/main/figs/elbow_inercia_k2_a_k6.png?raw=1)
![Silhouette](https://github.com/USER/REPO/blob/main/figs/silhouette_k2_a_k6.png?raw=1)
![Scatter ticket vs frecuencia](https://github.com/USER/REPO/blob/main/figs/scatter_avg_vs_freq_k6.png?raw=1)
![PCA 2D](https://github.com/USER/REPO/blob/main/figs/pca2d_k6.png?raw=1)

## Resultados y patrones
- Bandas por ticket: ~90 / ~180 / ~450 USD; separación adicional por frecuencia (~12/mes en alta frecuencia).
- PCA 2D: buena separación de los 6 clusters.
- Centroides en escala original: `centroides_kmeans.csv`.

## Métricas
- Silhouette (k=6): **≈ 0.461**
- Inercia (k=6): **≈ 7.6e+02**
- Estabilidad: variaciones mínimas al cambiar init/iteraciones.

## Acciones sugeridas
- Alta frecuencia + ticket medio: lealtad, cross-selling, novedades semanales.
- Ticket alto + baja frecuencia: bundles premium, reactivación dirigida.
- Ticket bajo + freq. media/baja: cupones, descuentos de recompra, recomendaciones en checkout.

## Video (5–7 min)
▶️ [Ver video en Google Drive](https://drive.google.com/file/d/1WemORDxNDlCA3UfL3D2rWfUJZE95iKYS/view?usp=sharing)

## Archivos
- `Clase8_KMeans.ipynb`
- `figs/elbow_inercia_k2_a_k6.png`
- `figs/silhouette_k2_a_k6.png`
- `figs/scatter_avg_vs_freq_k6.png`
- `figs/pca2d_k6.png`
- `centroides_kmeans.csv`
- `clientes_segmentados_kmeans.csv` (opcional)
