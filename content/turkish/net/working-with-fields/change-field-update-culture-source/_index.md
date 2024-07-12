---
title: Alan Güncelleme Kültür Kaynağını Değiştir
linktitle: Alan Güncelleme Kültür Kaynağını Değiştir
second_title: Aspose.Words Belge İşleme API'si
description: Alan Güncelleme Kültür Kaynağını Değiştir, Aspose.Words for .NET'te kültür kaynağını değiştirmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fields/change-field-update-culture-source/
---

Bu eğitimde, Aspose.Words for .NET kullanarak Word belgelerindeki alan güncelleme kültürü kaynağını değiştirme sürecinde size rehberlik edeceğiz. Kültür kaynağını değiştirerek, alan güncelleme ve adres-mektup birleştirme işlemleri sırasında tarih formatını kontrol edebilirsiniz. Bunu başarmak için size gerekli C# kaynak kodunu ve adım adım talimatları sağlayacağız.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Bir Document ve DocumentBuilder Oluşturun
Başlamak için Document sınıfının bir örneğini ve bir DocumentBuilder nesnesini oluşturun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belirli Yerel Ayara Sahip İçerik Ekleme
Daha sonra yerel ayarı Almanca olarak ayarlayın ve tarih biçimlendirmesine sahip alanlar ekleyin:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Yukarıdaki kodda yazı tipi yerel ayarını Almanca (yerel ayar ID 1031) olarak ayarladık ve belirli tarih formatına sahip iki alan ekledik.

## 3. Adım: Alan Güncelleme Kültürü Kaynağını Değiştirin
Alan güncelleme kültürü kaynağını değiştirmek için FieldOptions sınıfını kullanın:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

Bu örnekte, alan güncellemesi sırasında kullanılan kültürü, alanın kullandığı kültürden seçilecek şekilde ayarladık.

## 4. Adım: Adres Mektup Birleştirmeyi Gerçekleştirin
Adres-mektup birleştirme işlemi gerçekleştirin ve "Tarih2" alanı için tarih değerini belirtin:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

Bu kod parçasında adres-mektup birleştirme işlemini gerçekleştirip "Date2" alanına DateTime değeri sağlıyoruz.

## Adım 5: Belgeyi Kaydedin
Değiştirilen belgeyi, Document sınıfının Save yöntemini kullanarak bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Aspose.Words for .NET Kullanarak Alan Güncelleme Kültürü Kaynağını Değiştirmek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak Word belgelerindeki alan güncelleme kültürü kaynağını değiştirmek için tam kaynak kodu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET'i kullanarak Word belgelerindeki alan güncelleme kültürü kaynağını nasıl değiştireceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak, artık alan güncelleme ve adres-mektup birleştirme işlemleri sırasında tarih biçimlendirmesi için kullanılan kültürü kontrol edebilirsiniz. Doğru ve tutarlı tarih sağlamak için kültür kaynağını gereksinimlerinize göre özelleştirin.

### SSS'ler

#### S: Aspose.Words for .NET'te alan güncelleme kültürü kaynağını nasıl değiştirebilirim?

 C: Aspose.Words for .NET'te alan güncelleme kültürü kaynağını değiştirmek için`Document.FieldOptions.CultureSource` özelliği ve değerini şu şekilde ayarlayın:`FieldCultureSource.FieldCode` veya`FieldCultureSource.CurrentThread` . Örneğin, kullanabilirsiniz`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` alan kodunda tanımlanan kültürü kullanmak için.

#### S: Aspose.Words for .NET'te alanları güncellemek için belirli bir kültürü nasıl belirleyebilirim?

 C: Aspose.Words for .NET'te alanları güncellemek için belirli bir kültür belirlemek amacıyla`Document.FieldOptions.FieldUpdateCultureInfo` özelliği ayarlayın ve`CultureInfo` İstenilen kültüre karşılık gelen nesne. Örneğin, kullanabilirsiniz`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` Fransız (Fransa) kültürünü belirtmek için.

#### S: Aspose.Words for .NET'te otomatik alan güncellemeyi devre dışı bırakmak mümkün mü?

 C: Evet, Aspose.Words for .NET'te otomatik alan güncellemeyi devre dışı bırakmak mümkündür. Şunu kullanabilirsiniz:`Document.FieldOptions.UpdateFields` özelliği ve bunu şu şekilde ayarlayın:`false` Alanların otomatik güncellenmesini önlemek için. Bu, alanların güncellenmesini gerektiği gibi manuel olarak kontrol etmenize olanak tanır.

#### S: Aspose.Words for .NET'te belge alanlarını manuel olarak nasıl güncelleyebilirim?

 C: Aspose.Words for .NET'te bir belgedeki alanları manuel olarak güncellemek için`Field.Update` Her alan için ayrı ayrı yöntem. Örneğin, kullanabilirsiniz`field.Update()` Belirli bir alanı güncellemek için.