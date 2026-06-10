# Plantilla Oficial de Proyectos — Contraloría General de la República

[![Estándar Institucional](https://img.shields.io/badge/Est%C3%A1ndar-CGR--Obligatorio-blue.svg)](https://www.contraloria.gob)
[![Gobernanza Digital](https://img.shields.io/badge/Gobernanza-Software%20P%C3%BAblico-green.svg)]()
[![Cumplimiento Normativo](https://img.shields.io/badge/Cumplimiento-Legal%20%26%20Auditable-orange.svg)]()

Este repositorio constituye el **modelo técnico y normativo de referencia** para la creación, organización y despliegue de proyectos de desarrollo de software dentro de la Contraloría General de la República. 

Su propósito principal es garantizar la uniformidad de las arquitecturas digitales, la transparencia en la gestión de código público, la trazabilidad en los procesos de fiscalización y el estricto cumplimiento de los lineamientos legales e institucionales vigentes desde el primer día de desarrollo.

---

## 🏛️ Objetivos de la Plantilla

*   **Estandarización Organizacional:** Homogeneizar la estructura de directorios y la documentación técnica para simplificar la transferencia de conocimiento y el mantenimiento del software.
*   **Gobernanza y Cumplimiento Legal:** Integrar de manera nativa los términos de uso, licencias y políticas de privacidad obligatorias para la administración pública.
*   **Auditoría y Fiscalización:** Facilitar la revisión de código (*Pull Requests*), el control de cambios interno y la fiscalización de los activos tecnológicos de la institución.
*   **Optimización del Ciclo de Vida:** Reducir los tiempos de configuración inicial (*setup*) de nuevos proyectos mediante un ecosistema preconfigurado.

---

## 📂 Estructura de Carpetas del Repositorio

Todo proyecto derivado de esta plantilla debe mantener rigurosamente la siguiente anatomía de archivos y directorios:

```text
plantilla-oficial-proyectos/
├── .github/                         # Configuración de gobernanza y automatización en GitHub
│   ├── ISSUE_TEMPLATE/              # Plantillas obligatorias para el reporte de incidencias
│   │   ├── reporte_error.md         # Formato para reportar fallos técnicos (Bugs)
│   │   └── solicitud_mejora.md      # Formato para proponer nuevas funcionalidades
│   ├── PULL_REQUEST_TEMPLATE.md     # Lista de verificación de control de calidad antes de fusionar código
│   └── CONTRIBUTING.md              # Normas de colaboración, estilo de código y flujos de trabajo
├── config/                          # Parámetros de configuración del sistema (sin credenciales)
├── docs/                            # Documentación técnica, legal y funcional extendida
│   ├── arquitectura.md              # Diagramas, decisiones de diseño técnico y componentes
│   ├── modelo_datos.md              # Esquemas de bases de datos, diccionarios de datos y entidades
│   └── terminos_y_condiciones.md    # Marco legal, uso aceptable y protección de datos institucionales
├── src/                             # Código fuente principal del proyecto organizado por módulos
│   ├── api/                         # Capa de servicios, endpoints y controladores expuestos
│   ├── core/                        # Lógica de negocio central, validaciones y reglas institucionales
│   └── utils/                       # Funciones utilitarias, formateadores y herramientas comunes
├── tests/                           # Batería de pruebas automatizadas
│   ├── unitarias/                   # Pruebas de componentes individuales y funciones aisladas
│   └── integracion/                 # Pruebas de flujos completos y comunicación entre módulos
├── .env.example                     # Plantilla estructurada de variables de entorno (sin valores sensibles)
├── .gitignore                       # Filtros oficiales para evitar la fuga de archivos temporales o credenciales
├── CODE_OF_CONDUCT.md               # Código de conducta y ética para los equipos de desarrollo
├── LICENSE                          # Licencia de software público / Licencia institucional
└── README.md                        # Este documento (Manual de inducción del proyecto)
```

---

## 📑 Datos Básicos Obligatorios del Proyecto

El archivo `README.md` de cada proyecto derivado **debe ser editado obligatoriamente** para proveer la siguiente información estructurada:

### 1. Datos de Identificación General
*   **Nombre del Proyecto:** Nombre técnico y comercial de la solución.
*   **Código Interno de Sistema:** Identificador asignado por la Dirección de Tecnología o el área encargada.
*   **Área Propietaria / Solicitante:** Departamento, División o Unidad de la Contraloría responsable del producto.
*   **Líder Técnico / Responsable:** Nombre y correo institucional del administrador del repositorio.

### 2. Stack Tecnológico y Requisitos Mínimos
Detallar las versiones específicas utilizadas en el entorno (ej. *Node.js v18.x*, *Python 3.11*, *PostgreSQL 15*).

### 3. Diccionario y Modelo de Datos
Cada desarrollo que manipule persistencia de datos debe documentar en `docs/modelo_datos.md`:
*   Diagrama Entidad-Relación (DER) actualizado.
*   Clasificación de datos según su confidencialidad (Públicos, Reservados, Sensibles).
*   Estrategias de enmascaramiento o anonimización aplicadas para el cumplimiento del secreto institucional o leyes de protección de datos personales.

---

## ⚙️ Instrucciones de Despliegue y Desarrollo Local

### 1. Clonación e Inicio
Para iniciar un nuevo proyecto utilizando esta estructura estándar, haga clic en el botón **"Use this template"** en GitHub, o ejecute localmente:
```bash
git clone https://github.com/tu-organizacion/plantilla-oficial-proyectos.git mi-nuevo-proyecto
cd mi-nuevo-proyecto
```

### 2. Configuración del Entorno
Duplique el archivo de variables de entorno de ejemplo y configure los parámetros locales. **Nunca** suba el archivo `.env` final al repositorio.
```bash
cp .env.example .env
```

### 3. Ejecución en Desarrollo
*(El equipo de desarrollo debe documentar aquí los comandos exactos de inicialización, por ejemplo:)*
```bash
npm install && npm run dev
# o para entornos en Python
pip install -r requirements.txt && python main.py
```

---

## ⚖️ Marco Legal, Términos y Condiciones

Cualquier software desarrollado bajo esta estructura queda sujeto a las normativas de la Contraloría General de la República:
1.  **Propiedad del Código:** Salvo que se indique explícitamente lo contrario, todo el código fuente es propiedad intelectual del Estado / Contraloría General de la República.
2.  **Seguridad de la Información:** Queda estrictamente prohibido almacenar credenciales, llaves API, contraseñas o datos reales de ciudadanos/funcionarios dentro del repositorio de código. Todo acceso debe ser gestionado mediante bóvedas de secretos oficiales (Vaults) y variables de entorno seguras.
3.  **Términos Extendidos:** Para consultar el desglose sobre propiedad intelectual, límites de responsabilidad y tratamiento de datos institucionales, refiérase al archivo [docs/terminos_y_condiciones.md](docs/terminos_y_condiciones.md).

---

## 🤝 Contribución y Control de Calidad

Para mantener la integridad institucional del código, el flujo de trabajo exige:
1.  **Ramas de Trabajo:** Está prohibido realizar confirmaciones (*commits*) directas a la rama `main` o `master`. Todo cambio debe realizarse en ramas temáticas (`feature/`, `bugfix/`, `hotfix/`).
2.  **Revisión de Código:** Todo cambio debe pasar por un proceso de *Pull Request* (PR) y requiere la aprobación obligatoria de al menos un Líder Técnico o Arquitecto de Software asignado, verificando el cumplimiento del [PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md).
3.  **Pruebas Automatizadas:** Ninguna funcionalidad será integrada a la r