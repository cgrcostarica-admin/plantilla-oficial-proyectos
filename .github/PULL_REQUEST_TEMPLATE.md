## 🏛️ Plantilla de Pull Request (PR) — Contraloría General de la República

### 📋 Descripción de los Cambios
Este PR implementa el módulo de cruce automatizado para la validación de viáticos y asignaciones de transporte dentro del sistema de auditoría interna de la CGR. Corrige las alertas de inconsistencias generadas al procesar archivos planos institucionales y automatiza la detección de duplicidad en las fechas de comisión.

- **Tipo de cambio:** 
  - [ ] 🐛 Corrección de error (Bugfix)
  - [x] ✨ Nueva funcionalidad (Feature)
  - [x] ⚙️ Refactorización / Optimización (Refactor)
  - [ ] 📄 Documentación (Docs)
  - [ ] 🔒 Parche de Seguridad (Security)
- **ID de la Incidencia / Ticket:** CGR-3042

---

### 🔍 Detalles Técnicos e Impacto
- **Componentes Afectados:** `src/core/auditoria/viaticos`, `src/api/controllers/viaticos.controller.ts`, `docs/modelo_datos.md`.
- **¿Introduce cambios que rompen la compatibilidad hacia atrás?** [ ] Sí  /  [x] No
- *Si la respuesta es sí, describa el plan de migración o contingencia:* N/A

---

### 🧪 Plan de Pruebas y Evidencias
- **Pruebas Realizadas:**
  - [x] Pruebas unitarias ejecutadas exitosamente.
  - [x] Pruebas de integración verificadas en entorno de desarrollo local.
  - [x] Inspección estática de código (Linter / SonarQube) sin alertas críticas.

#### 📊 Evidencias de Funcionamiento:
```text
PASS  src/tests/unitarias/viaticos.test.ts
✓ Debe detectar viáticos duplicados para el mismo funcionario en la misma fecha (12ms)
✓ Debe calcular correctamente la retención según la normativa vigente de la CGR (8ms)

Test Suites: 1 passed, 1 total
Tests:       2 passed, 2 total
Snapshots:   0 total
Time:        1.45s
SonarQube Quality Gate: PASSED (0 Critical Vulnerabilities, Coverage 87.4%)