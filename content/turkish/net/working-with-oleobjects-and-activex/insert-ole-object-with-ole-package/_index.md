---
title: Ole Paketi ile Word'e Ole Nesnesi Ekleme
linktitle: Ole Paketi ile Word'e Ole Nesnesi Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak OLE paketi içeren bir OLE nesnesini bir belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Aşağıda, Aspose.Words for .NET kullanarak bir OLE paketiyle bir OLE nesnesinin word'e nasıl ekleneceğini gösteren, C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

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

## 3. Adım: OLE paketiyle bir OLE nesnesi ekleyin
 Belge Oluşturucuyu kullanın`InsertOleObject` OLE paketi içeren bir OLE nesnesini belgeye ekleme yöntemi. Veri akışını, nesne türünü, görüntüleme seçeneklerini ve diğer gerekli ayarları belirtin.

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

### Aspose.Words for .NET ile OLE paketine OLE nesnesi eklemek için örnek kaynak kodu

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

Bu, Aspose.Words for .NET ile OLE paketine bir OLE nesnesi eklemek için eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları izlediğinizden emin olun.

## Çözüm

Sonuç olarak, Aspose.Words for .NET kullanarak OLE paketiyle bir Word belgesine OLE nesnesi eklemek için adım adım kılavuzu inceledik.

Bu adımları takip ederek, Aspose.Words for .NET'i kullanarak OLE paketlerini içeren OLE nesnelerini Word belgelerinize başarıyla ekleyebileceksiniz. İstediğiniz sonuçları elde etmek için gerekli referansları içe aktardığınızdan ve talimatları dikkatlice uyguladığınızdan emin olun.

### Ole paketiyle Word'e ole nesnesi eklemeyle ilgili SSS

#### S: Aspose.Words for .NET'i kullanmak için hangi kimlik bilgilerini içe aktarmam gerekiyor?

C: Aspose.Words for .NET'i kullanmak için aşağıdaki referansları içe aktarmanız gerekir:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### S: Yeni bir belge ve belge oluşturucu nasıl oluşturulur?

 C: Kullanarak yeni bir belge oluşturabilirsiniz.`Document` sınıf ve bir belge oluşturucu kullanarak`DocumentBuilder` aşağıda gösterildiği gibi sınıf:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### S: OLE paketine sahip bir OLE nesnesi belgeye nasıl eklenir?

 C: Kullan`InsertOleObject`belge oluşturucunun yöntemi (`DocumentBuilder`) belgeye OLE paketi içeren bir OLE nesnesi eklemek için. Veri akışını, nesne türünü, görüntüleme seçeneklerini ve diğer gerekli ayarları belirtin. İşte bir örnek :

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

 C: Belgeyi kullanın`Save` Belgeyi bir dosyaya kaydetme yöntemi. İşte bir örnek :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### S: Aspose.Words for .NET ile OLE paketine OLE nesnesi eklemenin tam bir örneğini verebilir misiniz?

C: Burada Aspose.Words for .NET kullanarak bir OLE paketiyle bir OLE nesnesi eklemek için tam bir örnek kod bulabilirsiniz. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları izlediğinizden emin olun:

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

Bu, Aspose.Words for .NET kullanarak bir Word belgesine OLE paketi içeren bir OLE nesnesi ekleme konusundaki eğitimimizin sonuncusudur. Bu kodu projenize entegre etmek için gerekli referansları içe aktarmaktan ve açıklanan adımları takip etmekten çekinmeyin. Başka sorularınız varsa lütfen bizimle iletişime geçmekten çekinmeyin.