---
title: Ole Nesnesini Word Belgesine Simge Olarak Ekle
linktitle: Ole Nesnesini Word Belgesine Simge Olarak Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir OLE nesnesini word belgesine simge olarak nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Aşağıda, Aspose.Words for .NET kullanılarak bir OLE nesnesinin word belgesine simge olarak nasıl ekleneceğini gösteren C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

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

## Çözüm

Sonuç olarak, Aspose.Words for .NET kullanarak bir OLE nesnesini bir Word belgesine simge olarak eklemek için adım adım bir kılavuzu inceledik.

Bu adımları izleyerek, Aspose.Words for .NET'i kullanarak bir OLE nesnesini Word belgelerinize bir simge olarak başarıyla ekleyebileceksiniz. Gerekli referansları içe aktardığınızdan emin olun ve istenen sonuçları elde etmek için talimatları dikkatle izleyin.

### Word belgesine simge olarak ole nesnesi eklemek için SSS

#### S. Aspose.Words for .NET kullanarak bir OLE nesnesini bir Word belgesine simge olarak eklemek için hangi referanslar gereklidir?

C: Aspose.Words for .NET'i kullanmak için aşağıdaki referansları projenize aktarmanız gerekir:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### S. Aspose.Words for .NET'te yeni bir belge ve belge oluşturucu nasıl oluşturulur?

 A: kullanarak yeni bir belge oluşturabilirsiniz.`Document` sınıfını ve bir belge oluşturucuyu kullanarak`DocumentBuilder`sınıf. İşte bir örnek :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### S. Bir OLE nesnesini belgeye simge olarak nasıl ekleyebilirim?

 C: Belge Oluşturucu'nun`InsertOleObjectAsIcon` OLE nesnesini simge olarak ekleme yöntemi. OLE dosya yolunu, görüntüleme bayrağını, simge yolunu ve katıştırılmış nesne adını belirtin. İşte bir örnek :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### S. Simge olarak eklenen OLE nesnesi ile belge nasıl kaydedilir?

 C: Belgeyi kullanın`Save`Belgeyi bir dosyaya kaydetme yöntemi. İşte bir örnek :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```