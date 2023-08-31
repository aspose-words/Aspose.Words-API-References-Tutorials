---
title: Word Belgesinde Tercih Edilen Kontrol Türü
linktitle: Word Belgesinde Tercih Edilen Kontrol Türü
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir HTML belgesi yüklerken word belgesinde tercih edilen kontrol tipini belirlemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlloadoptions/preferred-control-type/
---
Bu makale, tercih edilen kontrol türü özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına ilişkin adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir HTML belgesini yüklerken tercih edilen kontrol tipini nasıl belirleyeceğinizi anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: HTML kodunu tanımlayın

 Başlamak için belge olarak yüklemek istediğiniz HTML kodunu tanımlamanız gerekir. Bu örnekte, bir tanımladık.`html` Seçeneklere sahip bir seçicinin HTML kodunu içeren değişken.

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

 Daha sonra, bir`HtmlLoadOptions` nesneyi ayarlayın ve`PreferredControlType` mülkiyet`HtmlControlType.StructuredDocumentTag`. Bu, Aspose.Words'e yükleme sırasında HTML'yi temsil etmek için StructuredDocumentTag'leri kullanmasını söyler.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## 3. Adım: Belgeyi yükleyin ve kaydedin

 biz kullanıyoruz`Document` Daha önce tanımlanan yükleme seçenekleriyle HTML kodunu bir bellek akışından yüklemek için sınıf. Daha sonra belgeyi belirtilen dizine kaydediyoruz.`.docx`dosya formatı.

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

 Bu adım adım kılavuzu takip ederek, bir HTML belgesini yüklerken istenen kontrol tipini belirlemek için Aspose.Words for .NET'teki "Tercih Edilen Kontrol Tipi" özelliğini nasıl kullanacağınızı öğrendiniz. ayarlamak`PreferredControlType` mülkiyet`HtmlControlType.StructuredDocumentTag` Aspose.Words'ün HTML içeriğinin daha iyi temsili ve işlenmesi için StructuredDocumentTags'i (SDT) kullanmasına olanak tanır. Özel gereksinimlerinize uyacak şekilde diğer kontrol türlerini de keşfedebilirsiniz. Bu özelliğin kullanılması, Aspose.Words ile C# uygulamanızda HTML belgelerinin doğru ve verimli şekilde işlenmesini sağlamaya yardımcı olur.

### Word belgesinde tercih edilen kontrol türü için SSS'ler

#### S: Aspose.Words for .NET'teki "Tercih Edilen Kontrol Türü" özelliği nedir?

C: "Tercih Edilen Kontrol Türü" özelliği, bir HTML belgesini yüklerken HTML öğelerini temsil etmek için tercih edilen kontrol türünü belirtmenize olanak tanır. HTML içeriğinin daha iyi temsil edilmesi ve işlenmesi için uygun kontrol tipinin seçilmesine yardımcı olur.

#### S: Bir HTML belgesini yüklerken tercih edilen kontrol türünü nasıl ayarlarım?

 C: Tercih edilen kontrol türünü ayarlamak için bir`HtmlLoadOptions` nesneyi ve onu ayarlayın`PreferredControlType` istenilen mülk`HtmlControlType` . Verilen örnekte,`HtmlControlType.StructuredDocumentTag` kullanıldı.

#### S: Tercih edilen kontrol türü olarak StructuredDocumentTags (SDT) kullanmanın önemi nedir?

C: StructuredDocumentTag'ler (SDT), bir Word belgesindeki karmaşık içeriği ve kontrolleri temsil etmek için kullanılabilen XML tabanlı öğelerdir. SDT'leri tercih edilen kontrol türü olarak kullanmak, HTML içeriğinin daha iyi uyumluluğunu ve temsilini sağlayabilir.

#### S: Aspose.Words'ün HTML belgesini yüklerken tercih edilen kontrol tipini kullanmasını nasıl sağlayabilirim?

 C: Ayarlayarak`PreferredControlType` mülkiyet`HtmlControlType.StructuredDocumentTag`Örnek kaynak kodunda gösterildiği gibi Aspose.Words, belgeyi yüklerken HTML öğelerini temsil etmek için SDT'leri kullanacaktır.

#### S: Tercih edilen seçenek olarak diğer kontrol türlerini kullanabilir miyim?

 C: Evet, bunun dışında`HtmlControlType.StructuredDocumentTag` Aspose.Words for .NET aşağıdaki gibi diğer kontrol türlerini destekler:`HtmlControlType.ContentControl` Ve`HtmlControlType.CustomXmlMarkup`.