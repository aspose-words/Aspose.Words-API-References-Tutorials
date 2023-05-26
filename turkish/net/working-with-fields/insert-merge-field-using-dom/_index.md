---
title: DOM Kullanarak Birleştirme Alanı Ekleme
linktitle: DOM Kullanarak Birleştirme Alanı Ekleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile özel alan birleştirme alanlarını Word belgelerinize nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-merge-field-using-dom/
---

Aspose.Words for .NET'in "Alan Birleştirme Alanı Ekle" özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Document ve DocumentBuilder'ı Oluşturma

Yeni bir belge oluşturarak ve bir DocumentBuilder başlatarak başlıyoruz.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: İmleci paragrafa taşıma

 biz kullanıyoruz`MoveTo()` İmleci alan birleştirme alanını eklemek istediğimiz paragrafa taşımak için DocumentBuilder yöntemi.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## 4. Adım: Alan birleştirme alanını ekleme

 DocumentBuilder'ı kullanıyoruz`InsertField()` paragrafa alan birleştirme alanı ekleme yöntemi.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Ardından, alan adı, alandan önceki ve sonraki metin ve dikey biçimlendirme seçenekleri gibi uygun seçenekleri belirterek alan birleştirme alanı özelliklerini yapılandırıyoruz.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Son olarak, diyoruz`Update()` alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile alan birleştirme alanı eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi ve DocumentBuilder'ı oluşturun.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İmleci paragrafa taşıyın.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Alan birleştirme alanı ekleyin.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Alanı güncelleyin.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

Bu örnekte, yeni bir belge oluşturduk, imleci istenen paragrafa taşıdık ve ardından belgeye bir alan birleştirme alanı ekledik.