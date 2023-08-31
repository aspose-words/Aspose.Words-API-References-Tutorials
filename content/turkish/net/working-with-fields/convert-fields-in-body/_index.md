---
title: Gövdedeki Alanları Dönüştür
linktitle: Gövdedeki Alanları Dönüştür
second_title: Aspose.Words Belge İşleme API'si
description: Sayfa alanlarını bir Word belgesinin gövdesindeki metne dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/convert-fields-in-body/
---

Bu adım adım eğitimde, sağlanan C# kaynak kodunu kullanarak Aspose.Words for .NET'in ConvertFieldsInBody özelliğini nasıl kullanacağınız konusunda size yol göstereceğiz. Bu özellik, belgenizin gövdesindeki belirli alanları düz metne dönüştürmenize olanak tanıyarak belgelerinizin işlenmesini kolaylaştırır. Bu özelliği etkili bir şekilde kullanmak için aşağıdaki adımları izleyin.

## 1. Adım: Önkoşullar

Başlamadan önce Aspose.Words for .NET'i yüklediğinizden ve işlenmeye hazır bir belgeye sahip olduğunuzdan emin olun. Ayrıca belgelerinizin dizin yoluna sahip olduğunuzdan emin olun.

## 2. Adım: Belgeyi yükleyin

Belgeler dizininizin yolu için bir değişken bildirerek başlayın, ardından bu değişkeni belirtilen belgeden bir Belge nesnesini başlatmak için kullanın. Örneğimizde belgenin adı "Bağlantılı alanlar.docx".

```csharp
// Belgeler dizininizin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Linked fields.docx");
```

## 3. Adım: Sayfa Alanlarını Düz Metne Dönüştürün

 Artık belge yüklendiğine göre dönüştürme adımlarına geçebiliriz. İlk bölümün gövdesindeki sayfa alanlarını düz metne dönüştürmek için`Range.Fields` belirtilen aralıktaki tüm alanları alma ve ardından türdeki alanları filtreleme yöntemi`FieldType.FieldPage` . Daha sonra şunu kullanabilirsiniz:`ForEach` her alanda döngü yapma ve arama yöntemini kullanma`Unlink()` düz metne dönüştürme yöntemi.

```csharp
// İlk bölümün gövdesinde sayfa alanlarını düz metne dönüştürmek için uygun parametreleri iletin.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## 4. Adım: Değiştirilen belgeyi kaydedin

Sayfa alanlarını düz metne dönüştürdükten sonra, değiştirilen belgeyi aşağıdaki düğmeyi kullanarak kaydedebilirsiniz:`Save()` yöntemi ve çıktı dosyasının yolunu ve adını belirtme. Örneğimizde "WorkingWithFields.ConvertFieldsInBody.docx" olarak kaydediyoruz.

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Aspose.Words for .NET ile gövdedeki alanları dönüştürmek için örnek kaynak kodu

Aspose.Words for .NET kullanarak alanları gövdeye dönüştürmek için tam kaynak kodu örneği:

```csharp
// Belgeler dizininizin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Linked fields.docx");

// İlk bölümün gövdesinde sayfa alanlarını düz metne dönüştürmek için uygun parametreleri iletin.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### SSS'ler

#### S: Aspose.Words, Microsoft Word'ün farklı sürümleriyle uyumlu mudur?

C: Evet, Aspose.Words, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 ve Word 2019 dahil olmak üzere Microsoft Word'ün çeşitli sürümleriyle uyumludur.

#### S: Aspose.Words karmaşık alan yapılarını yönetebilir mi?

C: Kesinlikle! Aspose.Words, iç içe alanlar, hesaplamalar ve koşullu ifadeler dahil olmak üzere karmaşık alan yapıları için kapsamlı destek sağlar. Her türlü alan yapısıyla çalışmak için güçlü API'den yararlanabilirsiniz.

#### S: Aspose.Words alan güncelleme işlemlerini destekliyor mu?

C: Evet, Aspose.Words alanları programlı olarak güncellemenize olanak sağlar. API'yi kullanarak alan değerlerini kolayca güncelleyebilir, hesaplamaları yenileyebilir ve alanla ilgili diğer işlemleri gerçekleştirebilirsiniz.

#### S: Aspose.Words'ü kullanarak alanları düz metne dönüştürebilir miyim?

C: Kesinlikle! Aspose.Words, alanları düz metne dönüştürmek için yöntemler sağlar. Bu, alanla ilgili herhangi bir biçimlendirme veya işlevsellik olmadan içeriği çıkarmanız gerektiğinde yararlı olabilir.

#### S: Aspose.Words'ü kullanarak dinamik alanlara sahip Word belgeleri oluşturmak mümkün müdür?

C: Kesinlikle! Aspose.Words, dinamik alanlarla Word belgeleri oluşturmak için güçlü özellikler sunar. Önceden tanımlanmış alanlara sahip şablonlar oluşturabilir ve bunları dinamik olarak verilerle doldurarak esnek ve verimli bir belge oluşturma çözümü sağlayabilirsiniz.