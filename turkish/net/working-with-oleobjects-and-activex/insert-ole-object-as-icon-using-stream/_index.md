---
title: Akışı Kullanarak Ole Nesnesini Simge Olarak Ekleme
linktitle: Akışı Kullanarak Ole Nesnesini Simge Olarak Ekleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir akışı kullanarak bir OLE nesnesini simge olarak nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Aşağıda, Aspose.Words for .NET ile bir akış kullanarak bir OLE nesnesinin bir simge olarak nasıl ekleneceğini gösteren C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce, Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Bu, Aspose.Words kitaplığının içe aktarılmasını ve gerekli ad alanlarının kaynak dosyanıza eklenmesini içerir.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## 2. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 Bu adımda, kullanarak yeni bir belge oluşturacağız.`Document` sınıfını ve bir belge oluşturucuyu kullanarak`DocumentBuilder` sınıf.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir akıştan simge olarak bir OLE nesnesi ekleyin
 Belge Oluşturucu'yu kullanın`InsertOleObjectAsIcon` OLE nesnesini bir akıştan belgeye bir simge olarak ekleme yöntemi. Veri akışını, nesne tipini, simge yolunu ve katıştırılmış nesne adını belirtin.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## 4. Adım: Belgeyi kaydedin
 Belgenin`Save` Belgeyi bir dosyaya kaydetme yöntemi.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Aspose.Words for .NET ile bir akış kullanarak bir OLE nesnesini simge olarak eklemek için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Bu, Aspose.Words for .NET ile bir akış kullanarak bir OLE nesnesini simge olarak eklemek için eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları uyguladığınızdan emin olun.