# RFQ.IO — PRD v0 (sin AP)

## objetivo
entregar al cliente 3–4 ofertas comparables en <4 h habiles, en un PDF con watermark. sin involucrarnos en facturacion ni pagos.

## nicho inicial
iluminacion industrial (high bay, exterior IP65+) y cables especiales (xlpe/thhn).

## propuesta de valor
- comparativo claro: precio, lead time, garantia, cumplimiento tecnico.
- ahorro medible vs precio base (si el cliente lo aporta).
- anti-bypass: comparativo anonimo + alias rfq+id@ + expiracion de links.

## alcance R0
- intake: whatsapp + form web.
- normalizacion AI: extraer 3–5 campos minimos por categoria.
- ofertas: link unico a proveedores con formulario estandar.
- comparativo: grid + score (50% precio, 30% lead, 20% garantia) + export pdf.

## fuera de alcance R0
- facturacion, pagos, AP, integraciones ERP profundas.

## flujo
1) cliente envia requerimiento → triage (AI + humano).
2) invitamos 3–6 proveedores → responden form.
3) generamos comparativo + pdf → cliente elige.

## SLA y metricas
- 2–4 h para 3–4 ofertas validas.
- tiempo mediano a 1a oferta ≤ 90 min.
- respuesta proveedor ≥ 70%.

## pricing v0
- fee por ahorro: 20% del ahorro o 1% del adjudicado (mayor), minimo 199k, tope 2M.

## kpis v0
- ≥ 70% de rfqs con 3+ ofertas <4 h
- ahorro medio 6–10%
- conversion rfq→decision ≥ 30%

## definicion de hecho (DoD R0)
crear rfq, invitar 3–6 proveedores, recibir 3+ ofertas, generar comparativo pdf con score.

## campos minimos por categoria
- luces: lm, IP, CCT, potencia, altura/uso.
- cables: calibre, aislamiento, tension, longitud, uso.
