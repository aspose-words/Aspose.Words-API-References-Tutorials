---
title: Word Belgesinde Tercih Edilen Kontrol Türü
linktitle: Word Belgesinde Tercih Edilen Kontrol Türü
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir HTML belgesi yüklerken word belgesinde tercih edilen kontrol tipini belirlemek için adım adım kılavuz.
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

 biz kullanıyoruz`Document` Daha önce tanımlanan yükleme seçenekleriyle bir bellek akışından HTML kodu yüklemek için sınıf. Ardından, belgeyi belirtilen dizine kaydederiz.`.docx`dosya formatı.

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

## Çözüm

 Bu adım adım kılavuzu takip ederek, bir HTML belgesi yüklerken istenen kontrol tipini belirlemek için Aspose.Words for .NET'teki "Tercih Edilen Kontrol Tipi" özelliğini nasıl kullanacağınızı öğrendiniz. ayarlamak`PreferredControlType` mülkiyet`HtmlControlType.StructuredDocumentTag` Aspose.Words'ün HTML içeriğinin daha iyi temsili ve işlenmesi için StructuredDocumentTags (SDT) kullanmasına izin verir. Özel gereksinimlerinize uyacak şekilde diğer kontrol türlerini de keşfedebilirsiniz. Bu özelliği kullanmak, Aspose.Words ile C# uygulamanızda HTML belgelerinin doğru ve verimli bir şekilde işlenmesini sağlamaya yardımcı olur.

### Word belgesinde tercih edilen kontrol türü için SSS

#### S: Aspose.Words for .NET'teki "Tercih Edilen Kontrol Tipi" özelliği nedir?

C: "Tercih Edilen Kontrol Tipi" özelliği, bir HTML belgesi yüklerken HTML öğelerini temsil etmek için tercih edilen kontrol tipini belirlemenize olanak tanır. HTML içeriğinin daha iyi temsili ve işlenmesi için uygun kontrol tipinin seçilmesine yardımcı olur.

#### S: Bir HTML belgesi yüklerken tercih edilen kontrol türünü nasıl ayarlarım?

 C: Tercih edilen kontrol tipini ayarlamak için bir`HtmlLoadOptions` nesne ve ayarla`PreferredControlType` İstenilen özellik`HtmlControlType` . Verilen örnekte,`HtmlControlType.StructuredDocumentTag` kullanıldı.

#### S: Tercih edilen kontrol türü olarak StructuredDocumentTags (SDT) kullanmanın önemi nedir?

A: StructuredDocumentTags (SDT), bir Word belgesindeki karmaşık içeriği ve denetimleri temsil etmek için kullanılabilen XML tabanlı öğelerdir. SDT'leri tercih edilen kontrol türü olarak kullanmak, HTML içeriğinin daha iyi uyumluluğunu ve temsilini sağlayabilir.

#### S: Aspose.Words'ün HTML belgesini yüklerken tercih edilen kontrol tipini kullanmasını nasıl sağlayabilirim?

 A: ayarlayarak`PreferredControlType` mülkiyet`HtmlControlType.StructuredDocumentTag`örnek kaynak kodunda gösterildiği gibi Aspose.Words, belgeyi yüklerken HTML öğelerini temsil etmek için SDT'leri kullanacaktır.

#### S: Diğer kontrol türlerini tercih edilen seçenek olarak kullanabilir miyim?

 C: Evet, bunun dışında`HtmlControlType.StructuredDocumentTag` , Aspose.Words for .NET, aşağıdakiler gibi diğer kontrol türlerini destekler:`HtmlControlType.ContentControl` Ve`HtmlControlType.CustomXmlMarkup`.