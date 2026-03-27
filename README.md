# 🤖 DERWIN — Mentor Conceptual del Lenguaje ADSO

> **Versión:** 1.0-BETA  
> 
> **Estado:** Experimental
> 
> **Motor Lógico:** `knowledge`

DERWIN es un asistente de orientación conceptual diseñado para acompañar a los equipos durante la competencia **ADSO CODE** del Centro de Formación SENA. A diferencia de un asistente técnico convencional, DERWIN opera bajo una filosofía de **"Acompañamiento sin Ventaja"** — responde únicamente desde el entendimiento conceptual, garantizando equidad absoluta entre los equipos participantes.

---

## 🎯 Objetivo del GPT

Acompañar conceptualmente a los equipos durante las fases de la competencia: Análisis, Desarrollo y Cierre. DERWIN no genera código, no sugiere implementaciones ni favorece a ningún equipo. Su propósito es formar criterio, no resolver el reto.

---

## 🛠 Arquitectura del Proyecto

El proyecto se divide en tres capas fundamentales:

1. **Capa de Identidad (`derwin_instructions.md`):** Define el system prompt, la personalidad de DERWIN, las reglas de equidad, el manejo emocional por situación y la lógica condicional de fases.

2. **Capa de Contexto (Knowledge Files):**
   - `adso_code_algoritmo.docx` — Especificación técnica del lenguaje ADSO.
   - `adso_code_presentacion.docx` — Formato completo de la competencia: roles, fases, restricciones y puntuación.
   - `current_phase.md` — Variable de fase activa. Se reemplaza manualmente antes de cada fase.

3. **Capa de Entrada (`conversation_starters.json`):** Los cuatro disparadores predefinidos que orientan al usuario según su rol en la competencia.

---

## 🚀 Cómo opera DERWIN durante la competencia

Antes de cada fase, el organizador reemplaza el archivo `current_phase.md` en el Knowledge del GPT con el valor correspondiente:

| Momento | Valor en `current_phase.md` |
|---|---|
| Antes de iniciar | `FASE: SIN INICIAR` |
| Fase de Análisis | `FASE: ANALISIS` |
| Fase de Desarrollo | `FASE: DESARROLLO` |
| Fase de Cierre | `FASE: CIERRE` |

DERWIN lee ese archivo antes de responder cualquier mensaje y ajusta su tono, urgencia y prioridades según la fase activa.

---

## 💬 Conversation Starters

Los cuatro puntos de entrada predefinidos según el perfil del usuario:

- **Tester:** *"Soy el Tester del equipo y no tengo claro qué debo documentar."*
- **Líder:** *"Soy el Líder y no sé cómo preparar el pitch final."*
- **Conceptual:** *"No termino de entender cómo funciona una instrucción del lenguaje."*
- **Desarrollo:** *"Estamos en desarrollo y hay algo que no nos está quedando claro."*

---

## ⚖️ Reglas de Oro

- **Solo el Líder puede consultar a DERWIN** — es el único rol autorizado a usar el segundo computador durante la competencia.
- **Sin código:** DERWIN no lee, no analiza ni comenta código pegado en la conversación.
- **Sin ventaja:** Cualquier respuesta que favorezca a un equipo sobre otro está bloqueada por diseño.
- **Neutralidad de lenguaje:** DERWIN no recomienda ningún lenguaje de programación. Esa decisión es del equipo.

---

## 📁 Archivos del repositorio

```
instructions.md - Instrucciones del GPT
conversation_starters.json - Conversaciones iniciales
current_phase.md - Fase actual de ejecución
README.md - Documentación del proyecto
adso_code_algoritmo.docx - Algoritmo que se empleará en la competencia
adso_code_presentacion.docx - Presentación que se empleará en la competencia
programa_prueba1.txt - Archivo de entrada 1
programa_prueba2.txt - Archivo de entrada 2
programa_prueba3.txt - Archivo de entrada 3
DerwinWorkflow.png - Flujo de trabajo del GPT
avatar-large.png - Avatar en su formato cuerpo completo
avatar-short.png - Avatar recortado en formato perfil
avatar.md - Propmt utilizado para generar el avatar
```

---

*Desarrollado para la competencia ADSO CODE — Centro de Formación SENA · Tecnología ADSO · Floridablanca, Santander.*