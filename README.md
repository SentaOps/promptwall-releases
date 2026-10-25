# PromptWall sürümleri

Bu depoda PromptWall appliance için **imzalı ürün yamaları** yayımlanır.
Kaynak kod burada değildir.

Her sürümde (Releases) şunlar bulunur:

| Dosya | Ne işe yarar |
|---|---|
| `promptwall-<sürüm>-amd64.pwpatch`, `promptwall-<sürüm>-arm64.pwpatch` | Ürün yaması; cihazın mimarisine uyanı kurulur |
| `SHA256SUMS` | Dosyaların SHA-256 değerleri |
| `index.json`, `index.json.sig` | İmzalı sürüm dizini; cihazın internetten denetimi bunu okur |

## Kurulum

Cihazın web konsolunda **Ayarlar → Sistem → Ürün güncellemesi**:

1. Cihazın mimarisine uyan `.pwpatch` dosyasını **Yükle ve doğrula**.
2. Doğrulandıktan sonra **Bu sürüme geç → Onayla ve başlat**.

Cihaz paketin imzasını kendisi doğrular; imzası, sürümü ya da mimarisi
tutmayan paket reddedilir. Yeni sürüm sağlıklı açılmazsa cihaz önceki
sürüme kendiliğinden döner. Yama yalnız ürün konteynerini günceller;
ayarlar, EDM/IDM, kanıt kayıtları, lisans ve sertifikalar değişmez.

Kurum isterse cihaz yeni sürümleri kendisi denetleyebilir:
Ayarlar → Sistem → Güncelleme kaynağı. Kurulum yine yönetici onayıyla yapılır.

## Kurum içi yansı

Paketleri kurumun kendi deposunda (Artifactory, Nexus vb.) tutmak için bir
sürümün bütün dosyalarını tek bir dizine koyun ve cihazda "Sürüm sitesi"
olarak o dizini verin. İmzalar aynı kaldığı için yansıdaki dosyalar
değiştirilemez.
