---
title: İç İçe Alanlar Ekle
linktitle: İç İçe Alanlar Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile iç içe alanları Word belgelerinize nasıl kolayca ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-nested-fields/
---

Aşağıda Aspose.Words for .NET'in "İç İçe Alanları Ekle" özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. İstediğiniz sonuçları elde etmek için her adımı dikkatlice takip ettiğinizden emin olun.

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

## 3. Adım: Sayfa sonları ekleme

Belgeye birden çok sayfa sonu eklemek için döngü kullanırız.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Adım 4: Alt Bilgiye Taşı

 biz kullanıyoruz`MoveToHeaderFooter()` İmleci ana altbilgiye taşımak için DocumentBuilder'ın yöntemi.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Adım 5: Yuvalanmış alanı ekleme

 DocumentBuilder'ı kullanıyoruz`InsertField()` altbilgiye iç içe geçmiş bir alan ekleme yöntemi.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Son olarak şunu diyoruz:`Update()` Alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile iç içe alanların eklenmesi için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi ve DocumentBuilder'ı oluşturun.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sayfa sonları ekleyin.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Altbilgiye git.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// İç içe alan ekleyin.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Alanı güncelleyin.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

Bu örnekte yeni bir belge oluşturduk, sayfa sonları ekledik, imleci alt bilgiye taşıdık ve ardından alt bilgiye iç içe bir alan ekledik.

### SSS'ler

#### S: Aspose.Words for .NET'i kullanarak bir Word belgesine iç içe geçmiş alanları nasıl ekleyebilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesine iç içe alanlar eklemek için şu adımları takip edebilirsiniz:

1. Yuvalanmış alanları eklemek istediğiniz paragrafı alın.
2.  Oluşturmak`FieldStart` ana alan için nesne.
3.  Alt alanları kullanarak ekleyin`FieldStart.NextSibling` karşılık gelenleri geçen yöntem`FieldStart` Parametre olarak nesneler.

#### S: Aspose.Words for .NET ile bir Word belgesinde iç içe geçmiş alanlar kullanmanın faydaları nelerdir?

C: İç içe alanların kullanılması, Aspose.Words for .NET ile bir Word belgesinde çeşitli avantajlar sunar. Bu, değişken değerlerin ve hesaplamaların iç içe geçmiş alanlara eklenmesine izin vererek dinamik belge şablonları oluşturmada daha fazla esneklik sağlar. İç içe alanlar ayrıca içerik tabloları, sayfa numaraları vb. oluşturma gibi otomatik içerik oluşturmayı da kolaylaştırabilir.

#### S: Aspose.Words for .NET ile bir Word belgesinde çok düzeyli iç içe geçmiş alanlara sahip olabilir miyim?

 C: Evet, Aspose.Words for .NET ile bir Word belgesinde çok düzeyli iç içe geçmiş alanlara sahip olmak mümkündür. kullanarak, iç içe geçmiş alanların karmaşık hiyerarşilerini oluşturabilirsiniz.`FieldStart.NextSibling` Mevcut üst alanlara alt alanlar ekleme yöntemi.

#### S: Aspose.Words for .NET ile bir Word belgesindeki iç içe geçmiş alanların özelliklerini nasıl özelleştirebilirim?

 C: Aspose.Words for .NET ile bir Word belgesindeki iç içe geçmiş alanların özelliklerini özelleştirmek için ilgili`FieldStart`nesneleri seçin ve özelliklerini gerektiği gibi değiştirin. İstenilen sonucu elde etmek için iç içe alanların biçimlendirme seçeneklerini, değerlerini, hesaplamalarını vb. ayarlayabilirsiniz.

#### S: İç içe alanların eklenmesi Aspose.Words for .NET'te Word belgesinin performansını etkiler mi?

C: İç içe alanların eklenmesi, özellikle belge çok sayıda iç içe alan veya karmaşık hiyerarşiler içeriyorsa, Aspose.Words for .NET ile Word belgesinin performansını etkileyebilir. Performansı artırmak için iç içe geçmiş alanlarda gereksiz veya tekrarlanan işlemlerden kaçınarak kodun optimize edilmesi önerilir.