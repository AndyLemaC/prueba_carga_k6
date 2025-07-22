# ⚡ Prueba de Carga con K6 - Servicio de Login

Este proyecto realiza una prueba de carga sobre el endpoint de login utilizando [K6](https://k6.io/), simulando múltiples usuarios concurrentes, validando el rendimiento bajo estrés, y evaluando tiempos de respuesta frente a umbrales definidos.

---

## ✅ Requisitos Previos

- Tener [K6 instalado](https://k6.io/docs/getting-started/installation/)
- Git instalado
- Editor de texto (Visual Studio Code, por ejemplo)

---

## 📁 Estructura del Proyecto

```
prueba_k6/
├── data/
│   └── users.csv                # Datos de prueba con usuarios y contraseñas
├── scripts/
│   └── login-test.js            # Script de prueba principal
├── resultados/
│   ├── resumen.json             # Reporte generado automáticamente
│   └── reporte.html             # Reporte visual (opcional)
├── conclusiones.txt            # Hallazgos del test
└── README.md                   # Este archivo
```

---

## ▶️ Ejecución del Script

Desde la terminal (CMD o PowerShell), navega a la carpeta del proyecto:

```bash
cd C:\Users\andyn\OneDrive\Documents\prueba_k6\prueba_k6
k6 run scripts\login-test.js
```

---

## 🔧 Configuración de la Prueba

- 🔁 **Escenario**: 1 escenario por defecto
- 👥 **Usuarios virtuales (VUs)**: hasta 20
- ⏱ **Duración total**: 3m30s (3 etapas incluyendo parada gradual)
- 📄 **Datos**: usuarios desde archivo CSV (`data/users.csv`)

---

## 🎯 Umbrales Definidos

| Métrica               | Umbral                  | Resultado alcanzado |
|-----------------------|--------------------------|----------------------|
| Tiempo respuesta p(95) | < 1500 ms               | ✅ 403.14 ms         |
| Tasa de error         | < 3%                    | ✅ 0.00%             |

---

## 📊 Resultados Obtenidos

### ✅ Totales

- Total de checks: **4862**
- Checks correctos: **100.00%**
- Fallos: **0%**

### 💡 Indicadores HTTP

| Métrica                  | Valor                   |
|--------------------------|-------------------------|
| Promedio (`avg`)         | 366.34 ms               |
| Mínimo (`min`)           | 319.07 ms               |
| Mediana (`med`)          | 361.9 ms                |
| Máximo (`max`)           | 1.15 s                  |
| Percentil 90 (`p(90)`)   | 389.60 ms               |
| Percentil 95 (`p(95)`)   | **403.14 ms**           |

### 🔁 Iteraciones

- Iteraciones completadas: **2431**
- Iteraciones por segundo: **11.53**

### 🌐 Red

- Datos recibidos: **1.4 MB**
- Datos enviados: **285 KB**

---

## 📌 Conclusiones

Consulta el archivo `conclusiones.txt` para ver los hallazgos clave del test, comportamiento bajo carga, posibles mejoras o puntos de atención detectados.