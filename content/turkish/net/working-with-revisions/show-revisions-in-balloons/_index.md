---
title: Düzeltmeleri Balonlarda Göster
linktitle: Düzeltmeleri Balonlarda Göster
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile revizyonları balonlarda gösterin.
type: docs
weight: 10
url: /tr/net/working-with-revisions/show-revisions-in-balloons/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki balonlardaki revizyonların nasıl gösterileceğini size göstereceğiz. Size kaynak kodunun tamamını sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. Adım: İnceleme gösterisi seçeneklerini yapılandırın

Gösteri seçeneklerini, revizyonların balonlarda görünür olmasını sağlayacak şekilde yapılandıracağız.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## 3. Adım: Belgeyi PDF formatında kaydedin

Son olarak, belgeyi balonlarla gösterilen düzeltmelerle birlikte PDF olarak kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown çıktı formatları

Çıktı, okunabilirliği artırmak için işaretleme biçiminde biçimlendirilebilir. Örneğin :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Aspose.Words for .NET kullanarak Revizyonları Balonlarda Göster için örnek kaynak kodu

Aspose.Words for .NET kullanan bir belgedeki balonlardaki revizyonları gösteren kaynak kodun tamamı burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Revizyonları satır içi olarak ekler, revizyonları balonlara siler ve biçimlendirir.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Revizyon çubuklarını sayfanın sağ tarafında oluşturur.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki balonlardaki revizyonların nasıl görüntüleneceğini öğrendik. Uygun görüntüleme seçeneklerini kullanarak, sağ tarafta revizyon çubukları bulunan baloncuklar halinde revizyonları görünür hale getirmeyi başardık. Aspose.Words for .NET, revizyon yönetimi de dahil olmak üzere Word belgelerinin işlenmesi için birçok güçlü özellik sunar. Artık bu bilgiyi Aspose.Words for .NET kullanarak kendi Word belgelerinizdeki balonlardaki revizyonları göstermek için kullanabilirsiniz.


### SSS'ler

#### S: Aspose.Words for .NET'e belge nasıl yüklenir?

 C: Kullan`Document` Bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirtebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET ile balonlardaki revizyonlar nasıl görüntülenir?

 C: Kullan`ShowInBalloons` mülkiyeti`RevisionOptions` Balonlardaki revizyonların görünümünü yapılandırmak için nesne. Bu özelliği şu şekilde ayarlayabilirsiniz:`ShowInBalloons.FormatAndDelete` balonlardaki revizyonları silme ve biçimlendirme revizyonlarıyla göstermek için.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### S: Aspose.Words for .NET ile bir belge PDF formatında nasıl kaydedilir?

 C: Kullan`Save` yöntemi`Document` Belgeyi PDF formatında kaydetmek için nesne. Tam hedef yolunu ".pdf" uzantısıyla belirtmeniz gerekir.

```csharp
doc.Save("path/to/destination/document.pdf");
```