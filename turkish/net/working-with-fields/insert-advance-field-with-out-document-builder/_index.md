---
title: Belge Oluşturucu Olmadan Gelişmiş Alan Ekle
linktitle: Belge Oluşturucu Olmadan Gelişmiş Alan Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word belgelerinize nasıl gelişmiş bir alan ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Aspose.Words for .NET'in "DocumentBuilder olmadan Gelişmiş Alan Ekleme" özelliğini kullanan aşağıdaki C# kaynak kodunu adım adım açıklayan bir kılavuz. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

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

## 3. Adım: Gelişmiş alanı ekleme

 biz kullanıyoruz`AppendField()`paragrafa gelişmiş bir alan ekleme yöntemi.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Ardından, istenen değerleri belirterek gelişmiş alanın çeşitli özelliklerini yapılandırıyoruz.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Son olarak, diyoruz`Update()` alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile DocumentBuilder olmadan gelişmiş bir alan eklemek için kaynak kodu örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Gelişmiş alanı girin.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

Bu örnekte, yeni bir belge oluşturduk, DocumentBuilder kullanmadan gelişmiş bir alan ekledik, çeşitli alan özelliklerini yapılandırdık ve belgeyi belirtilen bir dosya adıyla kaydettik.

Aspose.Words for .NET ile "DocumentBuilder Olmadan Ekle Gelişmiş Alan" özelliğinin nasıl kullanılacağına ilişkin kılavuzumuz burada sona eriyor.

