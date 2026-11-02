---
# METADATOS DEL EXPERIMENTO (eLabFTW Header)
title: "EXP-BM-2026-088: Aislamiento de ARN y Síntesis de ADNc"
category: "Biología Molecular"
tags: [arn-seq, rt-pcr, extraccion-arn, cdna]
status: "En Curso"
privacy: "Restringido (Solo Grupo de Investigación)"
---

## 1. Información General y Control de Cambios

| Parámetro | Detalle |
| :--- | :--- |
| **Investigador Principal** | Dra. Clara Morales |
| **Ejecutado por** | Msc. Carlos Mendoza |
| **Proyecto Vinculado** | PRJ-2026-CANCER-MAMA (`#PRJ-004`) |
| **Fecha de Inicio** | 2026-10-26 |
| **Lugar de Ejecución** | Cabina de Flujo Laminar II B (Lab 302) |

---

## 2. Reactivos, Equipos e Inventario (Trazabilidad eLabFTW)

> 💡 *Usa los enlaces de ítems internos de eLabFTW para vincular los números de lote y ubicaciones exactas.*

### Reactivos e Insumos
- [x] **Kit de Extracción:** RNeasy Mini Kit (Qiagen) | **Lote:** `#QG-984211` | **Caducidad:** 2027-04
- [x] **Enzima Reverse Transcriptase:** SuperScript IV | **Lote:** `#INV-8820` | **Almacén:** Congelador -20°C (Caja A-4)
- [x] **Control RNasa/DNasa:** Nuclease-Free Water (Ambion) | **Lote:** `#AM-0012`

### Equipos Calibrados
- **Centrífuga Refrigerada:** Eppendorf 5424 R (ID: `EQ-CENT-02`)
- **Espectrofotómetro:** NanoDrop One (ID: `EQ-ND-01`)
- **Termociclador:** Bio-Rad T100 (ID: `EQ-TC-03`)

---

## 3. Protocolo Paso a Paso (SOP-BM-012 v2)

### Fase A: Lisis de Muestras e Extracción de ARN
1. Resuspender la muestra de tejido celular en **600 µL de Buffer RLT** adicionado con 10 µL/mL de $\beta$-mercaptoetanol.
2. Homogeneizar mediante vórtex a máxima velocidad por **30 segundos**.
3. Añadir 1 volumen de etanol al 70% y centrifugar en columna RNeasy a **8,000 x g** durante **15 segundos**.
4. Realizar lavados secuenciales con buffers RW1 (350 µL) y RPE (500 µL).
5. Eluir el ARN purificado en **30 µL de agua libre de nucleasas**.

### Fase B: Síntesis de ADNc (Retrotranscripción)
Mezclar los siguientes componentes en microtubos PCR estériles de 0.2 mL:

| Componente | Concentración Inicial | Volumen por Reacción (µL) |
| :--- | :--- | :--- |
| ARN Molde | ~500 ng/µL | 2.0 |
| Oligo(dT)18 primer | 50 µM | 1.0 |
| dNTP Mix | 10 mM c/u | 1.0 |
| Nuclease-Free Water | — | 9.0 |
| **Subtotal** | | **13.0** |

*Incubar a 65°C por 5 minutos y enfriar inmediatamente en hielo por al menos 1 minuto.*

Añadir la mezcla enzimática final:
- 5X SSIV Buffer: **4.0 µL**
- DTT (100 mM): **1.0 µL**
- RNaseOUT Inhibitor: **1.0 µL**
- SuperScript IV RT (200 U/µL): **1.0 µL**

**Programa del Termociclador:**
- 23°C durante 10 min (Anidamiento)
- 50°C durante 10 min (Extensión/Síntesis)
- 80°C durante 10 min (Inactivación Enzimática)

---

## 4. Control de Calidad y Resultados Brutos

### Pureza y Concentración (NanoDrop)

| Muestra ID | Conc. (ng/µL) | Ratio $A_{260/280}$ | Ratio $A_{260/230}$ | Estado QC |
| :--- | :--- | :--- | :--- | :--- |
| M-2026-001 | 485.2 | 2.05 | 2.12 | Aprobado |
| M-2026-002 | 512.0 | 2.02 | 1.98 | Aprobado |
| Control (-) | 1.2 | 1.15 | 0.42 | N/A (Negativo) |

### Archivos de Datos Adjuntos

- 📁 [20261026_nanodrop_raw_export.csv](/data/20261026/20261026_nanodrop_raw_export.csv) *(Exportación directa de equipo)*
- 🖼️ [20261026_bioanalyzer_RNA_integrity.png](/assets/20261026/20261026_bioanalyzer_RNA_integrity.png) *(Comprobación RIN = 9.2)*

---

## 5. Firmas y Cierre de Auditoría

> 🔒 **Firma Digital eLabFTW:**
>
> - **Estado:** Firmado y Bloqueado contra modificaciones.
> - **Firmado por:** Ms. Timna Bergmann
> - **Hash SHA-256:** `9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08`
> - **Marca de Tiempo:** 2026-10-26 T 17:42:01 CEST