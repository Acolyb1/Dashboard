# Panel de energía · StockWatcher

Dashboard personal que monitorea en tiempo casi real un grupo de acciones del
sector energético (y algunas apuestas de bajo precio con potencial), pensado
para seguimiento propio — **no es un producto financiero ni asesoría de
inversión**.

🔗 **Dashboard en vivo:** https://acolyb1.github.io/Dashboard/

## ¿Qué muestra?

- **Tasa de cambio USD → COP**, resaltada arriba de todo.
- **Cinta de tickers** con el precio y variación del día de cada activo.
- **Gráfico de tendencia combinada**: variación % de todos los activos desde
  el primer día en que se empezaron a monitorear, en un solo gráfico
  (indexado a 0%, para poder comparar acciones con precios muy distintos).
  Pasa el mouse sobre un ticker para resaltar su línea.
- **Tabla resumen** con precio, variación del día, variación desde el inicio,
  RSI y P/E de cada activo, ordenada por la que más se movió.
- **Tarjetas por activo** con:
  - Precio actual y variación vs la apertura del día.
  - Precio de referencia desde que se empezó a monitorear.
  - Indicadores técnicos: RSI (14), tendencia por medias móviles (SMA 20/50),
    posición dentro del rango de 52 semanas, y P/E actual/proyectado.

## Activos monitoreados

| Símbolo | Empresa | Sector |
|---|---|---|
| BYDDF | BYD Co., Ltd. | EV / Baterías |
| IESFY | Interconexión Eléctrica S.A. (ISA) | Transmisión Eléctrica |
| EC | Ecopetrol S.A. | Petróleo & Gas |
| CIB | Grupo Cibest S.A. | Financiero |
| CEG | Constellation Energy Corporation | Energía Nuclear |
| CCJ | Cameco Corporation | Uranio |
| FSLR | First Solar, Inc. | Energía Solar |
| NEE | NextEra Energy, Inc. | Utilities / Renovables |
| PBR | Petróleo Brasileiro S.A. (Petrobras) | Petróleo & Gas |
| VST | Vistra Corp. | Generación Eléctrica |
| AMTX | Aemetis, Inc. | Biocombustibles |
| DNN | Denison Mines Corp. | Uranio |
| ENVX | Enovix Corporation | Baterías (ánodo de silicio) |
| CLNE | Clean Energy Fuels Corp. | Gas Natural Renovable |
| AMPY | Amplify Energy Corp. | Petróleo & Gas (small-cap) |

## ¿Cómo funciona?

Un script en Python corre localmente cada 15 minutos (lunes a viernes, en
horario de mercado) y hace todo el trabajo:

1. Descarga precios e históricos vía Yahoo Finance.
2. Calcula los indicadores técnicos y de valoración.
3. Si algún activo se mueve más de ±3% respecto a su apertura del día, envía
   una alerta por correo (una sola vez por activo por día).
4. Regenera este dashboard y lo publica automáticamente aquí.

Además, todos los lunes se envía por correo un resumen de las noticias más
recientes de cada empresa monitoreada, junto con el link a este dashboard.

## Aviso importante

Los indicadores técnicos y de valoración que se muestran (RSI, medias
móviles, MACD, P/E, rango de 52 semanas, etc.) son **puramente informativos**.
No constituyen una recomendación de compra ni de venta, ni asesoría
financiera de ningún tipo. Los datos provienen de Yahoo Finance y pueden
tener retraso. Toda decisión de inversión es responsabilidad exclusiva de
quien la toma.
