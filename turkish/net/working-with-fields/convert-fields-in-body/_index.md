---
title: Gövdedeki Alanları Dönüştür
linktitle: Gövdedeki Alanları Dönüştür
second_title: Aspose.Words for .NET API Referansı
description: Sayfa alanlarını bir Word belgesinin gövdesindeki metne dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/convert-fields-in-body/
---

Bu adım adım öğreticide, sağlanan C# kaynak kodunu kullanarak Aspose.Words for .NET'in ConvertFieldsInBody özelliğini nasıl kullanacağınız konusunda size yol göstereceğiz. Bu özellik, belgenizin gövdesindeki belirli alanları düz metne dönüştürmenizi sağlayarak belgelerinizin işlenmesini kolaylaştırır. Bu özelliği etkin bir şekilde kullanmak için aşağıdaki adımları izleyin.

## 1. Adım: Önkoşullar

Başlamadan önce, Aspose.Words for .NET'i kurduğunuzdan ve işlenmeye hazır bir belgeniz olduğundan emin olun. Ayrıca belgelerinize giden dizin yoluna sahip olduğunuzdan emin olun.

## 2. Adım: Belgeyi yükleyin

Belgeler dizininizin yolu için bir değişken bildirerek başlayın, ardından belirtilen belgeden bir Belge nesnesi başlatmak için bu değişkeni kullanın. Örneğimizde belgenin adı "Bağlantılı alanlar.docx".

```csharp
// Belgeler dizininizin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//belgeyi yükle
Document doc = new Document(dataDir + "Linked fields.docx");
```

## 3. Adım: Sayfa Alanlarını Düz Metne Dönüştürün

Belge yüklendiğine göre artık dönüştürme adımlarına geçebiliriz. İlk bölümün gövdesindeki sayfa alanlarını düz metne dönüştürmek için`Range.Fields` belirtilen aralıktaki tüm alanları alma ve ardından tür alanlarını filtreleme yöntemi`FieldType.FieldPage` . Sonra kullanabilirsiniz`ForEach` her alanda döngü yapmak ve çağırmak için yöntem`Unlink()` düz metne dönüştürme yöntemi.

```csharp
// Sayfa alanlarını ilk bölümün gövdesinde düz metne dönüştürmek için uygun parametreleri iletin.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## 4. Adım: Değiştirilen belgeyi kaydedin

 Sayfa alanlarını düz metne dönüştürdükten sonra, değiştirilmiş belgeyi kullanarak kaydedebilirsiniz.`Save()` yöntemi ve çıktı dosyasının yolunu ve adını belirtme. Örneğimizde "WorkingWithFields.ConvertFieldsInBody.docx" olarak kaydediyoruz.

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Aspose.Words for .NET ile gövdedeki alanları dönüştürmek için örnek kaynak kodu

İşte Aspose.Words for .NET kullanarak alanları gövdeye dönüştürmek için tam kaynak kodu örneği:

```csharp
// Belgeler dizininizin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//belgeyi yükle
Document doc = new Document(dataDir + "Linked fields.docx");

// Sayfa alanlarını ilk bölümün gövdesinde düz metne dönüştürmek için uygun parametreleri iletin.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
