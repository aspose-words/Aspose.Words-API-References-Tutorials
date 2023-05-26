---
title: Yerel Ayarı Değiştir
linktitle: Yerel Ayarı Değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinde tarih ve sayı biçimlendirmesi için yerel ayarı nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/change-locale/
---

Bu öğreticide, Aspose.Words for .NET kullanarak Word belgelerinde yerel ayarı değiştirme sürecinde size rehberlik edeceğiz. Yerel ayarı değiştirerek, adres mektup birleştirme işlemleri sırasında tarih ve sayıların biçimlendirmesini kontrol edebilirsiniz. Bunu başarmak için size gerekli C# kaynak kodunu ve adım adım yönergeleri sağlayacağız.

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

## 2. Adım: Bir Alan Ekleyin
Ardından, InsertField yöntemini kullanarak belgeye bir birleştirme alanı ekleyin:

```csharp
builder.InsertField("MERGEFIELD Date");
```

Yukarıdaki kodda, belgeye "Tarih" adlı bir birleştirme alanı ekliyoruz.

## 3. Adım: Yerel Ayarı Değiştirin
Tarih ve sayı biçimlendirmesi için yerel ayarı değiştirmek için, iş parçacığının geçerli kültürünü değiştirebilirsiniz. Bu örnekte, yerel ayarı Almanca ("de-DE") olarak ayarlayacağız:

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

Yukarıdaki kodda, mevcut kültürü saklıyoruz ve ardından mevcut iş parçacığının kültürünü Almanca olarak ayarlıyoruz.

## Adım 4: Adres Mektup Birleştirme Gerçekleştirin
Bir adres-mektup birleştirme işlemi gerçekleştirin ve "Tarih" alanı için tarih değerini girin:

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

Bu kod parçasında adres-mektup birleştirme işlemini yürütüyoruz ve "Tarih" alanı için geçerli tarihi değer olarak giriyoruz.

## 5. Adım: Orijinal Yerel Ayarı Geri Yükleyin
Adres mektup birleştirme tamamlandıktan sonra, ileti dizisi için özgün kültürü geri yükleyin:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

Yukarıdaki kodda, iş parçacığının orijinal kültürünü geri yüklüyoruz.

## 6. Adım: Belgeyi Kaydedin
Değiştirilen belgeyi Document sınıfının Save yöntemini kullanarak bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Aspose.Words for .NET kullanarak Yerel Ayarı Değiştirmek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak Word belgelerinde yerel ayarı değiştirmek için eksiksiz kaynak kodu burada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak Word belgelerinde yerel ayarı nasıl değiştireceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, adres mektup birleştirme işlemleri sırasında tarihlerin ve sayıların biçimlendirmesini artık kontrol edebilirsiniz. Belgelerinizde doğru ve tutarlı biçimlendirme sağlamak için yerel ayarı gereksinimlerinize göre özelleştirin.
