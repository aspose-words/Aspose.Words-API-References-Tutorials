---
title: Ole Nesnesini Simge Olarak Ekle
linktitle: Ole Nesnesini Simge Olarak Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir OLE nesnesini simge olarak nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Aşağıda, Aspose.Words for .NET kullanılarak bir OLE nesnesinin bir simge olarak nasıl ekleneceğini gösteren C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

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

## 3. Adım: Simge olarak bir OLE nesnesi ekleyin
 Belge Oluşturucu'yu kullanın`InsertOleObjectAsIcon` OLE nesnesini belgeye simge olarak ekleme yöntemi. OLE dosya yolunu, görüntüleme bayrağını, simge yolunu ve katıştırılmış nesne adını belirtin.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## 4. Adım: Belgeyi kaydedin
 Belgenin`Save` Belgeyi bir dosyaya kaydetme yöntemi.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Aspose.Words for .NET ile bir OLE nesnesini simge olarak eklemek için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Bu, Aspose.Words for .NET ile bir OLE nesnesini simge olarak eklemek için eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları uyguladığınızdan emin olun.
