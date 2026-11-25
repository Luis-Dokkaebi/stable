# Paymexbtc Core · demo del enjambre de 33 agentes

Mock funcional para inversionistas. Un solo archivo (`index.html`), sin build ni dependencias.

```bash
open app/index.html        # o: python3 -m http.server -d app 8080
```

## Qué hace

- Grafo estilo Obsidian (canvas + simulación de fuerzas) con los 33 agentes AG-01…AG-33, los agentes de flujo IA1, IA1.1, IA2, IA2.1, IA3, IA3.3, IA Proveedores y los actores (cliente, exchange MX, proveedor HK).
- Las conexiones se encienden una a una conforme cada agente actúa, desde la compra de 20 playeras hasta el sello del expediente. Al cierre, AG-33 conecta la malla completa (528 enlaces 33×33).
- Cálculos reales sobre datos de demo: cotización MXN→USDT/USDC, selección de red por costo/latencia, validación de wallet EVM/Solana, dígito verificador de CLABE, umbral LFPIORPI en UMA, IGI/DTA/IVA o tasa global de paquetería, hoja NIF C-22, póliza cuadrada, SHA-256 por documento y raíz Merkle.
- Controles que bloquean el flujo: RFC/CURP inválidos (AG-07), wallet inválida o red incompatible (AG-12). Alertas: UIF (AG-22), anomalías (AG-26), límites (AG-29), presunción comercial en paquetería (IA Proveedores).
- 8 agentes autoevolutivos (AG-08, 11, 13, 17, 19, 22, 26, 30) guardan memoria entre corridas en `localStorage`.

Todo es simulado: TXID, SPEI, pedimentos y documentos no tienen validez legal. Tasas y umbrales son editables y deben confirmarse con el agente aduanal y el oficial de cumplimiento.

## Despliegue

Producción: https://paymexbtc-core.vercel.app

El proyecto `paymexbtc-core` en Vercel está conectado a este repositorio. Cada push a la rama de producción (`claude/peaceful-euler-etfs5e`) redepliega solo. Los pushes a otras ramas generan deployments de preview.
