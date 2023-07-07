---
title: Ole Paketi ile Word'de Ole Nesnesi Ekleme
linktitle: Ole Paketi ile Word'de Ole Nesnesi Ekleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir OLE paketi ile bir OLE nesnesini bir belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Aşağıda, Aspose.Words for .NET kullanılarak bir OLE paketiyle bir OLE nesnesinin word'e nasıl ekleneceğini gösteren C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

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

## 3. Adım: OLE paketiyle bir OLE nesnesi ekleyin
 Belge Oluşturucu'nun`InsertOleObject`belgeye OLE paketi içeren bir OLE nesnesi ekleme yöntemi. Veri akışını, nesne tipini, görüntüleme seçeneklerini ve diğer gerekli ayarları belirtin.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## 4. Adım: Belgeyi kaydedin
 Belgenin`Save` Belgeyi bir dosyaya kaydetme yöntemi.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Aspose.Words for .NET ile bir OLE paketine OLE nesnesi eklemek için örnek kaynak kodu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Bu, Aspose.Words for .NET ile bir OLE paketine bir OLE nesnesi eklemek için eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları uyguladığınızdan emin olun.

## Çözüm

Sonuç olarak, Aspose.Words for .NET kullanarak bir OLE paketi ile bir OLE nesnesini bir Word belgesine eklemek için adım adım bir kılavuz inceledik.

Bu adımları izleyerek, Aspose.Words for .NET kullanarak OLE nesnelerini OLE paketleri ile Word belgelerinize başarıyla ekleyebileceksiniz. Gerekli referansları içe aktardığınızdan emin olun ve istenen sonuçları elde etmek için talimatları dikkatle izleyin.

### ole paketiyle kelimeye ole nesnesi eklemek için SSS

#### S: Aspose.Words for .NET'i kullanmak için hangi kimlik bilgilerine ihtiyacım var?

C: Aspose.Words for .NET'i kullanmak için aşağıdaki referansları içe aktarmanız gerekir:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### S: Yeni bir belge ve belge oluşturucu nasıl oluşturulur?

 A: kullanarak yeni bir belge oluşturabilirsiniz.`Document` sınıfını ve bir belge oluşturucuyu kullanarak`DocumentBuilder` sınıf, aşağıda gösterildiği gibi:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### S: Belgeye OLE paketi içeren bir OLE nesnesi nasıl eklenir?

 C: Şunu kullanın:`InsertOleObject` belge oluşturucunun yöntemi (`DocumentBuilder`) belgeye OLE paketi içeren bir OLE nesnesi eklemek için. Veri akışını, nesne tipini, görüntüleme seçeneklerini ve diğer gerekli ayarları belirtin. İşte bir örnek :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### S: Belge nasıl kaydedilir?

 C: Belgeyi kullanın`Save`Belgeyi bir dosyaya kaydetme yöntemi. İşte bir örnek :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### S: Aspose.Words for .NET ile bir OLE paketine OLE nesnesi eklemenin tam bir örneğini verebilir misiniz?

C: İşte Aspose.Words for .NET kullanarak bir OLE paketi ile bir OLE nesnesi eklemek için eksiksiz bir örnek kod. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları uyguladığınızdan emin olun:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Bu, Aspose.Words for .NET kullanarak bir OLE paketine sahip bir OLE nesnesini bir Word belgesine ekleme konusundaki eğitimimizi sonlandırıyor. Gerekli referansları içe aktarmaktan çekinmeyin ve bu kodu projenize entegre etmek için açıklanan adımları izleyin. Başka sorunuz varsa, lütfen bizimle iletişime geçmekten çekinmeyin.