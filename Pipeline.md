# 🚀 **Guía completa de implementación (GPT + pipeline automático)**

## 🧩 **Estructura general del proceso**

| Fase | Nombre                                         | Objetivo                                           | Input                   | Output                              |
| ---- | ---------------------------------------------- | -------------------------------------------------- | ----------------------- | ----------------------------------- |
| 0️⃣  | **Conversión del Roadmap a JSON estructurado** | Convertir el roadmap Markdown a un esquema JSON    | Markdown (`roadmap.md`) | `curso.yaml` o `curso.json`         |
| 1️⃣  | **Definición del temario detallado**           | Expandir roadmap a un temario completo             | JSON del curso          | `temario.md`                        |
| 2️⃣  | **Desglose paso a paso**                       | Crear preconceptos, temas y relaciones entre ellos | `temario.md`            | `mapa_conceptual.md`                |
| 3️⃣  | **Generación modular del curso**               | Crear módulos, semanas, y objetivos                | `mapa_conceptual.md`    | Carpeta `/modulos` con `.md`        |
| 4️⃣  | **Desarrollo del contenido**                   | Desarrollar contenido pedagógico completo          | `/modulos`              | Curso completo listo para versionar |
| 5️⃣  | **Validación de métricas de calidad**          | Revisar estructura, coherencia y estándares        | Curso completo          | Reporte de validación               |

---

## 🧠 **Paso 0 — Convertir Roadmap en JSON estructurado**

**Objetivo:** convertir un roadmap en Markdown a una estructura de curso en JSON/YAML lista para alimentar la plantilla `curso.yaml`.

### Prompt sugerido:

```text
Convierte el siguiente roadmap Markdown en una estructura JSON siguiendo este esquema:

{
"curso": {
    "nombre": "",
    "descripcion": "",
    "estado": "EN_DESARROLLO | COMPLETADO",
    "fases": [
    {
        "nombre": "fase 0 - ...",
        "tipo": "Conceptual | Técnico | Hands-on",
        "duracion_horas": 0,
        "descripcion": "",
        "semanas": [
        {
            "nombre": "",
            "duracion_horas": 0,
            "modulos": [
            {
                "titulo": "",
                "tipo": "Conceptual | Técnico | Hands-on",
                "objetivos": [],
                "archivos": []
            }
            ]
        }
        ]
    }...
    ],
    "metricas": {
    "numero_archivos": 0,
    "numero_modulos": 0,
    "numero_labs": 0
    }
}
}

Entrada (roadmap Markdown):
---
[pega aquí tu roadmap completo en formato Markdown]
---
```

💡 *Consejo:* Guarda el resultado como `curso.json` y valida con un parser (por ejemplo, en VSCode o `jq`).

---

## 📘 **Paso 1 — Generar el temario detallado**

**Objetivo:** expandir el roadmap en un temario con objetivos semanales y horas estimadas.

### Prompt:

```text
Toma el siguiente JSON de curso y genera un documento `temario.md` con la siguiente estructura:
- Título del curso
- Propósito
- Tabla con semanas (nombre, duración, tipo de contenido)
- Objetivos por semana (6–8 verbos medibles)
- Indicadores de progreso

Entrada: [pega aquí curso.json]
```

---

## 🧩 **Paso 2 — Crear mapa conceptual y preconceptos**

**Objetivo:** definir dependencias entre temas y explicar cómo evolucionan las competencias.

### Prompt:

```text
A partir del siguiente temario, genera un mapa conceptual que describa:
- Preconceptos requeridos
- Relaciones entre temas
- Progresión cognitiva (de básico a avanzado)
- Competencias que se adquieren en cada etapa

Entrada: [pega aquí temario.md]
Salida: `mapa_conceptual.md`
```

---

## 🧱 **Paso 3 — Generación modular del curso**

**Objetivo:** crear los módulos, semanas y objetivos a partir del mapa conceptual.

### Prompt:

```text
Usando el siguiente mapa conceptual, genera una estructura de carpetas y archivos Markdown:
- `/modulos/01-introduccion.md`
- `/modulos/02-fundamentos.md`
- `/modulos/03-practicas.md`
Cada archivo debe tener:
- Título descriptivo
- Objetivos del módulo
- Descripción
- Ejemplos prácticos
- Referencias

Entrada: [mapa_conceptual.md]
```

📁 **Salida esperada:**

```plaintext
/curso/
├── README.md
├── curso.yaml
├── temario.md
├── mapa_conceptual.md
├── /modulos/
│    ├── 01-introduccion.md
│    ├── 02-fundamentos.md
│    └── 03-practicas.md
└── /recursos/
    └── bibliografia.md
```

---

## 📘 **Paso 4 — Desarrollo del contenido**

**Objetivo:** completar los módulos con explicaciones, ejemplos, y hands-on labs.

### Prompt:

```text
Genera el contenido detallado del siguiente módulo Markdown, siguiendo el formato definido en el README principal (estructura cognitiva, tono profesional, ejemplos reales, y referencias).

Entrada: [contenido base del módulo]
```

---

## 🧮 **Paso 5 — Validación de métricas de calidad**

**Objetivo:** revisar que el curso cumple con los estándares definidos.

### Prompt:

```text
Evalúa el curso según las siguientes métricas de calidad:
1. Estructura completa (README, temario, módulos)
2. Claridad de objetivos (verbos medibles)
3. Cohesión cognitiva (progresión lógica)
4. Formato visual coherente (Markdown)
5. Métricas de completitud (número de módulos, horas, labs)
6. Navegación y enlaces correctos
7. Licencia y metadata

Entrada: estructura del curso (JSON + carpetas)
Salida: reporte de validación con puntuación 0–100
```

---

## ⚙️ **Automatización del pipeline**

Si lo integras en GitHub o una LMS:

1. **Commit del roadmap.md**

   * Trigger: `on: push` → ejecuta script

2. **Conversión automática**

    ```bash
    python scripts/convert_roadmap_to_json.py roadmap.md curso.json
    ```

3. **Generación del temario**

    ```bash
    gpt-cli run "prompts/generar_temario.txt" --input curso.json --output temario.md
    ```

4. **Desglose modular**

    ```bash
    gpt-cli run "prompts/generar_modulos.txt" --input mapa_conceptual.md --output modulos/
    ```

5. **Validación final**

    ```bash
    gpt-cli run "prompts/validar_curso.txt" --input curso/
    ```

---
