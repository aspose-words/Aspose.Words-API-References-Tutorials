---
title: İç İçe Alanlar Ekle
linktitle: İç İçe Alanlar Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile iç içe geçmiş alanları Word belgelerinize kolayca nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-nested-fields/
---

Aşağıda, Aspose.Words for .NET'in "İç İçe Alanları Ekle" özelliğini kullanan C# kaynak kodunu adım adım açıklayan bir kılavuz bulunmaktadır. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

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

## 3. Adım: Sayfa sonları ekleme

Belgeye birden fazla sayfa sonu eklemek için bir döngü kullanıyoruz.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## 4. Adım: Altbilgiye Taşıyın

 biz kullanıyoruz`MoveToHeaderFooter()` İmleci ana altbilgiye taşımak için DocumentBuilder yöntemi.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Adım 5: İç içe alan ekleme

 DocumentBuilder'ı kullanıyoruz`InsertField()`altbilgiye iç içe geçmiş bir alan ekleme yöntemi.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Son olarak, diyoruz`Update()` alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile iç içe alanlar eklemek için örnek kaynak kodu

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

Bu örnekte, yeni bir belge oluşturduk, sayfa sonları ekledik, imleci alt bilgiye taşıdık ve ardından alt bilgiye iç içe bir alan ekledik.

### SSS

#### S: Aspose.Words for .NET kullanarak bir Word belgesine iç içe geçmiş alanları nasıl ekleyebilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesine iç içe alanlar eklemek için şu adımları takip edebilirsiniz:

1. İç içe alanları eklemek istediğiniz paragrafı alın.
2.  Oluşturmak`FieldStart` üst alan için nesne.
3.  kullanarak alt alanları ekleyin.`FieldStart.NextSibling` karşılık gelen yöntemi`FieldStart` nesneleri parametre olarak

#### S: Aspose.Words for .NET ile bir Word belgesinde iç içe alanlar kullanmanın faydaları nelerdir?

C: İç içe alanların kullanılması, Aspose.Words for .NET ile bir Word belgesinde çeşitli avantajlar sunar. Bu, iç içe alanlara değişken değerlerin ve hesaplamaların eklenmesine izin vererek dinamik belge şablonları oluşturmada daha fazla esneklik sağlar. İç içe alanlar, içerik tabloları, sayfa numaraları vb. oluşturmak gibi otomatik içerik oluşturmayı da kolaylaştırabilir.

#### S: Aspose.Words for .NET ile bir Word belgesinde çok düzeyli iç içe alanlar olabilir mi?

 C: Evet, Aspose.Words for .NET ile bir Word belgesinde çok düzeyli iç içe alanlara sahip olmak mümkündür. kullanarak iç içe alanların karmaşık hiyerarşilerini oluşturabilirsiniz.`FieldStart.NextSibling` alt alanları mevcut üst alanlara ekleme yöntemi.

#### S: Aspose.Words for .NET ile bir Word belgesindeki iç içe geçmiş alanların özelliklerini nasıl özelleştirebilirim?

 C: Aspose.Words for .NET ile bir Word belgesindeki iç içe geçmiş alanların özelliklerini özelleştirmek için ilgili`FieldStart`nesneleri ve özelliklerini gerektiği gibi değiştirin. İstediğiniz sonucu elde etmek için iç içe geçmiş alanların biçimlendirme seçeneklerini, değerlerini, hesaplamalarını vb. ayarlayabilirsiniz.

#### S: İç içe alanlar eklemek, Aspose.Words for .NET ile Word belgesi performansını etkiler mi?

Y: İç içe alanların eklenmesi, özellikle belge çok sayıda iç içe alan veya karmaşık hiyerarşiler içeriyorsa, Aspose.Words for .NET ile Word belgesi performansını etkileyebilir. Performansı artırmak için iç içe geçmiş alanlarda gereksiz veya tekrarlanan işlemlerden kaçınarak kodun optimize edilmesi önerilir.