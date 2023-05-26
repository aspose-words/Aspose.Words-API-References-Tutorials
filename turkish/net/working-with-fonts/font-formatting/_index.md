---
title: Yazı Tipi Biçimlendirme
linktitle: Yazı Tipi Biçimlendirme
second_title: Aspose.Words for .NET API Referansı
description: Bu öğreticide, bir Word belgesindeki yazı tipini Aspose.Words for .NET ile nasıl biçimlendireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/font-formatting/
---

Bu öğreticide, Aspose.Words for .NET kitaplığını kullanarak bir Word belgesinde yazı tipi biçimlendirmesinin nasıl yapıldığını size göstereceğiz. Yazı tipi biçimlendirmesi, boyut, kalın, renk, yazı tipi, altı çizili ve daha fazlası dahil olmak üzere metnin görünümünü özelleştirmenizi sağlar. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

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

## 2. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 Ardından, örnekleyerek yeni bir belge oluşturacağız.`Document` sınıfı ve bir belge oluşturucuyu örnekleyerek`DocumentBuilder` sınıf.

```csharp
// Yeni bir belge oluştur
Document doc = new Document();

// Bir belge oluşturucu oluşturun
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Yazı tipi biçimlendirmesini yapılandırın
 Şimdi erişeceğiz`Font` belge oluşturucunun nesnesini seçin ve boyut, kalın, renk, yazı tipi, altı çizili vb. gibi yazı tipi biçimlendirme özelliklerini yapılandırın.

```csharp
// Yazı tipine erişin
Font font = builder.Font;

// Yazı tipi biçimlendirmesini yapılandırın
font.Size = 16;
font. Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
```

## 4. Adım: Belgeye metin ekleyin
Ardından, belgeye biçimlendirilmiş metin eklemek için belge oluşturucuyu kullanacağız.

```csharp
// Belgeye metin ekleyin
builder.Write("Example text.");
```

## 5. Adım: Belgeyi kaydedin
Son olarak, yazı tipi biçimlendirmesini içeren belgeyi kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

### Aspose.Words for .NET kullanarak Font Biçimlendirme için örnek kaynak kodu 
```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
builder.Write("Sample text.");
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi biçimlendirmesinin nasıl yapıldığını gördük. Yazı tipi biçimlendirme, belgelerinizdeki metnin görünümünü özelleştirmenize olanak tanır. Çekici ve profesyonel belgeler oluşturmak için bu özelliği kullanmaktan çekinmeyin.