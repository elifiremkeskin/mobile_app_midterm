# mobile_app_midterm

Erciyes Üniversitesi

Mühendislik Fakültesi

Bilgisayar Mühendisliği

**Fehim Köylü** tarafından verilen **Mobile Application Developement** dersi vize ödevidir.
> Hazırlayan: Elif İrem Keskin
> 
> Öğrenci no: 1030510558
> 
> Tarih: 28.04.2025

# Layout ve Tasarım: Stack ve Positioned Kullanımı

## İçindekiler
- [Giriş](#giriş)
- [Stack Nedir?](#stack-nedir)
- [Positioned Nedir?](#positioned-nedir)
- [Stack ve Positioned Birlikte Kullanımı](#stack-ve-positioned-birlikte-kullanımı)
- [Stack Özellikleri](#stack-özellikleri)
- [Positioned Özellikleri](#positioned-özellikleri)
- [Proje Kodu Açıklaması](#proje-kodu-açıklaması)
- [Sonuç](#sonuç)

## Giriş

Kullanıcı arayüzü (UI) tasarımında öğeleri ekran üzerinde esnek bir şekilde konumlandırmak için farklı layout yöntemleri kullanılır. **Stack** ve **Positioned** widget'ı, katmanlı ve serbest düzenlemeler yapmak için kullanılır.

---

## Stack Nedir?

**Stack**, birden fazla widget'ı üst üste yerleştirerek katmanlı bir görünüm oluşturur.

### Örnek:

```dart
Stack(
  children: [
    Container(
      width: 200,
      height: 200,
      color: Colors.blue,
    ),
    Container(
      width: 100,
      height: 100,
      color: Colors.red,
    ),
  ],
)
```

- İlk önce mavi bir kare, üstüne kırmızı daha küçük bir kare yerleştirilir.

---

## Positioned Nedir?

**Positioned**, yalnızca bir Stack içinde kullanılabilir ve öğenin Stack içindeki tam konumunu ayarlamak için kullanılır.

### Örnek:

```dart
Stack(
  children: [
    Container(
      width: 300,
      height: 300,
      color: Colors.green,
    ),
    Positioned(
      top: 50,
      left: 30,
      child: Container(
        width: 100,
        height: 100,
        color: Colors.orange,
      ),
    ),
  ],
)
```

- Turuncu kutu, yeşil zemin üzerinde `top: 50`, `left: 30` uzaklıkları ile konumlandırılır.

---

## Stack ve Positioned Birlikte Kullanımı

### Örnek: Profil Fotoğrafı ve Buton

```dart
Stack(
  children: [
    Container(
      width: double.infinity,
      height: 250,
      color: Colors.lightBlue,
    ),
    Positioned(
      top: 180,
      left: 20,
      child: CircleAvatar(
        radius: 40,
        backgroundColor: Colors.white,
        child: Icon(Icons.person, size: 40),
      ),
    ),
    Positioned(
      top: 190,
      right: 20,
      child: ElevatedButton(
        onPressed: () {},
        child: Text('Mesaj Gönder'),
      ),
    ),
  ],
)
```

- Sol altta bir profil fotoğrafı, sağ altta bir "Mesaj Gönder" butonu bulunur.

---

## Stack Özellikleri

| Özellik     | Açıklama |
| ------------- | ---------- |
| `alignment`   | Çocukları topluca hizalamak için kullanılır (`Alignment.center` vb.) |
| `fit`         | Stack boyutuna uyum sağlayıp sağlamayacaklarını belirler. |
| `clipBehavior`| Taşan öğelerin görünüp görünmeyeceğini ayarlar. |

---

## Positioned Özellikleri

| Özellik   | Açıklama |
| ----------- | --------- |
| `top`       | Üstten mesafe belirler. |
| `bottom`    | Alttan mesafe belirler. |
| `left`      | Soldan mesafe belirler. |
| `right`     | Sağdan mesafe belirler. |
| `width`     | Genişliği belirtir. |
| `height`    | Yüksekliği belirtir. |

---

## Proje Kodu Açıklaması

---

## Sonuç

Stack ve Positioned, özgür ve esnek yerleşim isteyen tasarımlar için güçlü araçlardır. Ancak karmaşık yapılarda performans sorunları yaratabileceği için dikkatli kullanılmalıdır.

Responsive tasarımlar geliştirirken Stack ve Positioned kullanımı iyi planlanmalıdır.
