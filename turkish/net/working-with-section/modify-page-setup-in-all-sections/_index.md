---
title: Tüm Bölümlerde Sayfa Düzenini Değiştirin
linktitle: Tüm Bölümlerde Sayfa Düzenini Değiştirin
second_title: Aspose.Words for .NET API Referansı
description: Bu öğreticide, Aspose.Words for .NET ile bir Word belgesinin tüm bölümlerindeki sayfa düzenini nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-section/modify-page-setup-in-all-sections/
---

Bu öğreticide, size Aspose.Words .NET kitaplığını kullanarak bir Word belgesinin tüm bölümlerindeki sayfa düzenini nasıl değiştireceğinizi göstereceğiz. Sayfa düzenini değiştirmek, kağıt boyutu, kenar boşlukları, yönlendirme vb. ayarları içerebilir. Kodu anlamanıza ve .NET projenizde uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Bir belge oluşturun ve içerik ve bölümler ekleyin
Ardından, örnekleyerek boş bir belge oluşturacağız.`Document` sınıf ve ilgili`DocumentBuilder` Belgeye içerik ve bölümler eklemek için yapıcı. Bu örnekte içerik ve üç bölüm ekliyoruz.

```csharp
// Bir belge oluştur
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İçerik ve bölümler ekleyin
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

## 3. Adım: Tüm bölümlerde sayfa düzenini düzenleyin
 Belgenin tüm bölümlerinde sayfa düzenini değiştirmek için bir`foreach` her bölüm boyunca döngü ve erişim için döngü`PageSetup` mülk. Bu örnekte, değeri olarak ayarlayarak tüm bölümlerin kağıt boyutunu değiştiriyoruz.`PaperSize.Letter`.

```csharp
foreach(Section section in doc.Sections)
     section.PageSetup.PaperSize = PaperSize.Letter;
```

### Aspose.Words for .NET kullanarak Tüm Bölümlerde Sayfa Düzenini Değiştirmek için örnek kaynak kodu 

```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");

// Bir belgenin birçok bölüm içerebileceğini anlamak önemlidir.
// ve her bölümün kendi sayfa düzeni vardır. Bu durumda, hepsini değiştirmek istiyoruz.
foreach (Section section in doc)
	section.PageSetup.PaperSize = PaperSize.Letter;
doc.Save(dataDir + "WorkingWithSection.ModifyPageSetupInAllSections.doc");

```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinin tüm bölümlerinde sayfa düzenini nasıl değiştireceğimizi gördük. Açıklanan adımları izleyerek her bölüme kolayca erişebilir ve sayfa yapılandırma ayarlarını özelleştirebilirsiniz. Özel ihtiyaçlarınızı karşılamak için bu özelliği uyarlamaktan ve kullanmaktan çekinmeyin.
