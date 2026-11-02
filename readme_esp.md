# Guía Estándar para Estructuración y Documentación de Proyectos de Biología Molecular

Este repositorio establece la estructura de archivos, el flujo de trabajo y las normas de documentación digital recomendadas para proyectos de investigación en biología molecular, garantizando la trazabilidad, reproducibilidad y el cumplimiento de los principios **FAIR** (*Findable, Accessible, Interoperability, Reusable*).

---

## 1. Estructura General del Repositorio

La siguiente arquitectura de carpetas organiza el almacenamiento de código, protocolos, metadatos y datos experimentales:

```text
lab-molecular-biology/
├── .gitignore                   # Exclusión de datos crudos pesados (>100MB) y archivos temporales
├── README.md                    # Documento principal del proyecto (visión general, normas, equipo)
├── LICENSE                      # Definición de derechos de uso, patentes y propiedad intelectual
│
├── docs/                        # Documentación estática y protocolos operativos (SOPs)
│   ├── sops/                    # Procedimientos Normalizados de Trabajo
│   │   ├── SOP-BM-001_pcr.md
│   │   └── SOP-BM-012_rna_extraction.md
│   └── safety/                  # Hojas de datos de seguridad (MSDS)
│
├── eln_exports/                 # Exportaciones periódicas firmadas (PDF/JSON) desde el ELN (eLabFTW)
│   └── 2026/
│       ├── EXP-BM-2026-087.pdf
│       └── EXP-BM-2026-088.pdf
│
├── data/                        # Gestión de Datos (Organización basada en principios FAIR)
│   ├── raw/                     # DATOS CRUDOS INMUTABLES (Solo lectura)
│   │   ├── sequencing_fastq/    # Archivos brutos de secuenciación (NGS, Sanger)
│   │   └── nanodrop_exports/    # Exportaciones directas de equipos analíticos
│   ├── processed/               # Datos limpios y estructurados para análisis
│   └── metadata/                # Mapeo de muestras, anticuerpos, lotes y fenotipos
│       ├── samples_inventory.csv
│       └── primers_database.json
│
├── src/                         # Código de análisis bioinformático y automatización
│   ├── pipelines/               # Flujos automatizados (Nextflow, Snakemake)
│   │   └── rna_seq_qc.nf
│   ├── python/                  # Funciones personalizadas en Python
│   │   └── parse_nanodrop.py
│   └── R/                       # Scripts de análisis estadístico
│       └── differential_expression.R
│
├── notebooks/                   # Cuadernos computacionales interactivos
│   ├── 01_qc_exploration.ipynb
│   └── 02_deseq2_analysis.Rmd
│
└── results/                     # Entregables finales y figuras para publicación
    ├── figures/                 # Gráficas finales vectoriales (SVG, PDF, PNG high-res)
    └── tables/                  # Tablas procesadas para manuscritos
```

---

## 2. Flujo de Trabajo y Documentación Digital (ELN)

Para mantener la integridad de la investigación, el laboratorio opera bajo las siguientes reglas de documentación:

### 2.1. Registro en la Libreta Electrónica (ELN - eLabFTW / Benchling)
1. **Nomenclatura Estándar:** Todo experimento registrado debe iniciar con el identificador único `EXP-[ÁREA]-[AÑO]-[ID]`, por ejemplo: `EXP-BM-2026-088`.
2. **Uso de Plantillas Estandarizadas:** No se permiten registros en texto plano sin estructura. Todos los registros deben usar las plantillas Markdown predefinidas en la carpeta `docs/sops/`.
3. **Trazabilidad de Reactivos:** Es obligatorio vincular el código de lote (`Lot Number`) de los kits, enzimas, alícuotas y congeladores registrados en el módulo de inventario.
4. **Firma y Inmutabilidad:** Al concluir un experimento, el registro debe ser **firmado digitalmente** en la plataforma ELN. Las modificaciones posteriores deben registrarse en un nuevo expediente complementario.

### 2.2. Gestión de Datos Brutos y Procesados (`data/`)
* **Regla de Inmutabilidad (`data/raw/`):** Los archivos crudos generados directamente por los equipos (secuenciadores, fotómetros, geles) **jamás se editan ni se sobreescriben**.
* **Enlaces Simbólicos y Referencias:** Dado que los archivos de secuenciación pueden superar los gigabytes, el ELN documenta el HASH SHA-256 o el ID de muestra y la ruta física o en la nube del archivo crudo.

### 2.3. Control de Código y Análisis (`src/` & `notebooks/`)
* Todo análisis bioinformático debe ser reproducible mediante scripts en R, Python o canalizaciones tipo Nextflow/Snakemake.
* Las versiones de dependencias y paquetes deben quedar registradas en un archivo de entorno (`environment.yml` o `requirements.txt`).

---

## 3. Manejo de Seguridad y Control de Accesos

Para balancear la necesidad de compartir datos con la protección de la propiedad intelectual y el recelo institucional:

1. **Privacidad Gradual:** Los cuadernos en curso son visibles únicamente por el autor y el Investigador Principal (PI).
2. **Liberación de Protocolos:** Los protocolos estandarizados (SOPs) aprobados se mueven a la categoría "Pública Interna" para el uso del grupo de investigación.
3. **Control de Versiones en Git:** Los datos sensibles o identificadores de pacientes jamás se suben a repositorios públicos (`.gitignore` configurado de manera estricta).

---

## 4. Requisitos para Nuevos Miembros del Laboratorio

Antes de iniciar trabajo experimental en mesa (*wet lab*) o en seco (*dry lab*):
- [ ] Solicitar acceso al ELN institucional (eLabFTW).
- [ ] Clonar este repositorio y verificar la instalación del entorno de software.
- [ ] Revisar los SOPs ubicados en `docs/sops/` correspondientes a su área de trabajo.
- [ ] Realizar un experimento de prueba etiquetando correctamente el inventario de prueba.