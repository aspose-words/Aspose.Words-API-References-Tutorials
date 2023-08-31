---
title: Belge Oluşturucu Olmadan ASKField'ı Ekle
linktitle: Belge Oluşturucu Olmadan ASKField'ı Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinize nasıl ASK alanı ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Aşağıda Aspose.Words for .NET'in "DocumentBuilder olmadan bir ASK alanı ekle" özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstediğiniz sonuçları elde etmek için her adımı dikkatlice takip ettiğinizden emin olun.

## Adım 1: Belge Dizini Kurulumu

Verilen kodda belgelerinizin dizinini belirtmelisiniz. "BELGE DİZİNİNİZ" değerini, belge dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi ve Paragrafı Oluşturma

Yeni bir belge oluşturup ilk paragrafı getirerek başlıyoruz.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 3. Adım: ASK alanını ekleme

 biz kullanıyoruz`AppendField()` Paragrafa ASK alanı ekleme yöntemi.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Daha sonra istenilen değerleri belirterek ASK alanının çeşitli özelliklerini yapılandırıyoruz.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Son olarak şunu diyoruz:`Update()` Alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile DocumentBuilder olmadan ASK alanı eklemek için kaynak kodu örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// ASK alanını ekleyin.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Bu örnekte yeni bir belge oluşturduk, DocumentBuilder kullanmadan bir ASK alanı ekledik, alanın çeşitli özelliklerini yapılandırdık ve belgeyi belirtilen dosya adıyla kaydettik.

Bu, Aspose.Words for .NET ile "DocumentBuilder Olmadan ASK Alanını Ekle" özelliğinin kullanımına ilişkin kılavuzumuzu tamamlıyor.

### SSS'ler

#### S: Aspose.Words'teki ASK alanı nedir?

C: Aspose.Words'teki ASK alanı, bir belgeyi açarken kullanıcıya soru sormak için kullanılır. Genellikle kullanıcıdan kullanıcıya değişebilecek belirli bilgi veya geri bildirim istemek için kullanılır.

#### S: Aspose.Words'te Belge Oluşturucuyu kullanmadan Word belgesine ASK alanı nasıl eklenir?

C: Aspose.Words'te Belge Oluşturucuyu kullanmadan bir Word belgesine ASK alanı eklemek için şu adımları takip edebilirsiniz:

1. Aspose.Words.Fields ad alanından Document ve Field sınıfını içe aktarın.
2. Mevcut belgenizi yükleyerek bir Belge örneği oluşturun.
3. Soru adını belirterek bir ASK alanı eklemek için InsertField yöntemini kullanın.
4. Belgeyi kaydedin.

#### S: Word belgesindeki ASK alanı için kullanıcı yanıtını nasıl alabilirim?

C: Bir Word belgesindeki ASK alanına ilişkin kullanıcının yanıtını almak için Document sınıfında bulunan GetFieldNames yöntemini kullanabilirsiniz. Bu yöntem, belgede bulunan alanların adlarının bir listesini döndürür. Daha sonra listede ASK alan adının mevcut olup olmadığını kontrol edebilir ve ilgili yanıtı alabilirsiniz.

#### S: ASK alanı kullanıcıdan daha fazla bilgi istemek için kullanılabilir mi?

C: Evet, ASK alanı kullanıcıdan birden fazla bilgi istemek için kullanılabilir. Belgenize her biri farklı bir soru içeren birden fazla ASK alanı ekleyebilirsiniz. Belge açıldığında kullanıcıdan ilgili yanıtlar istenecektir.