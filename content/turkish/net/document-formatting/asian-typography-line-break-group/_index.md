---
title: Word Belgesinde Asya Tipografi Satır Sonu Grubu
linktitle: Word Belgesinde Asya Tipografi Satır Sonu Grubu
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile word belgesinde Asya Tipografisi satır sonu grubunu nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/asian-typography-line-break-group/
---
Bu eğitimde size Aspose.Words for .NET ile word belgesi özelliğinde Asya Tipografi satır sonu grubunun nasıl kullanılacağını göstereceğiz. Kaynak kodunu anlamak ve biçimlendirme değişikliklerini uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için belgelerinizin dizini belirtin ve Asya tipografisini içeren belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Adım 2: Asya Tipografi Kurulumu

Şimdi belgenin ilk paragrafı için Asya tipografi ayarlarını yapılandıracağız. İşte nasıl:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi kullanarak belgeyi istediğiniz konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Aspose.Words for .NET kullanan Asya Tipografi Satır Arası Grubu için örnek kaynak kodu

Aspose.Words for .NET ile Asya Tipografi Satır Arası Grubu özelliğinin tam kaynak kodu:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Bu kodla Aspose.Words for .NET'i kullanarak Asya Tipografisi satır sonu grubunu uygulayabileceksiniz.

## Çözüm

 Bu eğitimde Aspose.Words for .NET'teki "Asya Tipografi Satır Sonu Grubu" özelliğini inceledik. Yapılandırarak`FarEastLineBreakControl`, `WordWrap` , Ve`HangingPunctuation` özellikleri`ParagraphFormat`sayesinde, bir Word belgesinde Asya tipografisinin satır kırma davranışını kontrol edebildik. Bu özellik, Asya karakterlerini işlemek ve karışık dil içeriğine sahip belgelerde düzgün satır sonları ve sözcük kaydırma sağlamak için kullanışlıdır.

### SSS'ler

#### S: Aspose.Words for .NET'teki "Asya Tipografi Satır Sonu Grubu" özelliği nedir?

C: Aspose.Words for .NET'teki "Asya Tipografi Satır Sonu Grubu" özelliği, bir Word belgesinde Asya tipografisi için satır kesme davranışını kontrol etmenize olanak tanır. Özellikle paragraflarda Asya karakterleriyle uğraşırken satırların nasıl kesileceğini ve kaydırılacağını etkiler.

#### S: Aspose.Words for .NET'te "Asya Tipografi Satır Arası Grubu"nu nasıl etkinleştiririm?

 C: "Asya Tipografi Satır Sonu Grubu"nu etkinleştirmek için`FarEastLineBreakControl`, `WordWrap` , Ve`HangingPunctuation` özellikleri`ParagraphFormat` belgenizdeki ilgili paragraf(lar) için. Ayar`FarEastLineBreakControl` ile`false` Satır kesme konusunda Asya karakterlerinin Latin karakterlerine benzer şekilde ele alınmasını sağlar.`WordWrap` ayarlanır`true` Asya tipografisi için kelime kaydırmayı etkinleştirir ve`HangingPunctuation` ayarlanır`false` Asya metinlerinde noktalama işaretlerinin asılı kalmasını önler.

#### S: "Asya Tipografi Satır Sonu Grubu"nu bir belgedeki belirli paragraflara uygulayabilir miyim?

C: Evet, "Asya Tipografi Satır Sonu Grubu" ayarlarını bir Word belgesindeki belirli paragraflara uygulayabilirsiniz. Örnek kodda ayarlar belgenin ilk paragrafına uygulanmıştır. Gerektiğinde diğer paragrafları hedeflemek için kodu, bunlara aşağıdaki adresten erişerek ayarlayabilirsiniz:`Paragraphs` belgedeki ilgili bölüm(ler)in toplanması.