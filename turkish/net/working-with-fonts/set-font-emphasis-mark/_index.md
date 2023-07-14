---
title: Yazı Tipi Vurgu İşaretini Ayarla
linktitle: Yazı Tipi Vurgu İşaretini Ayarla
second_title: Aspose.Words Belge İşleme API'sı
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
 örneğini oluşturun`Document` sınıf ve ilgili`DocumentBuilder` belge içeriğini oluşturmak için. Kullan`Font.EmphasisMark` yazı tipi vurgu stilini ayarlamak için özellik`EmphasisMark.UnderSolidCircle` . Daha sonra`Write` Ve`Writeln` yöntemleri`DocumentBuilder` belirtilen yazı tipi vurgusuyla metin eklemek için.

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
//Belge dizininizin yolu
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

### SSS

#### S: Aspose.Words kullanarak bir Word belgesindeki belirli bir yazı tipine nasıl aksan işaretleri ekleyebilirim?

C: Aspose.Words kullanarak bir Word belgesindeki belirli bir yazı tipine vurgu işaretleri eklemek için, istenen yazı tipine gitmek ve uygun vurgu işaretlerini uygulamak için API'yi kullanabilirsiniz. Bu, seçilen yazı tipiyle metne vurgu işaretleri ekleyecektir.

#### S: Bir Word belgesindeki vurgu işaretlerinin stilini Aspose.Words ile değiştirmek mümkün mü?

C: Evet, Aspose.Words ile bir Word belgesindeki vurgu işaretlerinin stilini değiştirebilirsiniz. API, vurgu işaretlerinin görünümünü özelleştirmek için renk, boyut, çizgi tipi vb. gibi stil özelliklerini ayarlamanıza olanak tanır.

#### S: Aspose.Words kullanarak bir Word belgesindeki tüm aksan işaretlerini nasıl kaldırabilirim?

C: Aspose.Words kullanarak bir Word belgesindeki tüm aksan işaretlerini kaldırmak için, API'yi kullanarak belgeye göz atabilir, mevcut aksan işaretlerini tespit edebilir ve uygun yöntemleri kullanarak bunları kaldırabilirsiniz. Bu, belgedeki tüm vurgu işaretlerini kaldıracaktır.

#### S: Bir Word belgesindeki metnin belirli bir bölümüne vurgu işaretleri ekleyebilir miyim?

C: Evet, Aspose.Words kullanarak bir Word belgesindeki metnin belirli bir bölümüne vurgu işaretleri ekleyebilirsiniz. API'yi kullanarak istediğiniz metin aralığını seçebilir ve metnin o kısmına uygun vurgu işaretleri ekleyebilirsiniz.

#### S: Vurgu işaretleri ihtiyaçlarıma göre özelleştirilebilir mi?

C: Evet, aksan işaretleri Aspose.Words kullanılarak ihtiyaçlarınıza göre özelleştirilebilir. Biçimlendirme tercihlerinize uyması için vurgu işaretlerinin renk, boyut, çizgi tipi ve daha fazlası gibi stil özelliklerini ayarlayabilirsiniz.