# Toolkit

[English](README.md) · **Español**

Con lo que construimos de verdad, contado a partir de los manifiestos de dependencias de
nuestras bases de código activas — no de memoria, ni de una lista de cosas sobre las que
leímos alguna vez.

**Método.** Cada cifra es el número de proyectos distintos cuyo `package.json` o
`requirements.txt` declara esa dependencia, sobre **19 proyectos que contienen código**
(quedan excluidos los proyectos que son solo documentación o propuestas). Contar
manifiestos en lugar de menciones implica que una tecnología que integramos una vez y
abandonamos no infla el número, y que una tecnología de la que hablamos en un documento de
diseño pero que nunca llegó a desplegarse puntúa cero.

## Runtime y framework

| | Proyectos (de 19) |
| --- | --- |
| Node.js / TypeScript | 13 |
| Express | 9 |
| Python | 6 |
| FastAPI | 3 |
| Cloud Functions Gen2 (`functions-framework`) | 3 |
| Next.js | 3 |
| React Native / Expo | 1 |

## Google Cloud

| | Proyectos (de 19) |
| --- | --- |
| Firestore (`firebase-admin`) | 11 |
| Firestore (`google-cloud-firestore`, Python) | 4 |
| Cloud Storage | 5 |
| BigQuery | 2 |
| Secret Manager (SDK; casi todo el acceso va por ADC, no por el SDK) | 1 |

El cómputo es Cloud Run y Cloud Functions Gen2 en todos los casos, con escalado a cero por
defecto.

## IA / LLM

| | Proyectos (de 19) |
| --- | --- |
| Gemini, `@google/generative-ai` (SDK antiguo) | 6 |
| Gemini, `@google/genai` (SDK actual) | 3 |
| Gemini, `google-generativeai` (Python) | 3 |

Los dos SDK de JavaScript conviven porque hay una migración en curso y la hacemos de forma
incremental, no como un corte único. Lo decimos en vez de ocultarlo: una base de código con
un único SDK en todas partes y sin historial de migración suele ser una base de código que
solo se ha escrito una vez.

## Datos y pagos

| | Proyectos (de 19) |
| --- | --- |
| MySQL (`mysql2`, incl. AWS RDS Aurora a través de un conector VPC) | 2 |
| Stripe | 1 |

## Plataformas de terceros

Pasarelas de WhatsApp, Meta Graph / Instagram, Telegram (alertas de operación), EspoCRM,
SendGrid y Resend (email transaccional), además de proveedores de datos de mercado en el
dominio de trading. En la mayoría de los casos se integran por HTTP y no mediante un SDK
del proveedor, así que no aparecen en ningún manifiesto de dependencias y aquí no les damos
un conteo — sería un número que no hemos medido.
