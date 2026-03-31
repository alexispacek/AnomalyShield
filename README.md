#  UEBA + CVE Analysis Challenge

##  Descripción

Este proyecto resuelve dos problemas:

1. **UEBA (User Behavior Analytics)**  
   Detección de anomalías en logins mediante reglas + modelo ML.

2. **Análisis de CVEs**  
   Extracción de información estructurada (vendor, producto, tipo de vulnerabilidad) a partir de texto libre.

---

## ⚙️ Tecnologías utilizadas

- Python
- Pandas / Numpy
- Scikit-learn (Isolation Forest)
- Sentence Transformers (embeddings)
- Google Gemini (LLM)
- Selenium + BeautifulSoup (scraping)

---

##  Enfoque

### Problema 1 (UEBA)

- Feature engineering por usuario
- Reglas estadísticas (percentiles)
- Modelo unsupervised (Isolation Forest)
- Calibración por usuario (UEBA real)
- Explicabilidad mediante LLM

---

### Problema 2 (CVE Analysis)

Pipeline híbrido:

- Clasificación de vulnerabilidad → embeddings
- Extracción vendor/producto → LLM (Gemini)
- Cache semántico → reducción de costo
- Batch processing → eficiencia
- Reprocesamiento → mejora de calidad

---

##  Resultados

- Alta precisión en detección de anomalías
- Pipeline robusto y escalable
- Reducción de llamadas a LLM mediante cache
- Dataset final enriquecido y estructurado

---

##  Cómo ejecutar

1. Instalar dependencias:

```bash
pip install -r requirements.txt

2. Configurar API Key:

en bash: export GEMINI_API_KEY=tu_api_key

3. Ejecutar notebooks:
problema1.ipynb
problema2.ipynb

Estructura

project/
├── notebooks/
│   ├── problema1.ipynb
│   └── problema2.ipynb
│
├── src/
│   └── data/
│       ├── user_logins.csv
│       └── CVE_3_meses.csv
│
├── challenge.pdf
├── README.md
├── requirements.txt
└── .gitignore

El scraping puede demorar ~1 hora (se recomienda reutilizar el CSV)
Se implementó cache semántico para optimizar costos
El sistema es extensible a otros datasets de vulnerabilidades

## Looker

Se puede visualizar mi dashboard interactivo en Looker Studio:

[https://lookerstudio.google.com/s/lkVEKRrzvAQ]

