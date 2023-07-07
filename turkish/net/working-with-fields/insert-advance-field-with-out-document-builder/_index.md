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

 biz kullanıyoruz`AppendField()` paragrafa gelişmiş bir alan ekleme yöntemi.

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

### SSS

#### S: Aspose.Words'te gelişmiş alan nedir?

C: Aspose.Words'teki Gelişmiş Alan, bir Word belgesinde hesaplamalar yapmanıza, koşullar eklemenize ve karmaşık işlemler gerçekleştirmenize izin veren özel bir alan türüdür. Dinamik ve özel alanlar oluşturmak için büyük esneklik sunar.

#### S: Aspose.Words'te Document Builder kullanmadan bir Word belgesine nasıl gelişmiş bir alan eklenir?

C: Aspose.Words'te Document Builder'ı kullanmadan bir Word belgesine gelişmiş bir alan eklemek için şu adımları izleyebilirsiniz:

1. Aspose.Words.Fields ad alanından Belge ve Alan sınıfını içe aktarın.
2. Mevcut belgenizi yükleyerek bir Belge örneği oluşturun.
3. Gelişmiş alan kodunu belirterek gelişmiş bir alan eklemek için InsertField yöntemini kullanın.
4. Belgeyi kaydedin.

#### S: Bir Word belgesinde gelişmiş bir alanın sonucu nasıl alınır?

C: Bir Word belgesindeki gelişmiş bir alanın sonucunu almak için Field sınıfında bulunan Result özelliğini kullanabilirsiniz. Bu özellik, alanın hesaplanan sonucunu döndürür.

#### S: Gelişmiş bir alanın formülünü bir Word belgesine ekledikten sonra değiştirebilir miyim?

C: Evet, gelişmiş bir alanın formülünü bir Word belgesine ekledikten sonra düzenleyebilirsiniz. Bunu, Field sınıfının FieldCode özelliğine erişerek ve formül metnini değiştirerek formülü güncelleyerek yapabilirsiniz.