# byhip-plugins

plugin.byhip.studio (GitHub Pages, `main` dalının kökü). Hip Medya sitelerindeki WordPress eklentileri yeni sürümlerini buradan alır.

| Yol | İçerik |
| --- | --- |
| `hip-press-bridge/info.json` | Son sürüm, paket adresi, SHA-256 özeti ve değişiklik notları. Eklenti her sitede günde iki kez buna bakar. |
| `hip-press-bridge/hip-press-bridge-X.Y.Z.zip` | Paket. Eski sürümler de durur. |
| `hip-press-bridge/index.html` | Sürüm sayfası; ilk kurulum için indirme bağlantısı. |

## Yeni sürüm yayınlama

Dosyalar elle düzenlenmez; hip-space reposunda üretilir:

```
npm run space -- plugin:build --out=../byhip-plugins
```

Sonra bu repoda commit ve push yapılır. `info.json` değiştiği anda siteler yeni sürümü görür; WordPress birkaç saat içinde kendisi kurar. hip.space'te Ayarlar › WordPress › **Hepsini şimdi güncelle** beklemeden başlatır.

Eklenti yalnız `https://plugin.byhip.studio` adresinden ve SHA-256 tutarsa kurulur. Bu yüzden bir ZIP'i yayınladıktan sonra değiştirmeyin; her değişiklik yeni bir sürüm numarasıyla yayınlanır.
