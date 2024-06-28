---
title: Arama Desenindeki Meta Karakterler
linktitle: Arama Desenindeki Meta Karakterler
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerini düzenlemek için arama modelinde meta karakterleri nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/meta-characters-in-search-pattern/
---
Bu makalede, Aspose.Words for .NET kütüphanesinde Arama Deseninde Meta Karakterler fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, Word belgelerinde gelişmiş aramalar ve değiştirmeler gerçekleştirmek için özel meta karakterler kullanmanıza olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## Adım 1: Yeni Bir Belge Oluşturma

 Arama modelinde meta karakterleri kullanmaya başlamadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgeye sahip olduğumuzda, bir kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde, şunu kullanıyoruz:`Writeln` Ve`Write` iki satır metin ekleme yöntemleri:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## 3. Adım: Metni bulun ve meta karakterlerle değiştirin

 Şimdi şunu kullanacağız:`Range.Replace` Özel meta karakterler içeren bir arama modelini kullanarak metni arama ve değiştirme işlevi. Örneğimizde "Bu satır 1&pBu satır 2" ifadesini "Bu satır değiştirildi" ile değiştiriyoruz.`&p` paragraf sonunu temsil eden meta karakter:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Adım 4: Belgeye sayfa sonu ekleme

 Başka bir meta karakterin kullanımını göstermek için belgeye bir sayfa sonu ekleyeceğiz.`InsertBreak` yöntemi ile`BreakType.PageBreak` parametreler. İlk önce imleci`DocumentBuilder` belgenin sonuna sayfa sonunu ve yeni bir metin satırını ekliyoruz:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## 5. Adım: Başka bir meta karakter bulun ve değiştirin

 Şimdi başka bir arama gerçekleştireceğiz ve şunu kullanarak değiştireceğiz:`&m` sayfa sonunu temsil eden meta karakter. "Bu 1. satır&mBu 2. satırdır" ifadesini "Sayfa sonu yeni metinle değiştirildi" ifadesiyle değiştiririz. :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Adım 6: Düzenlenen belgeyi kaydetme

Son olarak değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydederiz:`Save` yöntem:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Aspose.Words for .NET kullanan Arama Desenindeki Meta Karakterler için örnek kaynak kodu

Aspose.Words for .NET ile arama modelinde metakarakterlerin kullanımını gösteren tam örnek kaynak kodunu burada bulabilirsiniz:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Çözüm

Bu makalede, Aspose.Words for .NET arama modelinde meta karakterlerin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, özel meta karakterler kullanarak arama yapmak ve değiştirmek, sayfa sonları eklemek ve düzenlenen belgeyi kaydetmek için adım adım bir kılavuz izledik.

### SSS'ler

#### S: Aspose.Words for .NET'teki Arama Desenindeki Meta Karakterler özelliği nedir?

C: Aspose.Words for .NET'teki Arama Şeklindeki Meta Karakterler özelliği, Word belgelerinde gelişmiş aramalar ve değiştirmeler gerçekleştirmek için özel meta karakterler kullanmanıza olanak tanır. Bu meta karakterler, arama düzeninizde paragraf sonlarını, bölüm sonlarını, sayfa sonlarını ve diğer özel öğeleri temsil etmenize olanak tanır.

#### S: Aspose.Words for .NET'te yeni bir belge nasıl oluşturulur?

 C: Arama şablonunda meta karakterleri kullanmadan önce Aspose.Words for .NET'i kullanarak yeni bir belge oluşturmalısınız. Bu, bir örneği başlatarak yapılabilir.`Document` nesne. Yeni bir belge oluşturmak için örnek kod aşağıda verilmiştir:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgeye nasıl metin eklenir?

 C: Bir belgeye sahip olduğunuzda, bir metin ekleyebilirsiniz.`DocumentBuilder` nesne. Örneğimizde, şunu kullanıyoruz:`Writeln` Ve`Write` iki satır metin ekleme yöntemleri:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### S: Aspose.Words for .NET kullanarak bir belgede meta karakterler içeren metin nasıl aranır ve değiştirilir?

 C: Metni meta karakterlerle aramak ve değiştirmek için`Range.Replace` yöntem. Örneğimizde "Bu satır 1&pBu satır 2" ifadesini "Bu satır değiştirildi" ile değiştiriyoruz.`&p` paragraf sonunu temsil eden meta karakter:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### S: Aspose.Words for .NET kullanarak bir belgeye sayfa sonu nasıl eklenir?

C: Başka bir meta karakterin kullanımını göstermek için belgeye bir sayfa sonu ekleyeceğiz.`InsertBreak` yöntemi ile`BreakType.PageBreak` parametreler. İlk önce imleci`DocumentBuilder` belgenin sonuna sayfa sonunu ve yeni bir metin satırını ekliyoruz:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### S: Aspose.Words for .NET kullanılarak bir belgede nasıl arama yapılır ve başka bir meta karakterle değiştirilir?

 C: Şimdi başka bir arama gerçekleştireceğiz ve şunu kullanarak değiştireceğiz:`&m` sayfa sonunu temsil eden meta karakter. "Bu 1. satır&mBu 2. satırdır" ifadesini "Sayfa sonu yeni metinle değiştirildi" ifadesiyle değiştiririz. :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### S: Düzenlenen belge Aspose.Words for .NET'te nasıl kaydedilir?

 C: Belgede değişiklik yaptıktan sonra, onu kullanarak belirtilen dizine kaydedebilirsiniz.`Save` yöntem:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```