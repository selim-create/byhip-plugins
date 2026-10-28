# byhip-plugins

plugin.byhip.studio (GitHub Pages, `main` dalının kökü). Hip Medya sitelerindeki WordPress eklentileri yeni sürümlerini buradan alır.

| Yol | İçerik |
| --- | --- |
| `hip-press-bridge/info.json` | Son sürüm, paket adresi, SHA-256 özeti ve değişiklik notları. Eklenti her sitede günde iki kez buna bakar. |
| `hip-press-bridge/hip-press-bridge-X.Y.Z.zip` | Paket. Eski sürümler de durur. |
| `hip-press-bridge/index.html` | Sürüm sayfası; ilk kurulum için indirme bağlantısı. |
| `hip-monitor-agent/info.json` | HIP Monitor Agent sürümü, ZIP adresi ve SHA-256 doğrulaması. |
| `hip-monitor-agent/hip-monitor-agent-X.Y.Z.zip` | İmzalı isteklerle salt okunur sağlık endpoint'i sunan bağımsız WordPress eklentisi. |
| `hip-monitor-agent/index.html` | Monitor Agent indirme ve sürüm sayfası. |

## Yeni sürüm yayınlama

Dosyalar elle düzenlenmez; hip-space reposunda üretilir:

```
npm run space -- plugin:build --out=../byhip-plugins
npm run space -- plugin:build --plugin=hip-monitor-agent --out=../byhip-plugins
```

Sonra bu repoda commit ve push yapılır. `info.json` yayımlandığında, ilgili güncelleyiciyi içeren eklenti sürümleri yeni sürümü WordPress güncelleme kontrolünde görür. Monitor Agent 0.1.0 otomatik güncelleyici içermez; ilk geçiş elle yapılır. hip.space'te Ayarlar › WordPress › **Hepsini şimdi güncelle** beklemeden başlatır.

Eklenti yalnız `https://plugin.byhip.studio` adresinden ve SHA-256 tutarsa kurulur. Bu yüzden bir ZIP'i yayınladıktan sonra değiştirmeyin; her değişiklik yeni bir sürüm numarasıyla yayınlanır.

## HIP Monitor Agent güvenlik notu

Dağıtım paketinde müşteri anahtarı veya lisansı bulunmaz. Eklentinin kurulması HIP Control'e kendiliğinden erişim vermez; mevcut sürümde site sahibi tarafından ayrı güvenli eşleştirme gerekir. Yeni bir `info.json` sürümü mevcut ZIP'i değiştirmeden yayınlanır.
