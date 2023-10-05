---
title: Ole Nesnesini Word Belgesine Simge Olarak Ekle
linktitle: Ole Nesnesini Word Belgesine Simge Olarak Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir OLE nesnesini word belgesine simge olarak nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Aspose.Words for .NET kullanılarak bir OLE nesnesinin word belgesine simge olarak nasıl ekleneceğini gösteren aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

## 1. Adım: Gerekli referansları içe aktarın
Başlamadan önce Aspose.Words for .NET'i kullanmak için gerekli referansları projenize aktardığınızdan emin olun. Buna Aspose.Words kütüphanesinin içe aktarılması ve gerekli ad alanlarının kaynak dosyanıza eklenmesi de dahildir.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 2. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 Bu adımda yeni bir belge oluşturacağız.`Document` sınıf ve bir belge oluşturucu kullanarak`DocumentBuilder` sınıf.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir OLE nesnesini simge olarak ekleyin
 Belge Oluşturucu'yu kullanın`InsertOleObjectAsIcon`OLE nesnesini belgeye simge olarak ekleme yöntemi. OLE dosya yolunu, görüntüleme bayrağını, simge yolunu ve katıştırılmış nesne adını belirtin.

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

Bu, Aspose.Words for .NET ile bir OLE nesnesinin simge olarak eklenmesine yönelik eksiksiz bir kod örneğidir. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları izlediğinizden emin olun.

## Çözüm

Sonuç olarak, Aspose.Words for .NET kullanarak bir Word belgesine OLE nesnesini simge olarak eklemek için adım adım bir kılavuz inceledik.

Bu adımları izleyerek, Aspose.Words for .NET'i kullanarak bir OLE nesnesini Word belgelerinize başarıyla simge olarak ekleyebileceksiniz. İstediğiniz sonuçları elde etmek için gerekli referansları içe aktardığınızdan ve talimatları dikkatlice uyguladığınızdan emin olun.

### Word belgesine ole nesnesini simge olarak eklemeyle ilgili SSS

#### S. Aspose.Words for .NET kullanarak bir Word belgesine OLE nesnesini simge olarak eklemek için hangi referanslara ihtiyaç vardır?

C: Aspose.Words for .NET'i kullanmak için aşağıdaki referansları projenize aktarmanız gerekir:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### S. Aspose.Words for .NET'te yeni bir belge ve belge oluşturucu nasıl oluşturulur?

 C: Kullanarak yeni bir belge oluşturabilirsiniz.`Document` sınıf ve bir belge oluşturucu kullanarak`DocumentBuilder` sınıf. İşte bir örnek :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### S. Bir OLE nesnesini belgeye simge olarak nasıl ekleyebilirim?

 C: Belge Oluşturucuyu kullanın`InsertOleObjectAsIcon` OLE nesnesini simge olarak ekleme yöntemi. OLE dosya yolunu, görüntüleme bayrağını, simge yolunu ve katıştırılmış nesne adını belirtin. İşte bir örnek :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### S. OLE nesnesi simge olarak eklenmiş halde belge nasıl kaydedilir?

 C: Belgeyi kullanın`Save` Belgeyi bir dosyaya kaydetme yöntemi. İşte bir örnek :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```