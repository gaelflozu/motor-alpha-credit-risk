# 🐺 Motor Alpha v3.0 | Quantitative Credit Risk Engine

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

> **Simulador Interactivo en Vivo:** [Lanzar Dashboard de Motor Alpha](https://gaelflozu.github.io/motor-alpha-credit-risk/)

## 📌 Resumen Ejecutivo
**Motor Alpha** es un sistema cuantitativo de originación de crédito diseñado para abandonar los modelos tradicionales de límite fijo y transicionar hacia una **Asignación Asimétrica de Capital**. 

El objetivo principal del motor no es solo predecir quién va a pagar, sino calcular matemáticamente **cuánto capital se puede arriesgar** por cliente para maximizar el Valor Esperado (+EV) del portafolio, protegiendo a la institución del riesgo de ruina.

## 📐 Arquitectura Matemática (Core Logic)

El motor opera bajo tres pilares fundamentales de gestión de riesgo:

1. **Probabilidad de Default (PD) via Machine Learning:**
   Se implementó un modelo de **Regresión Logística** entrenado con más de 31,000 registros históricos. El modelo pondera variables demográficas y financieras para escupir una probabilidad exacta de impago por cada solicitud.

2. **Criterio de Kelly Fraccional (Optimización de Capital):**
   A diferencia de los límites estáticos, Motor Alpha utiliza una fracción conservadora del Criterio de Kelly (`f = 0.10`) para calcular la exposición máxima óptima. Esto asegura un crecimiento asintótico del capital del banco mientras mitiga la volatilidad ante rachas de impagos.
   * *Supuesto de castigo:* Se asume un **Loss Given Default (LGD) del 100%** para estresar el modelo al máximo nivel de riesgo.

3. **La "Guillotina de Riesgo" (Risk Cut-off):**
   El sistema tiene programada una regla de negocio inquebrantable: cualquier perfil cuya Probabilidad de Default (PD) supere el **15%** es automáticamente rechazado, bloqueando la exposición a capitales tóxicos. La exposición máxima por cliente está topada a $50,000 MXN.

## 💻 Tech Stack
* **Data Science & Modelado:** Python, Pandas, Scikit-Learn.
* **Frontend / Dashboard:** HTML5, Vanilla JavaScript, Tailwind CSS.
* **Despliegue:** GitHub Pages (Client-side simulation).

## 🚀 Cómo ejecutar la simulación local
Si deseas clonar este repositorio y correr la interfaz de simulación:

1. Clona el repositorio:

    git clone https://github.com/gaelflozu/motor-alpha-credit-risk.git

2. Abre el archivo `index.html` en cualquier navegador moderno.
3. Para simular carteras, carga el archivo `.csv` de prueba incluido en la carpeta `/data` (contiene +6,200 registros de clientes).
4. El dashboard generará los límites de crédito dinámicos y la matriz de aprobación/rechazo en tiempo real.

## 👨‍💻 Sobre el Autor
**Gael Flores Zúñiga**
*Estudiante de Actuaría | Analista Cuantitativo Junior*

* Conecta conmigo en [LinkedIn](https://www.linkedin.com/in/gael-flores-datos)
* Contacto: gaelflozu@gmail.com
