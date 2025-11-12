# RFQ.IO — API v0 (sin AP)

## auth
R0 sin auth (endpoints internos). luego supabase auth.

## endpoints

### POST /api/rfqs
crea rfq y corre triage AI.
body:
{ "cliente": {"nombre":"", "wa":"", "email":""}, "texto":"", "archivos":["url1"] }
res:
{ "rfq_id":"RFQ-0001", "categoria":"iluminacion|cables", "spec_json":{...}, "faltantes":[] }

### POST /api/rfqs/:id/invite
genera links unicos para proveedores.
body:
{ "suppliers":["sup_1","sup_2"], "expires_at":"2025-12-31T23:59:59Z" }
res:
{ "invites":[{"supplier_id":"sup_1","link":"https://.../bid?t=...","expires_at":"..."}] }

### POST /api/bids
proveedor envia oferta.
body:
{ "rfq_id":"RFQ-0001","token":"...","marca_modelo":"...","precio":1080000,"iva_pct":19,"precio_total":1285200,"lead_days":5,"garantia_meses":12,"files":["url_ficha.pdf"],"notas":"" }
res:
{ "bid_id":"bid_123","cumple":true,"motivos":[],"gaps":[] }

### GET /api/comparatives/:rfq_id
tabla + score y link pdf.
res:
{ "rfq_id":"RFQ-0001","items":[{"supplier":"sup_1","precio_total":1285200,"lead_days":5,"garantia_meses":12,"cumple":true,"score":0.86}], "pdf_url":"https://.../RFQ-0001.pdf" }

## scoring
P_norm = min(precio_total)/precio_total  
T_norm = min(lead_days)/lead_days  
G_norm = garantia_meses/max(garantia_meses)  
score = 0.5*P_norm + 0.3*T_norm + 0.2*G_norm
