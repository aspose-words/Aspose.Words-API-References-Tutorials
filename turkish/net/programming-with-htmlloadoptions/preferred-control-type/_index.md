---
title: Tercih Edilen Kontrol Tipi
linktitle: Tercih Edilen Kontrol Tipi
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir HTML belgesi yüklerken tercih edilen kontrol tipini belirlemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlloadoptions/preferred-control-type/
---

Bu makale, tercih edilen kontrol tipi özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir HTML belgesi yüklerken tercih edilen kontrol tipini nasıl belirleyeceğinizi öğrenebileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: HTML kodunu tanımlayın

 Başlamak için, bir belge olarak yüklemek istediğiniz HTML kodunu tanımlamanız gerekir. Bu örnekte, bir`html` seçenekleri olan bir seçicinin HTML kodunu içeren değişken.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## 2. Adım: HTML yükleme seçeneklerini ayarlayın

 Sonra, bir`HtmlLoadOptions` nesne ve ayarlayın`PreferredControlType` mülkiyet`HtmlControlType.StructuredDocumentTag`. Bu, Aspose.Words'e yükleme sırasında HTML'yi temsil etmesi için StructuredDocumentTags'i kullanmasını söyler.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## 3. Adım: Belgeyi yükleyin ve kaydedin

 biz kullanıyoruz`Document` Daha önce tanımlanan yükleme seçenekleriyle bir bellek akışından HTML kodu yüklemek için sınıf. Ardından, belgeyi belirtilen dizine kaydederiz.`.docx` dosya formatı.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Aspose.Words for .NET ile tercih edilen kontrol tipi için örnek kaynak kodu

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Bu kadar ! Aspose.Words for .NET ile bir HTML belgesi yüklerken tercih edilen kontrol tipini başarıyla belirlediniz.