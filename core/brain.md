# Brain — Flutter Payments

- **Elección de pasarela**: Contenido digital in-app -> `in_app_purchase` o RevenueCat (`purchases_flutter`); bienes físicos/servicios externos -> `flutter_stripe` (`PaymentSheet`).
- **Auditoría**: `$pay:audit` inspecciona `lib/` buscando secretos, fugas de stream y validación cliente-only.
