---
title: Yazı Tipi Vurgu İşaretini Ayarla
linktitle: Yazı Tipi Vurgu İşaretini Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi vurgu stilini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-font-emphasis-mark/
---

Bu öğreticide, size Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi vurgu stilini nasıl ayarlayacağınızı göstereceğiz. Yazı tipi vurgusu, metindeki belirli kelimeleri veya tümceleri vurgulamak için kullanılır.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Belge dizinini tanımlayın
Dizin yolunu Word belgenizin konumuna ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi oluşturun ve özelleştirin
 örneğini oluşturun`Document` sınıf ve ilgili`DocumentBuilder` belge içeriğini oluşturmak için. Kullan`Font.EmphasisMark`yazı tipi vurgu stilini ayarlamak için özellik`EmphasisMark.UnderSolidCircle` . Daha sonra`Write` Ve`Writeln` yöntemleri`DocumentBuilder` belirtilen yazı tipi vurgusuyla metin eklemek için.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## 3. Adım: Belgeyi kaydedin
 kullanarak belgeyi kaydedin.`Save` yöntemi`Document` uygun yol ve dosya adıyla.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Aspose.Words for .NET kullanan Set Font Vurgu İşareti için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi vurgu stilini nasıl ayarlayacağınızı öğrendiniz. Farklı vurgu stilleriyle denemeler yapın ve bu özelliği belgelerinizdeki sözcükleri veya tümceleri vurgulamak için kullanın.
