---
title: Alan Ekle Belge Oluşturucu Olmadan Metni Ekle
linktitle: Belge Oluşturucu Olmadan FieldIncludeText Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerinize FieldIncludeText alanını nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Aşağıda Aspose.Words for .NET'in "FieldIncludeText alanı ekle" işlevini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstediğiniz sonuçları elde etmek için her adımı dikkatlice takip ettiğinizden emin olun.

## Adım 1: Belge Dizini Kurulumu

Verilen kodda belgelerinizin dizinini belirtmelisiniz. "BELGE DİZİNİNİZ" değerini, belge dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Belgeyi ve Paragrafı Oluşturma

Yeni bir belge oluşturup bir paragrafı başlatarak başlıyoruz.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 3. Adım: FieldIncludeText alanını ekleme

 biz kullanıyoruz`AppendField()` Paragrafa FieldIncludeText alanı ekleme yöntemi.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Daha sonra yer iminin adını ve kaynak dosyanın adını belirterek FieldIncludeText alanının özelliklerini yapılandırıyoruz.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Daha sonra paragrafı belgenin gövdesine ekliyoruz.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Son olarak şunu diyoruz:`Update()` Alanı güncelleme yöntemi.

```csharp
fieldIncludeText.Update();
```

### Aspose.Words for .NET ile FieldIncludeText alanı eklemeye yönelik kaynak kodu örneği

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

Bu örnekte yeni bir belge oluşturduk, bir paragrafa başlangıç değeri verdik, yer imi adını ve kaynak dosya adını belirten bir FieldIncludeTexten ekledik ve belgeyi belirtilen dosya adıyla kaydettik.

Bu, Aspose.Words for .NET ile "FieldIncludeText Ekle" özelliğinin kullanımına ilişkin kılavuzumuzu tamamlıyor.

### SSS'ler

#### S: Aspose.Words for .NET'te metin ekleme alanı için kaynak dosyayı nasıl belirleyebilirim?

 C: Aspose.Words for .NET'te metin ekleme alanının kaynak dosyasını belirtmek için`FieldIncludeText.SourceFullName`Kaynak dosyanın tam yolunu ayarlama özelliği. Kaynak dosyanın erişilebilir olduğundan ve metin ekleme alanına eklemek istediğiniz içeriği içerdiğinden emin olun.

#### S: Aspose.Words for .NET ile metin ekleme alanına bir makrodan metin ekleyebilir miyim?

 C: Evet, Aspose.Words for .NET ile metin ekleme alanına bir makrodan metin ekleyebilirsiniz. Şunu kullanabilirsiniz:`FieldIncludeText.IncludeText` İçeriği alana dahil edilecek makronun adını belirtme özelliği.

#### S: Belge oluşturucu olmadan metin içeren alan eklemek Aspose.Words for .NET ile Word belgesinin yapısını etkiler mi?

C: Belge oluşturucu olmadan bir metin içerme alanı eklemek, Word belgesinin yapısını doğrudan etkilemez. Ancak belge içeriğine yeni bir alan öğesi ekler. Mevcut öğeleri ihtiyaçlarınıza göre ekleyerek, silerek veya değiştirerek belge yapısını değiştirebilirsiniz.

#### S: Aspose.Words for .NET ile bir Word belgesindeki metin ekleme alanının görünümünü özelleştirebilir miyim?

C: Metin ekleme alanı, Word belgesindeki görünümünü doğrudan özelleştirmez. Ancak, Aspose.Words for .NET'te bulunan paragraf özelliklerini, yazı tipi özelliklerini ve diğer biçimlendirme nesnelerini kullanarak dahil edilen metni biçimlendirebilirsiniz.