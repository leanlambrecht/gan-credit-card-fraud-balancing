# Redes generativas para balance de fraude crediticio

El proyecto utiliza una **Generative Adversarial Network (GAN)** para generar transacciones sintéticas de la clase minoritaria y evaluar su efecto sobre modelos de detección de fraude.

## ¿Qué es una red generativa?

Una GAN enfrenta dos redes: un **generador**, que crea registros sintéticos, y un **discriminador**, que intenta distinguirlos de los datos reales. El entrenamiento adversario busca que los datos generados sean cada vez más plausibles.

## Metodología

- Análisis del fuerte desbalance del dataset de tarjetas.
- Comparación de `class_weight`, submuestreo y SMOTE.
- Entrenamiento de varias configuraciones GAN.
- Generación de 2.000 registros sintéticos de fraude.
- Reentrenamiento de Decision Tree, Random Forest y Gradient Boosting.

## Resultado principal

Con datos GAN, Random Forest alcanza F1 0,9850, precision 0,9959 y recall 0,9743. Gradient Boosting logra F1 0,9830 y Decision Tree 0,9707, superando las configuraciones sin generación sintética reportadas en el trabajo.

## Estructura

- `notebooks/`: notebook principal con rutas relativas y datos preparados para ejecutarse desde el repositorio.
- `data/`: dataset completo comprimido en partes y muestra rápida.
- `assets/figures/`: distribuciones de clases y resultado de SMOTE.
- `results/`: comparación de métricas.
- `reports/`: informe profesional en PDF y Word.

## Ejecución

```bash
pip install -r requirements.txt
jupyter notebook notebooks/gan-credit-card-fraud-balancing.ipynb
```

## Autor

**Lea Lambrecht**  
LinkedIn: linkedin.com/in/lealambrecht  
GitHub: github.com/leanlambrecht
