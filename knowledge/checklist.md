# Checklist de Auditoría — `$pay:audit`

- [ ] Cero claves secretas (`sk_`, `whsec_`) en `lib/`, `.env` empaquetado o assets.
- [ ] Recibos/webhooks validados en servidor (nunca confianza ciega en cliente).
- [ ] `purchaseStream` suscrito al inicio y `cancel()` en `dispose()`.
- [ ] `completePurchase()` invocado solo tras entrega confirmada.
- [ ] Flujo de `restorePurchases()` visible en el paywall.
