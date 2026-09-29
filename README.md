<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=soft&color=0:FCAF01,50:FE2C6B,100:FC05AC&height=160&section=header&text=PluginHider&fontSize=60&fontColor=FFFFFF&fontAlignY=42&desc=Spigot%20%2F%20Paper%20%E2%80%A2%201.8%20%E2%86%92%201.21.11&descSize=15&descAlignY=72&animation=fadeIn" alt="PluginHider" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/coslant/PluginHider/releases/latest"><img src="https://img.shields.io/github/v/release/coslant/PluginHider?style=for-the-badge&label=%C4%B0ndir&color=FE2C6B&logo=github" alt="Download" /></a>
  <a href="https://discord.gg/forges"><img src="https://img.shields.io/badge/Discord-Forges%20Studio-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord: Forges Studio" /></a>
</p>

<p align="center">
  <a href="https://github.com/coslant/PluginHider/actions/workflows/build.yml"><img src="https://img.shields.io/github/actions/workflow/status/coslant/PluginHider/build.yml?branch=main&style=flat-square&label=build" alt="Build" /></a>
  <img src="https://img.shields.io/badge/Minecraft-1.8%20%E2%86%92%201.21.11-FCAF01?style=flat-square" alt="Minecraft 1.8 - 1.21.11" />
  <img src="https://img.shields.io/badge/Spigot%20%7C%20Paper-FE9808?style=flat-square" alt="Spigot | Paper" />
  <img src="https://img.shields.io/badge/Java-8-FD6C29?style=flat-square&logo=openjdk&logoColor=white" alt="Java 8" />
  <a href="LICENSE"><img src="https://img.shields.io/github/license/coslant/PluginHider?style=flat-square&color=FB0C9E&label=lisans" alt="License" /></a>
</p>

<p align="center">
  <b>Sunucunda hangi pluginlerin kurulu olduğunu gizler.</b>
  <br>
  <sub><kbd>EN</kbd> Hides which plugins your server runs, from commands and tab completion alike.</sub>
</p>

Sunucuna giren biri `/pl` veya `/ver` yazdığında hangi pluginleri kullandığını görebilir; bu bilgi
bilinen açıkları hedeflemek için kullanılır. PluginHider bu sızıntıyı üç katmanda kapatır.
Tek jar **1.8 – 1.21.11** arası çalışır.

## ✨ Özellikler

- 🚫 `/plugins`, `/pl`, `/ver`, `/version`, `/about`, `/?` komutlarını engeller
- 🎭 `/bukkit:pl`, `/minecraft:me` gibi **ad alanlı** komutları da kapatır — bu olmadan engeli aşmak çok kolay
- 🌳 1.13+ sürümlerde komut, istemcinin komut ağacından tamamen **silinir**; oyuncu komutun varlığını bile bilmez
- ⌨️ Tab tamamlamada önerilerden süzülür
- 🔑 `pluginhider.bypass` yetkisi olanlar (varsayılan: OP) her şeyi görmeye devam eder
- 📝 Engellenen denemeler isteğe bağlı olarak konsola yazılır
- ⚡ Hiçbir bağımlılığı yok, ProtocolLib gerektirmez

## 🛡️ Nasıl çalışır

| Katman | Ne yapar | Sürüm |
| :-- | :-- | :-- |
| Komut çalıştırma | Komut çalıştırılmadan engellenir | 1.8 → 1.21.11 |
| Komut ağacı | Komut istemciye hiç gönderilmez | 1.13+ |
| Tab tamamlama | Öneri listesinden çıkarılır | 1.13+ |

> 1.13 öncesi sürümlerde sunucu yazılımı istemciye komut ağacı göndermez. Orada yalnızca ilk katman
> çalışır: komut engellenir, ama tab tamamlama filtrelenemez.

## 📥 Kurulum

1. [Releases](https://github.com/coslant/PluginHider/releases/latest) sayfasından `PluginHider.jar` dosyasını indir.
2. Sunucunun `plugins/` klasörüne at.
3. Sunucuyu yeniden başlat.
4. `plugins/PluginHider/config.yml` dosyasından gizlenecek komutları düzenle.

## 🎮 Komutlar

| Komut | Açıklama | Yetki |
|-------|----------|-------|
| `/pluginhider reload` | Ayarları yeniden yükler | `pluginhider.admin` |

**Alias:** `/phider`

## 🔑 Yetkiler

| Yetki | Açıklama | Varsayılan |
|-------|----------|------------|
| `pluginhider.bypass` | Gizlenen komutları görür ve kullanır | op |
| `pluginhider.admin` | Ayarları yönetir | op |

## ⚙️ Ayarlar (config.yml)

| Anahtar | Açıklama |
|---------|----------|
| `blocked-commands` | Gizlenecek komutların listesi |
| `block-namespaced` | `/bukkit:pl` gibi ad alanlı tüm komutları gizle |
| `allowed-namespaces` | Ad alanı engellemesinden muaf tutulacaklar |
| `log-attempts` | Engellenen denemeleri konsola yaz |
| `messages.blocked` | Engellenince gösterilecek mesaj |

> 💡 **İpucu:** `messages.blocked` değerini sunucunun normal "bilinmeyen komut" mesajıyla aynı
> tutarsan, oyuncu bir engelleme olduğunu bile anlamaz.

## 🛠️ Derleme

```bash
mvn clean package
```

Çıktı: `target/PluginHider.jar`

> 1.8 uyumluluğu için Java 8 hedefiyle derlenir. En sorunsuz derleme **JDK 8, 11 veya 17** iledir.

Her push'ta [GitHub Actions](https://github.com/coslant/PluginHider/actions/workflows/build.yml) projeyi otomatik derler; etiketlenen sürümler (`v*`) jar'ıyla birlikte [Releases](https://github.com/coslant/PluginHider/releases) sayfasında yayınlanır.

## 💬 Destek

- 🐛 Hata bildirimi ve öneriler için [Issues](https://github.com/coslant/PluginHider/issues) sekmesini kullan.
- 💬 Sorular ve destek için [Forges Studio Discord](https://discord.gg/forges) sunucusuna katıl.

## 📄 Lisans

[MIT](LICENSE) — dilediğin gibi kullan, değiştir, dağıt.

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=0:FCAF01,50:FE2C6B,100:FC05AC&height=4&section=footer" width="100%" alt="" />
  <br>
  <sub>🔥 <a href="https://github.com/coslant">coslant</a> tarafından geliştirildi · <a href="https://discord.gg/forges">Forges Studio</a></sub>
</p>
