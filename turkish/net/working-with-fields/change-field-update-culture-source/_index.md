---
title: Alanı Değiştir Kültür Kaynağını Güncelle
linktitle: Alanı Değiştir Kültür Kaynağını Güncelle
second_title: Aspose.Words Belge İşleme API'sı
description: Alanı Değiştir Kültür Kaynağını Güncelle, Aspose.Words for .NET'te kültür kaynağını değiştirmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fields/change-field-update-culture-source/
---

Bu öğreticide, Aspose.Words for .NET kullanarak Word belgelerindeki alan güncelleme kültürü kaynağını değiştirme sürecinde size rehberlik edeceğiz. Kültür kaynağını değiştirerek, alan güncelleme ve adres mektup birleştirme işlemleri sırasında tarih biçimlendirmesini kontrol edebilirsiniz. Bunu başarmak için size gerekli C# kaynak kodunu ve adım adım yönergeleri sağlayacağız.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfının bir örneğini ve DocumentBuilder nesnesini oluşturun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belirli Yerel Ayarla İçeriği Ekleyin
Ardından, yerel ayarı Almanca olarak ayarlayın ve tarih biçimlendirmeli alanlar ekleyin:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Yukarıdaki kodda, yazı tipi yerel ayarını Almanca (yerel ayar kimliği 1031) olarak ayarlıyoruz ve belirli tarih biçimlendirmesiyle iki alan ekliyoruz.

## 3. Adım: Alanı Değiştir Kültür Kaynağını Güncelleyin
Alan güncelleme kültürü kaynağını değiştirmek için FieldOptions sınıfını kullanın:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

Bu örnekte, alan tarafından kullanılan kültürden seçilecek alan güncellemesi sırasında kullanılan kültürü ayarladık.

## Adım 4: Adres Mektup Birleştirme Gerçekleştirin
Bir adres-mektup birleştirme işlemi gerçekleştirin ve "Tarih2" alanı için tarih değerini belirtin:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

Bu kod parçacığında adres-mektup birleştirme işlemini yürütüyoruz ve "Date2" alanı için bir DateTime değeri veriyoruz.

## 5. Adım: Belgeyi Kaydedin
Değiştirilen belgeyi Document sınıfının Save yöntemini kullanarak bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Aspose.Words for .NET kullanarak Alan Güncelleme Kültür Kaynağını Değiştirmek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak Word belgelerinde alan güncelleme kültürü kaynağını değiştirmek için eksiksiz kaynak kodu burada:

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
Tebrikler! Aspose.Words for .NET kullanarak Word belgelerinde alan güncelleme kültürü kaynağını nasıl değiştireceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak, alan güncelleme ve adres mektup birleştirme işlemleri sırasında tarih biçimlendirme için kullanılan kültürü artık kontrol edebilirsiniz. Doğru ve tutarlı tarih sağlamak için kültür kaynağını gereksinimlerinize göre özelleştirin.

### SSS

#### S: Aspose.Words for .NET'te alan güncelleme kültürü kaynağını nasıl değiştirebilirim?

 Y: Aspose.Words for .NET'te alan güncelleme kültürü kaynağını değiştirmek için`Document.FieldOptions.CultureSource` özellik ve değerini olarak ayarlayın`FieldCultureSource.FieldCode` veya`FieldCultureSource.CurrentThread` . Örneğin, kullanabilirsiniz`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` alan kodunda tanımlanan kültürü kullanmak için.

#### S: Aspose.Words for .NET'te alanları güncellemek için belirli bir kültürü nasıl belirleyebilirim?

C: Aspose.Words for .NET'te alanları güncellemek için belirli bir kültür belirtmek üzere`Document.FieldOptions.FieldUpdateCultureInfo` özelliğini ayarlayın ve`CultureInfo` istenen kültüre karşılık gelen nesne. Örneğin, kullanabilirsiniz`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` Fransız (Fransa) kültürünü belirtmek için.

#### S: Aspose.Words for .NET'te otomatik alan güncellemesini devre dışı bırakmak mümkün mü?

 C: Evet, Aspose.Words for .NET'te otomatik alan güncellemesini devre dışı bırakmak mümkündür. kullanabilirsiniz`Document.FieldOptions.UpdateFields` özellik ve bunu ayarlayın`false` alanların otomatik güncellenmesini önlemek için. Bu, alanların güncellenmesini gerektiği şekilde manuel olarak kontrol etmenizi sağlar.

#### S: Aspose.Words for .NET'te belge alanlarını manuel olarak nasıl güncelleyebilirim?

 C: Aspose.Words for .NET'te bir belgedeki alanları manuel olarak güncellemek için`Field.Update` her alan için ayrı ayrı yöntem. Örneğin, kullanabilirsiniz`field.Update()` belirli alanı güncellemek için.