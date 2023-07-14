---
title: Akışı Kullanarak Ole Nesnesini Simge Olarak Ekleme
linktitle: Akışı Kullanarak Ole Nesnesini Simge Olarak Ekleme
second_title: Aspose.Words Belge İşleme API'sı
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

## Çözüm

Yukarıdaki adım adım kılavuz, Aspose.Words for .NET ile bir akış kullanılarak bir OLE nesnesinin bir Word belgesine simge olarak nasıl ekleneceğini açıklar. Açıklanan adımları izleyerek, bu işlevi projenize entegre edebileceksiniz. Gerekli referansları içe aktardığınızdan emin olun, yeni bir belge ve belge oluşturucu oluşturun, OLE nesnesini akıştan bir simge olarak ekleyin ve ardından belgeyi kaydedin. Sağlanan örnek kodu başlangıç noktası olarak kullanın ve gereksinimlerinize göre özelleştirin.

### SSS

#### S. Aspose.Words for .NET'i kullanmak için gerekli referanslar nasıl içe aktarılır?

A. Gerekli referansları içe aktarmak için şu adımları izlemelisiniz:

 Aşağıdakileri ekleyin`using` kaynak dosyanızın en üstündeki ifadeler:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Aspose.Words kitaplığını projenize eklediğinizden emin olun.

#### S. Aspose.Words for .NET kullanarak yeni bir belge ve belge oluşturucu nasıl oluşturulur?

A. Yeni bir belge ve belge oluşturucu oluşturmak için şu adımları izleyebilirsiniz:

 Kullan`Document` yeni bir belge oluşturmak için sınıf:

```csharp
Document doc = new Document();
```
 Kullan`DocumentBuilder` önceden oluşturulmuş belgeyle ilişkili bir belge oluşturucu oluşturmak için sınıf:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### S. Aspose.Words for .NET kullanarak bir akıştan bir OLE nesnesini simge olarak nasıl ekleyebilirim?

A. Bir akıştan simge olarak bir OLE nesnesi eklemek için şu adımları izleyebilirsiniz:

 Kullan`InsertOleObjectAsIcon` OLE nesnesini eklemek için belge oluşturucunun yöntemi:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### S. Belge bir dosyaya nasıl kaydedilir?

A.  Belgeyi bir dosyaya kaydetmek için,`Save` hedef yolu belirten belgenin yöntemi:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### S. Bir OLE nesnesini bir akıştan bir simge olarak projeme eklemek için kodu nasıl gömerim?

A. Bir OLE nesnesini bir akıştan bir simge olarak projenize ekleme kodunu katıştırmak için şu adımları izleyin:
- Uygun referansları ekleyerek gerekli referansları içe aktarın.`using` ifadeler.
-  kullanarak yeni bir belge ve bir belge oluşturucu oluşturun.`Document` Ve`DocumentBuilder` sınıflar.
- OLE nesnesini bir akıştan bir simge olarak eklemek için kodu kullanın.
-  kullanarak belgeyi kaydedin.`Save` uygun hedef yolu ile yöntem.

Bu adımları izleyerek, Aspose.Words for .NET'i kullanarak bir akıştan bir OLE nesnesini bir simge olarak başarıyla ekleyebileceksiniz. İstenen sonuçları elde etmek için talimatları izlediğinizden ve gerekli referansları içe aktardığınızdan emin olun.