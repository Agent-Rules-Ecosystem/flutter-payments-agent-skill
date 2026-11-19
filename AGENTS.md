---
name: flutter-payments-agent-skill
description: In-App Purchases (purchaseStream/completePurchase), RevenueCat entitlements, Stripe PaymentSheet and server-side receipt validation.
---

# Flutter Payments (IAP, RevenueCat & Stripe) Skill — Directiva de Habilidad

## Bootstrap de la Habilidad

Al detectar el trigger `$pay` o archivos del dominio, cargar en orden:
1. `.skill/flutter-payments-agent-skill/SKILL.md`
2. `.skill/flutter-payments-agent-skill/core/commands.md`
3. `.skill/flutter-payments-agent-skill/core/brain.md`
4. `.skill/flutter-payments-agent-skill/core/path_map.md`

## Reglas Canónicas

1. **Validación server-side obligatoria**: Nunca confiar en el estado local del cliente para desbloquear entitlements; validar recibos/webhooks en backend.
2. **Cero llaves secretas en la app**: Solo usar claves publicables (`pk_...` / SDK keys públicas) en Flutter; `sk_...` y `whsec_...` viven únicamente en backend.
3. **Suscribirse a `purchaseStream` en el arranque**: Escuchar compras pendientes al iniciar la app y llamar `completePurchase()` solo tras entregar el beneficio.
4. **Botón obligatorio de Restaurar Compras**: Exigido por App Store Review Guidelines para bienes no consumibles y suscripciones.
5. **Cumplir reglas de tienda**: Bienes digitales consumidos dentro de la app usan IAP nativo (StoreKit / Google Play Billing); Stripe se reserva a bienes físicos o servicios externos.
6. **Inviolabilidad de `.skill/`**: Nunca editar archivos dentro de `.skill/flutter-payments-agent-skill/` desde el proyecto cliente; registrar mejoras en `overview/learning.md` vía `$learnskill flutter-payments-agent-skill [propuesta]`.
