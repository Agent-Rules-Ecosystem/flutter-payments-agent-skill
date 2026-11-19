# Patrones Seguros — Pagos en Flutter 3+

## 1. Ciclo Seguro de `in_app_purchase`
1. Inicializar listener de `purchaseStream` en `main()` o bootstrap de sesión.
2. Enviar `verificationData.serverVerificationData` al backend.
3. Solo tras respuesta `200 OK` del backend, invocar `completePurchase(purchase)`.

## 2. RevenueCat (`purchases_flutter`)
Usar `Purchases.getCustomerInfo()` y `addCustomerInfoUpdateListener` consultando `entitlements.active[id]?.isActive == true`.

## 3. Stripe `PaymentSheet`
El backend crea el `PaymentIntent` con `idempotencyKey` y devuelve `clientSecret`; Flutter solo presenta `Stripe.instance.presentPaymentSheet()`.
