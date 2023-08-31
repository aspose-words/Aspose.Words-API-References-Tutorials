---
title: Yazı Tipi Vurgu İşaretini Ayarla
linktitle: Yazı Tipi Vurgu İşaretini Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi vurgu stilini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-font-emphasis-mark/
---

Bu eğitimde size Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi vurgu stilini nasıl ayarlayacağınızı göstereceğiz. Yazı tipi vurgusu, metindeki belirli kelimeleri veya cümleleri vurgulamak için kullanılır.

## Önkoşullar
Başlamadan önce aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- .NET için Aspose.Words kütüphanesi projenizde yüklü

## 1. Adım: Belge dizinini tanımlayın
 Dizin yolunu Word belgenizin konumuna ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi oluşturun ve özelleştirin
 Bir örneğini oluşturun`Document` sınıf ve ilişkili`DocumentBuilder` belge içeriğini oluşturmak için. Kullan`Font.EmphasisMark` yazı tipi vurgu stilini ayarlama özelliği`EmphasisMark.UnderSolidCircle` . Daha sonra şunu kullanın:`Write` Ve`Writeln` yöntemleri`DocumentBuilder` Belirtilen yazı tipi vurgusuna sahip metin eklemek için.

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
 kullanarak belgeyi kaydedin.`Save` yöntemi`Document` uygun yol ve dosya adı ile.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Aspose.Words for .NET kullanarak Yazı Tipi Vurgu İşaretini Ayarlama için örnek kaynak kodu 

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
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi vurgu stilini nasıl ayarlayacağınızı öğrendiniz. Farklı vurgu stillerini deneyin ve belgelerinizdeki kelimeleri veya cümleleri vurgulamak için bu özelliği kullanın.

### SSS'ler

#### S: Aspose.Words'ü kullanarak bir Word belgesindeki belirli bir yazı tipine nasıl vurgu işaretleri ekleyebilirim?

C: Aspose.Words'ü kullanarak bir Word belgesindeki belirli bir yazı tipine vurgu işaretleri eklemek için, istediğiniz yazı tipine gitmek ve uygun vurgu işaretlerini uygulamak için API'yi kullanabilirsiniz. Bu, seçilen yazı tipiyle metne vurgu işaretleri ekleyecektir.

#### S: Bir Word belgesindeki vurgu işaretlerinin stilini Aspose.Words ile değiştirmek mümkün müdür?

C: Evet, Aspose.Words ile Word belgesindeki aksan işaretlerinin stilini değiştirebilirsiniz. API, vurgu işaretlerinin görünümünü özelleştirmek için renk, boyut, çizgi türü vb. stil özelliklerini ayarlamanıza olanak tanır.

#### S: Aspose.Words'ü kullanarak bir Word belgesindeki tüm aksan işaretlerini nasıl kaldırabilirim?

C: Aspose.Words kullanarak bir Word belgesindeki tüm aksan işaretlerini kaldırmak için, API'yi kullanarak belgeye göz atabilir, mevcut aksan işaretlerini tespit edebilir ve uygun yöntemleri kullanarak bunları kaldırabilirsiniz. Bu, belgedeki tüm vurgu işaretlerini kaldıracaktır.

#### S: Word belgesindeki metnin belirli bir bölümüne vurgu işaretleri ekleyebilir miyim?

C: Evet, Aspose.Words'ü kullanarak Word belgesindeki metnin belirli bir bölümüne vurgu işaretleri ekleyebilirsiniz. API'yi kullanarak istediğiniz metin aralığını seçebilir ve metnin o kısmına uygun vurgu işaretlerini ekleyebilirsiniz.

#### S: Vurgu işaretleri ihtiyaçlarıma göre özelleştirilebilir mi?

C: Evet, Aspose.Words kullanılarak aksan işaretleri ihtiyaçlarınıza göre özelleştirilebilir. Vurgu işaretlerinin renk, boyut, çizgi türü ve daha fazlası gibi stil özelliklerini biçimlendirme tercihlerinize uyacak şekilde ayarlayabilirsiniz.