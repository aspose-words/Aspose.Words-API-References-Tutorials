---
title: Revizyonları Balonlarda Göster
linktitle: Revizyonları Balonlarda Göster
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile revizyonları balonlarda gösterin.
type: docs
weight: 10
url: /tr/net/working-with-revisions/show-revisions-in-balloons/
---

Bu adım adım kılavuzda, size Aspose.Words for .NET kullanarak bir Word belgesinde balonlardaki revizyonları nasıl göstereceğinizi göstereceğiz. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. Adım: İnceleme gösterme seçeneklerini yapılandırın

Revizyonları balonlarda görünür kılmak için göster seçeneklerini yapılandıracağız.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## 3. Adım: Belgeyi PDF biçiminde kaydedin

Son olarak, Balonlarda Gösterilen düzeltmelerle belgeyi PDF olarak kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown çıktı formatları

Çıktı, okunabilirliği artırmak için işaretlemede biçimlendirilebilir. Örneğin :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Aspose.Words for .NET kullanarak Revizyonları Balonlarda Göster için örnek kaynak kodu

Aspose.Words for .NET kullanan bir belgede balonlardaki revizyonları gösteren eksiksiz kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Render'lar revizyonları satır içine ekler, revizyonları balonlarda siler ve biçimlendirir.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Bir sayfanın sağ tarafında revizyon çubukları oluşturur.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki balonlardaki revizyonları nasıl görüntüleyeceğimizi öğrendik. Uygun görüntüleme seçeneklerini kullanarak, revizyonları sağ tarafta revizyon çubukları ile baloncuklarda görünür hale getirebildik. Aspose.Words for .NET, revizyon yönetimi de dahil olmak üzere Word belgelerini işlemek için birçok güçlü özellik sunar. Artık Aspose.Words for .NET'i kullanarak kendi Word belgelerinizdeki balonlardaki revizyonları göstermek için bu bilgiyi kullanabilirsiniz.


### SSS

#### S: Aspose.Words for .NET'te bir belge nasıl yüklenir?

 C: Şunu kullanın:`Document` bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirleyebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET ile revizyonları balonlarda nasıl gösterebilirim?

 C: Şunu kullanın:`ShowInBalloons` mülkiyeti`RevisionOptions` revizyonların balonlarda görüntülenmesini yapılandırmak için nesne. Bu özelliği şu şekilde ayarlayabilirsiniz:`ShowInBalloons.FormatAndDelete` revizyonları silme ve biçimlendirme revizyonları ile balonlarda göstermek için.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### S: Aspose.Words for .NET ile bir belgeyi PDF formatında nasıl kaydedebilirim?

 C: Şunu kullanın:`Save` yöntemi`Document` Belgeyi PDF biçiminde kaydetmek için nesne. ".pdf" uzantılı tam hedef yolu belirtmelisiniz.

```csharp
doc.Save("path/to/destination/document.pdf");
```