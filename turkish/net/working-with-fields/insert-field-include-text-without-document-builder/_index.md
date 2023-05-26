---
title: Belge Oluşturucu Olmadan FieldIncludeText Ekleme
linktitle: Belge Oluşturucu Olmadan FieldIncludeText Ekleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerinize FieldIncludeText alanını nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Aspose.Words for .NET'in "Bir FieldIncludeText alanı ekle" işlevini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi ve Paragrafı Oluşturma

Yeni bir belge oluşturarak ve bir paragraf başlatarak başlıyoruz.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 3. Adım: FieldIncludeText alanını ekleme

 biz kullanıyoruz`AppendField()` Paragrafa bir FieldIncludeText alanı eklemek için yöntem.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Ardından, yer işaretinin adını ve kaynak dosyanın adını belirterek FieldIncludeText alanının özelliklerini yapılandırıyoruz.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Ardından, paragrafı belgenin gövdesine ekliyoruz.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Son olarak, diyoruz`Update()` alanı güncelleme yöntemi.

```csharp
fieldIncludeText.Update();
```

### Aspose.Words for .NET ile bir FieldIncludeText alanı eklemek için kaynak kodu örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi ve paragrafı oluşturun.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// FieldIncludeText alanını ekleyin.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

Bu örnekte, yeni bir belge oluşturduk, bir paragraf başlattık, yer imi adını ve kaynak dosya adını belirten bir FieldIncludeTexten ekledik ve belgeyi belirtilen bir dosya adıyla kaydettik.

Bu, Aspose.Words for .NET ile "Insert a FieldIncludeText" özelliğini kullanma konusundaki kılavuzumuzu sonlandırıyor.