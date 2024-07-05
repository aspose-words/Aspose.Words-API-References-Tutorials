---
title: Akışı Kullanarak Ole Nesnesini Simge Olarak Ekleme
linktitle: Akışı Kullanarak Ole Nesnesini Simge Olarak Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir akışı kullanarak bir OLE nesnesini simge olarak nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Aşağıda Aspose.Words for .NET ile bir akış kullanarak bir OLE nesnesinin simge olarak nasıl ekleneceğini gösteren C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Buna Aspose.Words kütüphanesinin içe aktarılması ve gerekli ad alanlarının kaynak dosyanıza eklenmesi de dahildir.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## 2. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 Bu adımda yeni bir belge oluşturacağız.`Document` sınıf ve bir belge oluşturucu kullanarak`DocumentBuilder` sınıf.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir akıştan simge olarak bir OLE nesnesi ekleyin
 Belge Oluşturucu'yu kullanın`InsertOleObjectAsIcon` Bir OLE nesnesini bir akıştan belgeye simge olarak ekleme yöntemi. Veri akışını, nesne türünü, simge yolunu ve katıştırılmış nesne adını belirtin.

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

### Aspose.Words for .NET ile bir akış kullanarak OLE nesnesini simge olarak eklemek için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Bu, Aspose.Words for .NET ile bir akışı kullanarak bir OLE nesnesini simge olarak eklemek için eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları izlediğinizden emin olun.

## Çözüm

Yukarıdaki adım adım kılavuz, Aspose.Words for .NET ile bir akış kullanarak bir Word belgesine bir OLE nesnesinin simge olarak nasıl ekleneceğini açıklamaktadır. Açıklanan adımları takip ederek bu işlevselliği projenize entegre edebileceksiniz. Gerekli referansları içe aktardığınızdan, yeni bir belge ve belge oluşturucu oluşturduğunuzdan, OLE nesnesini akıştan bir simge olarak eklediğinizden ve ardından belgeyi kaydettiğinizden emin olun. Başlangıç noktası olarak sağlanan örnek kodu kullanın ve ihtiyaçlarınıza göre özelleştirin.

### SSS'ler

#### S. Aspose.Words for .NET'i kullanmak için gerekli referanslar nasıl içe aktarılır?

A. Gerekli referansları içe aktarmak için şu adımları izlemelisiniz:

 Aşağıdakileri ekleyin`using` kaynak dosyanızın üst kısmındaki ifadeler:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Aspose.Words kütüphanesini projenize eklediğinizden emin olun.

#### S. Aspose.Words for .NET kullanarak yeni bir belge ve belge oluşturucu nasıl oluşturulur?

A. Yeni bir belge ve belge oluşturucu oluşturmak için şu adımları takip edebilirsiniz:

 Kullan`Document` yeni bir belge oluşturmak için sınıf:

```csharp
Document doc = new Document();
```
 Kullan`DocumentBuilder`önceden oluşturulan belgeyle ilişkili bir belge oluşturucu oluşturmak için sınıf:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### S. Aspose.Words for .NET kullanarak bir akışa simge olarak bir OLE nesnesi nasıl eklenir?

A. Bir OLE nesnesini bir akıştan simge olarak eklemek için şu adımları takip edebilirsiniz:

 Kullan`InsertOleObjectAsIcon` OLE nesnesini eklemek için belge oluşturucunun yöntemi:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### S. Belge bir dosyaya nasıl kaydedilir?

A.  Belgeyi bir dosyaya kaydetmek için kullanabilirsiniz.`Save` Hedef yolunu belirten belgenin yöntemi:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### S. Bir OLE nesnesini bir akıştan simge olarak projeme eklemek için kodu nasıl eklerim?

A. Bir OLE nesnesini bir akıştan simge olarak projenize ekleme kodunu eklemek için şu adımları izleyin:
-  Uygun referansları ekleyerek gerekli referansları içe aktarın`using` ifadeler.
-  kullanarak yeni bir belge ve belge oluşturucu oluşturun.`Document` Ve`DocumentBuilder` sınıflar.
- OLE nesnesini bir akıştan simge olarak eklemek için kodu kullanın.
-  kullanarak belgeyi kaydedin.`Save` uygun hedef yolu ile yöntem.

Bu adımları izleyerek, Aspose.Words for .NET'i kullanarak bir akıştan simge olarak bir OLE nesnesini başarılı bir şekilde ekleyebileceksiniz. İstediğiniz sonuçları elde etmek için talimatları izlediğinizden ve gerekli referansları içe aktardığınızdan emin olun.