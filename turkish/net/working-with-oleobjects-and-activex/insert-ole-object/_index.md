---
title: Word Belgesine Ole Nesnesi Ekleme
linktitle: Word Belgesine Ole Nesnesi Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir OLE nesnesini word belgesine nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Aşağıda, Aspose.Words for .NET kullanılarak bir OLE nesnesinin word belgesine nasıl ekleneceğini gösteren C# kaynak kodunu adım adım açıklayan bir kılavuz bulunmaktadır.

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
 Belge Oluşturucu'yu kullanın`InsertOleObject`belgeye bir OLE nesnesi ekleme yöntemi. OLE nesne URL'sini, nesne türünü, görüntüleme seçeneklerini ve diğer gerekli ayarları belirtin.

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

## Çözüm

Sonuç olarak, OLE nesnelerini bir Word belgesine eklemek, Aspose.Words for .NET tarafından sunulan güçlü bir özelliktir. Bu kitaplığı kullanarak HTML dosyaları, Excel elektronik tabloları, PowerPoint sunumları vb. gibi OLE nesnelerini Word belgelerinize kolayca gömebilirsiniz.

Bu makalede, bir OLE nesnesinin bir Word belgesine nasıl ekleneceğini gösteren C# kaynak kodunu açıklayan adım adım bir kılavuzdan geçtik. Gerekli referansları, yeni bir belge ve belge oluşturucu oluşturmayı ve bir OLE nesnesi ekleme ve belgeyi kaydetme adımlarını ele aldık.

### Bir Word belgesine OLE nesnesi eklemekle ilgili SSS

#### S: Aspose.Words for .NET'i kullanmak için hangi kimlik bilgilerine ihtiyacım var?

C: Aspose.Words for .NET'i kullanmak için aşağıdaki referansları içe aktarmanız gerekir:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### S: Yeni bir belge ve belge oluşturucu nasıl oluşturulur?

 A: kullanarak yeni bir belge oluşturabilirsiniz.`Document` sınıfını ve bir belge oluşturucuyu kullanarak`DocumentBuilder` sınıf, aşağıda gösterildiği gibi:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### S: Belgeye bir OLE nesnesi nasıl eklenir?

 C: Şunu kullanın:`InsertOleObject` belge oluşturucunun yöntemi (`DocumentBuilder`) belgeye bir OLE nesnesi eklemek için. OLE nesne URL'sini, nesne türünü, görüntüleme seçeneklerini ve diğer gerekli ayarları belirtin. İşte bir örnek :

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmldosyası", doğru, doğru, boş);
```

#### S: Belge nasıl kaydedilir?

 C: Belgeyi kullanın`Save`Belgeyi bir dosyaya kaydetme yöntemi. İşte bir örnek :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### S: Aspose.Words for .NET ile bir OLE nesnesi eklemenin tam bir örneğini verebilir misiniz?

A: İşte Aspose.Words for .NET ile bir OLE nesnesi eklemek için eksiksiz bir örnek kod. Bu kodu projenize entegre etmek için gerekli referansları içe aktardığınızdan ve daha önce açıklanan adımları uyguladığınızdan emin olun:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmldosyası", doğru, doğru, boş);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
