---
title: ASKField'ı Document Builder Olmadan Ekle
linktitle: ASKField'ı Document Builder Olmadan Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile Word belgelerinize nasıl ASK alanı ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Aspose.Words for .NET'in "DocumentBuilder olmadan bir ASK alanı ekle" özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi ve Paragrafı Oluşturma

Yeni bir belge oluşturarak ve ilk paragrafı getirerek başlıyoruz.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 3. Adım: ASK alanını ekleme

 biz kullanıyoruz`AppendField()` paragrafa bir ASK alanı ekleme yöntemi.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Ardından, istenen değerleri belirterek ASK alanının çeşitli özelliklerini yapılandırıyoruz.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Son olarak, diyoruz`Update()` alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile DocumentBuilder olmadan bir ASK alanı eklemek için kaynak kod örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// ASK alanını girin.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Bu örnekte yeni bir belge oluşturduk, DocumentBuilder kullanmadan bir ASK alanı ekledik, alanın çeşitli özelliklerini yapılandırdık ve belgeyi belirtilen bir dosya adıyla kaydettik.

Aspose.Words for .NET ile "DocumentBuilder Olmadan ASK Alanı Ekle" özelliğinin kullanımına ilişkin kılavuzumuz burada sona eriyor.

### SSS

#### S: Aspose.Words'te ASK alanı nedir?

A: Aspose.Words'teki bir SOR alanı, bir belgeyi açarken kullanıcıya soru sormak için kullanılır. Genellikle, kullanıcıdan kullanıcıya değişebilen belirli bilgileri veya geri bildirimi istemek için kullanılır.

#### S: Aspose.Words'te Document Builder kullanmadan Word belgesine ASK alanı nasıl eklenir?

C: Aspose.Words'te Document Builder'ı kullanmadan bir Word belgesine ASK alanı eklemek için şu adımları izleyebilirsiniz:

1. Aspose.Words.Fields ad alanından Belge ve Alan sınıfını içe aktarın.
2. Mevcut belgenizi yükleyerek bir Belge örneği oluşturun.
3. Soru adını belirterek bir ASK alanı eklemek için InsertField yöntemini kullanın.
4. Belgeyi kaydedin.

#### S: Bir Word belgesindeki ASK alanı için kullanıcı yanıtını nasıl alabilirim?

C: Kullanıcının bir Word belgesindeki ASK alanına yanıtını almak için, Document sınıfında bulunan GetFieldNames yöntemini kullanabilirsiniz. Bu yöntem, belgede bulunan alanların adlarının bir listesini döndürür. Ardından ASK alan adının listede olup olmadığını kontrol edebilir ve ilgili yanıtı alabilirsiniz.

#### S: ASK alanı, kullanıcıdan daha fazla bilgi istemek için kullanılabilir mi?

C: Evet, ASK alanı kullanıcıdan birden çok bilgi istemek için kullanılabilir. Belgenize, her biri farklı bir soru içeren birden çok ASK alanı ekleyebilirsiniz. Belge açıldığında, kullanıcıdan ilgili yanıtlar istenecektir.