---
title: Ole Nesnesi Ekle
linktitle: Ole Nesnesi Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir OLE nesnesini bir belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Aspose.Words for .NET kullanarak bir OLE nesnesinin nasıl ekleneceğini gösteren aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce, Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Bu, Aspose.Words kitaplığının içe aktarılmasını ve gerekli ad alanlarının kaynak dosyanıza eklenmesini içerir.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 2. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 Bu adımda, kullanarak yeni bir belge oluşturacağız.`Document` sınıfını ve bir belge oluşturucuyu kullanarak`DocumentBuilder` sınıf.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir OLE nesnesi ekleyin
 Belge Oluşturucu'yu kullanın`InsertOleObject` belgeye bir OLE nesnesi ekleme yöntemi. OLE nesne URL'sini, nesne türünü, görüntüleme seçeneklerini ve diğer gerekli ayarları belirtin.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmldosyası", doğru, doğru, boş);
```

## 4. Adım: Belgeyi kaydedin
 Belgenin`Save` Belgeyi bir dosyaya kaydetme yöntemi.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Aspose.Words for .NET ile bir OLE nesnesi eklemek için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmldosyası", doğru, doğru, boş);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Bu, Aspose.Words for .NET ile bir OLE nesnesi eklemek için eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları uyguladığınızdan emin olun.
