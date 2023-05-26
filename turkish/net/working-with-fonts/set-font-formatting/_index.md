---
title: Yazı Tipi Formatını Ayarla
linktitle: Yazı Tipi Formatını Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgesinde yazı tipi biçimlendirmesini nasıl ayarlayacağınızı öğrenin ve çekici belgeler oluşturun.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-font-formatting/
---
Bu öğreticide, size Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi biçimlendirmesini nasıl ayarlayacağınızı göstereceğiz. Kalın, renkli, italik, yazı tipi, boyut, boşluk ve altı çizili gibi stilleri nasıl uygulayacağınızı öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Belge dizinini tanımlayın
Dizin yolunu Word belgenizin konumuna ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi oluşturun ve biçimlendirin
 örneğini oluşturun`Document` sınıf ve`DocumentBuilder` belgeyi oluşturmak için sınıf. Kullan`Font` mülkiyeti`DocumentBuilder` yazı tipi biçimlendirme özelliklerine erişmek için.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## 3. Adım: Belgeyi kaydedin
 Kullan`Save` yazı tipi biçimlendirmesi uygulanmış olarak belgeyi kaydetme yöntemi. Yer değiştirmek`"WorkingWithFonts.SetFontFormatting.docx"` İstenen dosya adıyla.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### Aspose.Words for .NET kullanarak Yazı Tipi Biçimlendirmesini Ayarlamak için örnek kaynak kodu 
```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## Çözüm
Tebrikler! Artık Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi biçimlendirmesini nasıl ayarlayacağınızı biliyorsunuz. Daha fazla yazı tipi biçimlendirme seçeneği keşfedebilir ve kişiselleştirilmiş ve çekici Word belgeleri oluşturabilirsiniz.
