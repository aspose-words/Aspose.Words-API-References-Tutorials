---
title: Alan Ekle Belge Oluşturucu Olmadan Metni Dahil Et
linktitle: Belge Oluşturucu Olmadan FieldIncludeText Ekleme
second_title: Aspose.Words Belge İşleme API'sı
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

### SSS

#### S: Aspose.Words for .NET'te metin ekleme alanı için kaynak dosyayı nasıl belirleyebilirim?

 C: Aspose.Words for .NET'teki metin ekleme alanı için kaynak dosyayı belirtmek üzere`FieldIncludeText.SourceFullName`kaynak dosyanın tam yolunu ayarlamak için özellik. Kaynak dosyanın erişilebilir olduğundan ve metin ekleme alanına eklemek istediğiniz içeriği içerdiğinden emin olun.

#### S: Aspose.Words for .NET ile metin ekleme alanına bir makrodan metin ekleyebilir miyim?

 C: Evet, Aspose.Words for .NET ile metin ekleme alanına bir makrodan metin ekleyebilirsiniz. kullanabilirsiniz`FieldIncludeText.IncludeText` içeriği alana dahil edilmesi gereken makronun adını belirtmek için özelliği.

#### S: Belge oluşturucu olmadan bir metin içerme alanı eklemek, Aspose.Words for .NET ile Word belge yapısını etkiler mi?

C: Belge oluşturucu olmadan bir metin içerme alanı eklemek, Word belgesinin yapısını doğrudan etkilemez. Ancak belge içeriğine yeni bir alan öğesi ekler. Mevcut öğeleri ihtiyaçlarınıza göre ekleyerek, silerek veya değiştirerek belge yapısını değiştirebilirsiniz.

#### S: Aspose.Words for .NET ile bir Word belgesindeki metin ekleme alanının görünümünü özelleştirebilir miyim?

C: Metin dahil etme alanı, bir Word belgesindeki görünümünü doğrudan özelleştirmez. Ancak, dahil edilen metni, Aspose.Words for .NET'te bulunan paragraf özelliklerini, yazı tipi özelliklerini ve diğer biçimlendirme nesnelerini kullanarak biçimlendirebilirsiniz.