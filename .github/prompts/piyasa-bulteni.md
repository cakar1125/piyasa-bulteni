# Piyasa Bülteni - Pro Analist
# GRUP A — Pazartesi, Çarşamba, Cuma, Pazar | 09:00 UTC (12:00 İstanbul)

Bugünün tarihini belirle (YYYY-MM-DD formatında). Günlük kripto/piyasa bülteni hazırla.

NOT: Repo zaten mevcut dizinde. git komutu KULLANMA. Dosyaları write_file aracıyla yaz.

## ADIM 1 — Önceki raporları oku

list_files ile bultenler/ klasörünü kontrol et. Son 3 raporu read_file ile oku. Önceki AL/SAT/BEKLE kararlarını not al.

## ADIM 2 — API verilerini çek

fetch_url ile şunları al:
- `https://api.alternative.me/fng/?limit=1`
- `https://api.coingecko.com/api/v3/global`
- `https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=bitcoin,ethereum,solana,binancecoin&order=market_cap_desc&sparkline=false`
- `https://api.coingecko.com/api/v3/search/trending`
- `https://fapi.binance.com/fapi/v1/fundingRate?symbol=BTCUSDT&limit=1`
- `https://fapi.binance.com/fapi/v1/openInterest?symbol=BTCUSDT`

## ADIM 3 — Web araması

web_search ile şunları ara:
- "bitcoin market today"
- "crypto news today"
- "BTC ETF inflows today"

## ADIM 4 — Confluence analizi

Her gösterge: Boğa +1 / Ayı -1 / Nötr 0. Net toplam: >+3 = BOĞA, <-3 = AYI, arası = NÖTR.

## ADIM 5 — Raporu yaz

write_file ile `bultenler/YYYY-MM-DD_piyasa-bulteni.md` dosyasını oluştur:

```
# [YYYY-MM-DD] Piyasa Bülteni

## 30 Saniyelik Özet
[2 cümle makro görünüm]

## Confluence Tablosu
| Gösterge | Değer | Sinyal | Ağırlık |
|---|---|---|---|
| Fear & Greed | X | 🔴/🟢/🟡 Açıklama | Yüksek |
| BTC Dominance | X% | ... | Orta |
| Funding Rate | X% | ... | Yüksek |
| Open Interest | $XB | ... | Yüksek |
| Global Market Cap | $XT | ... | Orta |
| Haber Tonu | ... | ... | Düşük |

**Net Skor: X → [BOĞA/AYI/NÖTR]**

## Coin Kararları
### BTC — [AL/SAT/BEKLE] (%XX güven)
Sebep: [1-2 cümle]
Önceki karar: [önceki] → Doğru muydu? [evet/hayır/belirsiz]

### ETH — [AL/SAT/BEKLE] (%XX güven)
### SOL — [AL/SAT/BEKLE] (%XX güven)
### BNB — [AL/SAT/BEKLE] (%XX güven)

## Trending Coinler
[Top 3 trending + kısa yorum]
```
