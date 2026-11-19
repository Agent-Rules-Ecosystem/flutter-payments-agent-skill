# Plantilla Canónica — Servicio de Entitlements (Dart 3)

```dart
sealed class PaymentResult {
  const PaymentResult();
}
final class PaymentSuccess extends PaymentResult { const PaymentSuccess(); }
final class PaymentCancelled extends PaymentResult { const PaymentCancelled(); }
final class PaymentFailed extends PaymentResult {
  const PaymentFailed(this.reason);
  final String reason;
}
```
