---
title: Adres Mektup Birleştirme Alan Adlarını Alın
linktitle: Adres Mektup Birleştirme Alan Adlarını Alın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerinizde adres mektup birleştirme alan adlarını nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/get-mail-merge-field-names/
---

Aspose.Words for .NET'in "Get Merge Field Names" özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleme

İlk adım, belgeyi birleştirme alan adlarını almak istediğiniz yere yüklemektir.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

"BELGE DOSYASINIZ"ı kendi dosyanızın adıyla değiştirdiğinizden emin olun.

## 3. Adım: Birleştirme alan adlarını alın

 biz kullanıyoruz`GetFieldNames()` belgede bulunan birleştirme alanlarının adlarını içeren bir dizi elde etme yöntemi.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 bu`fieldNames` değişken artık birleştirme alanlarının adlarını içerir.

### Aspose.Words for .NET ile Alan Adlarını Birleştirme İçin Kaynak Kodu Örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Birleştirme alan adlarını alın.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Birleştirme alanlarının sayısını görüntüleyin.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 Bu örnekte, bir belge yükledik, birleştirme alan adlarını`GetFieldNames()` yöntemi ve belgede bulunan birleştirme alanlarının sayısını görüntüler.

Bu, Aspose.Words for .NET ile "Get Merge Field Names" özelliğinin kullanımına ilişkin kılavuzumuzun sonuna geliyor.