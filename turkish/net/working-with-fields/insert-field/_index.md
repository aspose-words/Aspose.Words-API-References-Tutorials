---
title: Alan Ekle
linktitle: Alan Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerinize nasıl alan ekleyeceğinizi öğrenin. Belgelerinizi dinamik alanlarla kişiselleştirin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-field/
---

Aşağıda Aspose.Words for .NET'in "Insert a Field" özelliğini kullanan C# kaynak kodunu adım adım açıklayan bir kılavuz bulunmaktadır. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Document ve DocumentBuilder'ı Oluşturma

Yeni bir belge oluşturarak ve bir DocumentBuilder başlatarak başlıyoruz.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Alanın eklenmesi

 biz kullanıyoruz`InsertField()` Belgeye bir alan eklemek için DocumentBuilder yöntemi. Bu örnekte, "MyFieldName" alan adına ve birleştirme biçimine sahip bir birleştirme alanı (MERGEFIELD) ekliyoruz.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Aspose.Words for .NET ile bir alan eklemek için kaynak kodu örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi ve DocumentBuilder'ı oluşturun.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// alanı girin.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

Bu örnekte, yeni bir belge oluşturduk, bir DocumentBuilder başlattık ve ardından "AlanAdım" alan adına ve birleştirme biçimine sahip bir birleştirme alanı ekledik. Belge daha sonra belirtilen dosya adıyla kaydedilir.

Aspose.Words for .NET ile "Insert a Field" (Alan Ekle) özelliğinin kullanımına ilişkin kılavuzumuz burada sona eriyor.
