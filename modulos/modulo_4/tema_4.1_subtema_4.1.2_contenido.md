# Quality Gates y Reglas

## 1. Quality Profiles (Perfiles de Calidad)

Un perfil define **qué reglas** se aplican a tu proyecto.

* **SonarWay**: El perfil por defecto. Recomendado para empezar.
* **Custom**: Puedes crear tu propio perfil. "Quiero activar la regla de complejidad ciclomática estricta pero ignorar la de logs".

## 2. Quality Gates (Umbrales de Calidad)

Un Quality Gate responde a la pregunta: **¿Es este código apto para producción? (Pass/Fail)**.
Se basa en métricas sobre **Código Nuevo** (New Code). Esto es vital: No te exige arreglar la deuda técnica de hace 10 años, pero te exige que lo que escribiste *hoy* esté limpio.

### Condiciones típicas de un Quality Gate

* Coverage on New Code >= 80%
* Duplicated Lines on New Code < 3%
* Security Review Rating on New Code is A (Sin vulnerabilidades nuevas).
* Maintainability Rating on New Code is A.

## 3. Clean as You Code

Es la filosofía detrás de SonarQube.

* No intentes arreglar todo el código legado de golpe (te frustrarás).
* Enfócate en que el **Leak Period** (el código nuevo) esté inmaculado.
* Con el tiempo, el código viejo se refactoriza o se borra, y la calidad global sube sola.
