[Uploading README.md…]()
# Arduino 3D Simülatör

Tarayıcıda çalışan, kurulum gerektirmeyen **3 boyutlu Arduino simülatörü**. Arduino Uno'yu ve elektronik parçaları sahneye koyup kablolarla bağlıyor, kodu **blok** (mBlock tarzı) veya **metin** (Arduino C++) olarak yazıp çalıştırıyorsun.

**🔗 Canlı demo:** https://hilmidnmz0.github.io/Arduino-3D-Sim-lat-r/

> Tek bir `index.html` dosyasıdır. İndirip çift tıklayarak da açabilirsin (Three.js ve Blockly internetten yüklenir, bu yüzden internet gerekir).

## Özellikler

- **3B devre kurma:** Parçaları sürükle, pinlere tıklayıp kablo çek, döndür, sil. Breadboard'a bırakılan parçalar bacaklarıyla deliklere otomatik oturur.
- **Gerçek devre hesabı:** Dirençsiz bağlanan LED yanabilir, kısa devre uyarısı verilir, potansiyometre ve LDR gerilim bölücü olarak çalışır, PWM ile LED'ler kısık yanar.
- **İki yönlü, senkron programlama:** Metin kodu yazdıkça bloklar, blokları düzenledikçe metin güncellenir. Bloğa çevrilemeyen kısımlar "ham kod" bloğu olarak korunur.
- **Seri monitör, hız ayarı** ve hazır örnekler (blok ve metin).
- **Proje kaydet / aç:** Devre, kablolar, kod ve blokları `.json` dosyası olarak kaydedip tekrar yükleyebilirsin (`Ctrl+S` ile de kaydedilir).

## Desteklenen parçalar

| Grup | Parçalar |
|---|---|
| Kart | Arduino Uno, breadboard |
| Temel | LED (5 renk), direnç, buton, potansiyometre, buzzer |
| Göstergeler | 7 segment (ortak katot), LCD 16x2, RGB LED |
| Sensörler | HC-SR04 (mesafe), DHT11 (sıcaklık/nem), LDR (ışık) |
| Eyleyiciler | Servo, step motor (28BYJ-48 + ULN2003), röle |
| Diğer | Mesafe ölçümü için hareket ettirilebilen engel |

DHT11 ve LDR'nin değerlerini sahnede parçayı seçince çıkan ayar çubuklarıyla değiştirirsin. Potansiyometrenin düğmesini fareyle sürüklersin, butona fareyle basılı tutarak basarsın.

## Nasıl kullanılır

1. Sağ üstteki **`</> Kod`** düğmesiyle kod panelini aç, listeden bir **örnek** seç (kablolu gelir) veya "Boş devre"yi seç.
2. Soldaki panelden parça ekle. Bir pine tıkla, sonra başka bir pine tıkla: kablo çekilir.
3. **Bloklar** sekmesinde blok sürükle ya da **Metin** sekmesinde Arduino kodu yaz.
4. **▶** ile çalıştır, **■** ile durdur. Çıktı **seri monitörde** görünür.

**Kısayollar:** `R` seçili parçayı döndürür · `Del` siler · sağ tık kabloyu siler · `Esc` kablo çekmeyi iptal eder · `Ctrl+Enter` programı çalıştırır · `Ctrl+S` projeyi kaydeder.

## Desteklenen Arduino kodu

Kod, tarayıcıda JavaScript'e çevrilerek çalıştırılır. Gerçek bir derleyici değildir.

- **Temel:** `setup()`, `loop()`, `pinMode`, `digitalWrite/Read`, `analogWrite/Read`, `delay`, `delayMicroseconds`, `millis`, `micros`, `pulseIn`, `tone/noTone`, `Serial`
- **Matematik:** `map`, `constrain`, `random`, `sqrt`, `abs`, `pow` ve benzerleri
- **Kütüphaneler:** `LiquidCrystal`, `Servo`, `Stepper`, `DHT`
- **Dil:** değişkenler, diziler, fonksiyonlar, `if / else`, `for`, `while`, `#define`

**Desteklenmeyenler:** `class`, `struct`, ek kütüphaneler, I2C LCD (`LiquidCrystal_I2C`), kesmeler. Float bir değişken tam sayı değerindeyse seri monitörde `12.00` yerine `12` yazılır.

## Notlar

- Parçaların kenar boşlukları, direnç ve sensör davranışları gerçek devrelere yaklaşık olarak benzetilmiştir; amaç **eğitimdir**, devre tasarımı yapmak için kesin bir ölçü aracı değildir.
- Bu proje yapay zekâ araçlarıyla geliştirilmiştir.

## Teknolojiler

[Three.js](https://threejs.org/) (3B sahne) · [Blockly](https://developers.google.com/blockly) (blok programlama) · saf HTML/CSS/JavaScript, derleme adımı yok.

## Lisans

Lisans eklenmedi. Paylaşım ve kullanım koşullarını belirlemek için depoya bir lisans (örneğin MIT) ekleyebilirsin.
