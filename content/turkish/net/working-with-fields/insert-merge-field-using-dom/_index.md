---
title: DOM Kullanarak Birleştirme Alanı Ekle
linktitle: DOM Kullanarak Birleştirme Alanı Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile özel alan birleştirme alanlarını Word belgelerinize nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-merge-field-using-dom/
---

Aşağıda Aspose.Words for .NET'in "Alan Birleştirme Alanı Ekle" özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstediğiniz sonuçları elde etmek için her adımı dikkatlice takip ettiğinizden emin olun.

## Adım 1: Belge Dizini Kurulumu

Verilen kodda belgelerinizin dizinini belirtmelisiniz. "BELGE DİZİNİNİZ" değerini, belge dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Document ve DocumentBuilder'ı Oluşturma

Yeni bir belge oluşturup DocumentBuilder'ı başlatarak başlıyoruz.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: İmleci paragrafa taşıma

 biz kullanıyoruz`MoveTo()` İmleci alan birleştirme alanını eklemek istediğimiz paragrafa taşımak için DocumentBuilder'ın yöntemini kullanın.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## 4. Adım: Alan birleştirme alanını ekleme

 DocumentBuilder'ı kullanıyoruz`InsertField()` Paragrafa alan birleştirme alanı ekleme yöntemi.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Daha sonra alan adı, alandan önceki ve sonraki metin ve dikey biçimlendirme seçenekleri gibi uygun seçenekleri belirterek alan birleştirme alan özelliklerini yapılandırıyoruz.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Son olarak şunu diyoruz:`Update()` Alanı güncelleme yöntemi.

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

Bu örnekte yeni bir belge oluşturduk, imleci istenen paragrafa taşıdık ve ardından belgeye bir alan birleştirme alanı ekledik.

### SSS'ler

#### S: Aspose.Words for .NET'i DOM ile kullanarak bir Word belgesine nasıl birleştirme alanı ekleyebilirim?

C: DOM ile Aspose.Words for .NET kullanarak bir Word belgesine birleştirme alanı eklemek için şu adımları takip edebilirsiniz:

1. Birleştirme alanını eklemek istediğiniz paragrafa gidin.
2.  Oluşturmak`FieldMergeField` nesne.
3. Alan adı ve biçimlendirme seçenekleri gibi birleştirme alanı özelliklerini ayarlayın.
4.  kullanarak birleştirme alanını paragrafa ekleyin.`Paragraph.AppendChild` yöntem.

#### S: Aspose.Words for .NET'te birleştirme alanı için kaynak verileri nasıl belirleyebilirim?

C: Aspose.Words for .NET'te birleştirme alanının kaynak verilerini belirtmek için`FieldMergeField.FieldName` CSV dosyası, veritabanı vb. gibi harici bir veri kaynağındaki alanın adı olan birleştirme alanı adını ayarlama yöntemini kullanın.`FieldMergeField.Text` Birleştirme alanı değerini doğrudan ayarlama yöntemi.

#### S: Aspose.Words for .NET ile bir Word belgesindeki birleştirme alanının görünümünü özelleştirebilir miyim?

 C: Evet, Aspose.Words for .NET ile Word belgesindeki birleştirme alanının görünümünü özelleştirebilirsiniz. Özelliklerini kullanarak büyük/küçük harf, yazı tipi, renk vb. biçimlendirme seçeneklerini ayarlayabilirsiniz.`FieldMergeField` nesne.

#### S: Aspose.Words for .NET ile bir Word belgesine birleştirme alanının başarıyla eklenip eklenmediğini nasıl kontrol edebilirim?

 C: Birleştirme alanının başarıyla eklenip eklenmediğini kontrol etmek için belge içeriğine göz atabilir ve birleştirme alanı örneklerini arayabilirsiniz. Yöntemlerini ve özelliklerini kullanabilirsiniz.`Document` Belgenin paragraflarına, alanlarına ve diğer öğelerine erişim nesnesi.

#### S: DOM kullanarak birleştirme alanı eklemek Aspose.Words for .NET ile Word belgesinin yapısını etkiler mi?

C: DOM kullanarak birleştirme alanı eklemek, Word belgesinin yapısını doğrudan etkilemez. Ancak belge içeriğine yeni bir alan öğesi ekler. Mevcut öğeleri ihtiyaçlarınıza göre ekleyerek, silerek veya değiştirerek belge yapısını değiştirebilirsiniz.