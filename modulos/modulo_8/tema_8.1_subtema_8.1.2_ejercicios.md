# Ejercicios: Gobernanza

## Ejercicio: Efecto de Política

Quieres aplicar una política estricta para que NINGÚN desarrollador pueda crear una IP Pública (Pip) directamente en una máquina virtual (para forzarlos a usar Load Balancers o VPN).

¿Qué efecto usas?

* [ ] Audit
* [x] Deny
* [ ] Disabled

**Respuesta**: Deny.

## Ejercicio: Secure Score

Tu jefe te dice: "Nuestro Secure Score en Azure es del 30%. Necesitamos subirlo al 80% este mes".
Entras a Defender for Cloud y ves estas recomendaciones. Ordena por impacto (cuál sube más el puntaje rápido):

A. Activar MFA para cuentas con permisos de Owner (10 puntos).
B. Habilitar logs de diagnóstico para un servicio que no usamos (1 punto).
C. Restringir acceso a puertos de gestión (SSH/RDP) en VMs expuestas a internet (8 puntos).

**Prioridad**: A, C, B.

## Ejercicio: JSON Policy

Completa el JSON para permitir solo VMs de tamaño pequeño (para ahorrar costos en Dev).

```json
{
  "if": {
    "field": "type",
    "equals": "Microsoft.Compute/virtualMachines"
  },
  "then": {
    "effect": "Deny",
    "details": {
      "type": "Microsoft.Compute/virtualMachines/sku",
      "notIn": ["Standard_B1s", "Standard_B2s"]
    }
  }
}
```
