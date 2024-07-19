---
title: Belge Oluşturucu Olmadan Gelişmiş Alan Ekle
linktitle: Belge Oluşturucu Olmadan Gelişmiş Alan Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinize nasıl gelişmiş alan ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Aşağıda Aspose.Words for .NET'in "DocumentBuilder Olmadan Gelişmiş Alan Ekleme" özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstediğiniz sonuçları elde etmek için her adımı dikkatlice takip ettiğinizden emin olun.

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

## 3. Adım: Gelişmiş alanı ekleme

 biz kullanıyoruz`AppendField()` paragrafa gelişmiş alan ekleme yöntemi.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Daha sonra istenilen değerleri belirterek gelişmiş alanın çeşitli özelliklerini yapılandırıyoruz.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Son olarak şunu diyoruz:`Update()` Alanı güncelleme yöntemi.

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

// Gelişmiş alanı ekleyin.
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

Bu örnekte yeni bir belge oluşturduk, DocumentBuilder'ı kullanmadan gelişmiş bir alan ekledik, çeşitli alan özelliklerini yapılandırdık ve belgeyi belirtilen dosya adıyla kaydettik.

Bu, Aspose.Words for .NET ile "DocumentBuilder Olmadan Gelişmiş Alan Ekle" özelliğinin nasıl kullanılacağına ilişkin kılavuzumuzu tamamlıyor.

### SSS'ler

#### S: Aspose.Words'ün gelişmiş alanı nedir?

C: Aspose.Words'deki Gelişmiş Alan, bir Word belgesinde hesaplamalar yapmanıza, koşullar eklemenize ve karmaşık işlemler gerçekleştirmenize olanak tanıyan özel bir alan türüdür. Dinamik ve özel alanlar oluşturmak için büyük esneklik sunar.

#### S: Aspose.Words'te Belge Oluşturucuyu kullanmadan Word belgesine gelişmiş alan nasıl eklenir?

C: Aspose.Words'te Belge Oluşturucu'yu kullanmadan Word belgesine gelişmiş bir alan eklemek için şu adımları takip edebilirsiniz:

1. Aspose.Words.Fields ad alanından Document ve Field sınıfını içe aktarın.
2. Mevcut belgenizi yükleyerek bir Belge örneği oluşturun.
3. Gelişmiş alan kodunu belirterek gelişmiş bir alan eklemek için InsertField yöntemini kullanın.
4. Belgeyi kaydedin.

#### S: Word belgesindeki gelişmiş bir alanın sonucu nasıl alınır?

C: Word belgesindeki gelişmiş bir alanın sonucunu almak için Field sınıfında bulunan Result özelliğini kullanabilirsiniz. Bu özellik alanın hesaplanan sonucunu döndürür.

#### S: Gelişmiş bir alanın formülünü Word belgesine ekledikten sonra değiştirebilir miyim?

C: Evet, gelişmiş bir alanın formülünü Word belgesine ekledikten sonra düzenleyebilirsiniz. Bunu, Field sınıfının FieldCode özelliğine erişerek ve formül metnini değiştirerek formülü güncelleyerek yapabilirsiniz.