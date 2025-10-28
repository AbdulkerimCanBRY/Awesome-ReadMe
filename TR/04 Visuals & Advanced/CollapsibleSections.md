# 📖 Katlanabilir Bölümler Rehberi (`Collapsible Sections`)

Bu rehber, `README` dosyalarınızı daha temiz ve daha organize tutmak için HTML'in `<details>` ve `<summary>` etiketlerini kullanarak nasıl **katlanabilir/genişletilebilir (collapsible)** bölümler oluşturacağınızı açıklamaktadır. Bu teknik, uzun kod bloklarını, yapılandırma dosyası örneklerini veya sıkça sorulan sorular gibi ikincil bilgileri varsayılan olarak gizlemek için mükemmeldir.

## İçindekiler

1.  [Katlanabilir Bölüm Nedir ve Neden Kullanılır?](#1-katlanabilir-bölüm-nedir-ve-neden-kullanılır)
2.  [Temel Yazım Kuralları (Syntax)](#2-temel-yazım-kuralları-syntax)
3.  [İç İçe Katlanabilir Bölümler](#3-i̇ç-i̇çe-katlanabilir-bölümler)
4.  [İçerik Olarak Markdown Kullanımı](#4-i̇çerik-olarak-markdown-kullanımı)
5.  [Pratik Kullanım Alanları](#5-pratik-kullanım-alanları)
6.  [En İyi Kullanım Pratikleri](#6-en-i̇yi-kullanım-pratikleri)

-----

## 1\. Katlanabilir Bölüm Nedir ve Neden Kullanılır?

Katlanabilir bölüm, kullanıcının tıklayarak içeriğini gösterebileceği veya gizleyebileceği interaktif bir alandır. GitHub, Markdown dosyaları içinde temel HTML etiketlerinin kullanımına izin verir ve `<details>` bu güçlü özelliklerden biridir.

**Başlıca faydaları:**

  - **Temiz ve Odaklanmış Arayüz:** `README` dosyasının ilk bakışta daha kısa ve daha az göz korkutucu görünmesini sağlar. Kullanıcılar sadece ilgilendikleri detayları görmek için tıklarlar.
  - **Organizasyon:** Uzun veya teknik olarak yoğun bilgileri (hata çıktıları, uzun kod örnekleri vb.) ana akıştan ayırır.
  - **Gelişmiş Dokümantasyon:** Sıkça Sorulan Sorular (SSS) gibi bölümler için ideal bir yapı sunar.

## 2\. Temel Yazım Kuralları (Syntax)

Bir katlanabilir bölüm oluşturmak için iki HTML etiketi kullanılır:

  - `<details>`: Gizlenecek içeriğin tamamını saran ana etikettir.
  - `<summary>`: Her zaman görünür olan ve tıklandığında içeriği açıp kapatan başlık metnini içerir.

### Temel Örnek

```html
<details>
  <summary>Buraya tıklayarak detayları görebilirsiniz.</summary>

  Bu bölüm, varsayılan olarak gizlidir. Başlığa tıklandığında görünür hale gelir.
  Buraya istediğiniz kadar metin veya başka içerikler ekleyebilirsiniz.
</details>
```

### Sonuç:

<details>
<summary>Buraya tıklayarak detayları görebilirsiniz.</summary>

Bu bölüm, varsayılan olarak gizlidir. Başlığa tıklandığında görünür hale gelir.
Buraya istediğiniz kadar metin veya başka içerikler ekleyebilirsiniz.

</details>

-----

## 3\. İç İçe Katlanabilir Bölümler

Daha karmaşık ve hiyerarşik yapılar oluşturmak için `<details>` etiketlerini iç içe kullanabilirsiniz.

### İç İçe Örnek

```html
<details>
  <summary>Ana Konu</summary>

  Bu ana konunun açıklamasıdır.

  <details>
    <summary>Alt Konu 1</summary>

    Bu da alt konunun detaylarıdır.
  </details>

  <details>
    <summary>Alt Konu 2</summary>
    
    Bu da ikinci alt konunun detaylarıdır.
  </details>
</details>
```

### Sonuç:

<details>
<summary>Ana Konu</summary>

Bu ana konunun açıklamasıdır.

<details>
<summary>Alt Konu 1</summary>

```
Bu da alt konunun detaylarıdır.
```

</details>

<details>
<summary>Alt Konu 2</summary>

```
Bu da ikinci alt konunun detaylarıdır.
```

</details>
</details>

-----

## 4\. İçerik Olarak Markdown Kullanımı

`<details>` etiketinin en güçlü özelliklerinden biri, içine normal Markdown sözdizimini yazabilmenizdir. Kod blokları, listeler, resimler ve tablolar gibi tüm Markdown öğeleri sorunsuz bir şekilde çalışır.

**Önemli Not:** Markdown'ın düzgün işlenmesi için, `<summary>` etiketinden sonra ve `</details>` etiketinden önce **bir satır boşluk bırakmanız** gerekir.

### Markdown ile Örnek

````html
<details>
  <summary>🚀 Kurulum Komutlarını Göster</summary>

  Aşağıda projenin kurulumu için gereken temel komutlar listelenmiştir:

  ```shell
  # 1. Depoyu klonlayın
  git clone [https://github.com/kullanici/proje.git](https://github.com/kullanici/proje.git)

  # 2. Dizine gidin
  cd proje

  # 3. Bağımlılıkları yükleyin
  npm install
````

Daha fazla bilgi için `INSTALL.md` dosyasına bakabilirsiniz.

\</details\>

````

### Sonuç:

&lt;details&gt;
  &lt;summary&gt;🚀 Kurulum Komutlarını Göster&lt;/summary&gt;

Aşağıda projenin kurulumu için gereken temel komutlar listelenmiştir:

```shell
# 1. Depoyu klonlayın
git clone https://github.com/kullanici/proje.git

# 2. Dizine gidin
cd proje

# 3. Bağımlılıkları yükleyin
npm install
````

Daha fazla bilgi için `INSTALL.md` dosyasına bakabilirsiniz.

\</details\>

-----

## 5\. Pratik Kullanım Alanları

  - **Sıkça Sorulan Sorular (SSS):** Her soru bir `<summary>`, her cevap ise `<details>` içinde yer alabilir.
  - **Uzun Kod Blokları:** Kullanıcının ilk bakışta görmesi gerekmeyen uzun kod veya yapılandırma dosyası örneklerini gizlemek.
  - **Hata Çıktıları (Error Logs):** Bir "Issue" raporunda, uzun hata loglarını bir katlanabilir bölüm içine koyarak raporun daha okunabilir olmasını sağlamak.
  - **Sürüm Notları (Release Notes):** Her sürümün detaylarını ayrı bir katlanabilir bölüm içinde sunmak.

-----

## 6\. En İyi Kullanım Pratikleri

  - **Boşluk Kuralı:** Markdown'ın doğru çalışması için `<summary>` ve `</details>` etiketlerinden sonra/önce boş bir satır bırakmayı unutmayın.
  - **Açıklayıcı Başlıklar:** `<summary>` metni, gizli içeriğin ne hakkında olduğunu net bir şekilde açıklamalıdır. "Detaylar" gibi genel bir ifade yerine "Yapılandırma Dosyası Örneğini Görüntüle" gibi daha spesifik bir başlık kullanın.

  - **Kritik Bilgileri Gizlemeyin:** Projenin kurulumu veya temel kullanımı için hayati önem taşıyan bilgileri varsayılan olarak gizlemekten kaçının. Bu özellik, ikincil veya isteğe bağlı bilgiler için daha uygundur.
