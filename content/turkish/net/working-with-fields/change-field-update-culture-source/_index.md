---
title: Alan Güncelleme Kültür Kaynağını Değiştir
linktitle: Alan Güncelleme Kültür Kaynağını Değiştir
second_title: Aspose.Words Belge İşleme API'si
description: Bu kılavuzla Aspose.Words for .NET'te alan güncelleme kültürü kaynağını nasıl değiştireceğinizi öğrenin. Farklı kültürlere dayalı tarih biçimlendirmesini kolayca kontrol edin.
type: docs
weight: 10
url: /tr/net/working-with-fields/change-field-update-culture-source/
---
## giriiş

Bu derste Aspose.Words for .NET dünyasına dalacağız ve alan güncelleme kültürü kaynağının nasıl değiştirileceğini keşfedeceğiz. Tarih alanları içeren Word belgeleriyle uğraşıyorsanız ve bu tarihlerin farklı kültürlere göre nasıl biçimlendirildiğini kontrol etmeniz gerekiyorsa bu kılavuz tam size göre. Süreci adım adım inceleyerek her konsepti kavramanızı ve projelerinizde etkili bir şekilde uygulayabilmenizi sağlayalım.

## Önkoşullar

Koda geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET: Buradan indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Herhangi bir .NET uyumlu IDE (örneğin, Visual Studio).
- Temel C# Bilgisi: Bu eğitimde, C# programlama konusunda temel bir anlayışa sahip olduğunuz varsayılmaktadır.

## Ad Alanlarını İçe Aktar

Öncelikle projemiz için gerekli namespace’leri import edelim. Bu, Aspose.Words tarafından sağlanan tüm gerekli sınıflara ve yöntemlere erişebilmemizi sağlayacaktır.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Şimdi Aspose.Words for .NET'te alan güncelleme kültürü kaynağını nasıl değiştireceğinizi anlamanıza yardımcı olmak için örneği birden fazla adıma ayıralım.

## 1. Adım: Belgeyi Başlatın

 İlk adım, yeni bir örneğini oluşturmaktır.`Document` sınıf ve bir`DocumentBuilder`. Bu, Word belgemizi oluşturmanın ve değiştirmenin temelini oluşturur.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belirli Yerel Ayara Sahip Alanları Ekleme

Daha sonra belgeye alanlar eklememiz gerekiyor. Bu örnek için iki tarih alanı ekleyeceğiz. Kültürün tarih biçimini nasıl etkilediğini göstermek için yazı tipinin yerel ayarını Almanca (LocaleId = 1031) olarak ayarlayacağız.

```csharp
builder.Font.LocaleId = 1031; // Almanca
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

## 3. Adım: Alan Güncelleme Kültürü Kaynağını Ayarlayın

 Alanları güncellerken kullanılan kültürü kontrol etmek için`FieldUpdateCultureSource` mülkiyeti`FieldOptions`sınıf. Bu özellik kültürün alan kodundan mı yoksa belgeden mi alınacağını belirler.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

## 4. Adım: Adres Mektup Birleştirmeyi Yürütün

Artık alanları gerçek verilerle doldurmak için adres-mektup birleştirme yürütmemiz gerekiyor. Bu örnekte ikinci tarih alanını ayarlayacağız (`Date2`) 1 Ocak 2011'e kadar.

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

## Adım 5: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydediyoruz. Bu adım, alan güncelleme kültürü kaynağını değiştirme işlemini tamamlar.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'te alan güncelleme kültürü kaynağını başarıyla değiştirdiniz. Bu adımları takip ederek Word belgelerinizin tarih ve diğer alan değerlerinin belirtilen kültür ayarlarına göre görüntülenmesini sağlayabilirsiniz. Bu, özellikle uluslararası bir izleyici kitlesine yönelik belgeler oluştururken yararlı olabilir.

## SSS'ler

###  ayarın amacı nedir?`LocaleId`?
`LocaleId` Tarihlerin ve yerel ayarlara duyarlı diğer verilerin nasıl biçimlendirileceğini etkileyen metin için kültür ayarlarını belirtir.

### Almanca dışında farklı bir yerel ayar kullanabilir miyim?
 Evet, ayarlayabilirsiniz`LocaleId`geçerli herhangi bir yerel ayar tanımlayıcısına. Örneğin İngilizce (Amerika Birleşik Devletleri) için 1033.

###  Ayarlamazsam ne olur?`FieldUpdateCultureSource` property?
Bu özellik ayarlanmazsa alanlar güncellenirken belgenin varsayılan kültür ayarları kullanılacaktır.

### Alanları alan kodu yerine belgenin kültürüne göre güncellemek mümkün müdür?
 Evet, ayarlayabilirsiniz`FieldUpdateCultureSource` ile`FieldUpdateCultureSource.Document` Belgenin kültür ayarlarını kullanmak için.

### Tarihleri farklı bir düzende nasıl biçimlendiririm?
 Tarih biçimi desenini şuradan değiştirebilirsiniz:`InsertField` yöntemini değiştirerek`\\@` değeri değiştirin.