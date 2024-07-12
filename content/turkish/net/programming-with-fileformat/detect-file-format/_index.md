---
title: Belge Dosya Formatını Algıla
linktitle: Belge Dosya Formatını Algıla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belge dosya formatını algılamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-fileformat/detect-file-format/
---

Bu makale, belge dosyası formatı algılama özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına ilişkin adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda farklı belge dosyalarının formatının nasıl tespit edileceğini anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Dizinleri tanımlayın

 Başlamak için, dosyaları formatlarına göre saklamak istediğiniz dizinleri tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`Belgeler dizininizin gerçek yolu ile. Henüz mevcut değilse "Desteklenen", "Bilinmeyen", "Şifrelenmiş" ve "Pre97" dizinlerini oluşturuyoruz.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Henüz mevcut değilse dizinleri oluşturun.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## 2. Adım: Dosyalara Göz Atın

 Daha sonra şunu kullanırız:`GetFiles` yöntemi`Directory` Belirtilen dizindeki dosyaların listesini almak için sınıf. Ayrıca bir tane kullanıyoruz`Where` "Bozuk belge.docx" adlı belirli bir dosyayı hariç tutmak için yan tümce.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## 3. Adım: Her dosyanın formatını tespit edin

 Listedeki her dosyanın üzerinden geçiyoruz ve`DetectFileFormat` yöntemi`FileFormatUtil` Dosyanın biçimini algılamak için sınıf. Ayrıca tespit edilen belge türünü de görüntüleriz.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Belge türünü görüntüle
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... Desteklenen diğer belge biçimleri için vakalar ekleyin
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

Bu kadar ! Aspose.Words for .NET'i kullanarak farklı belge dosyalarının formatını başarıyla tespit ettiniz.

### Aspose.Words for .NET ile dosya formatı tespiti için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Henüz mevcut değilse dizinleri oluşturun.
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// Belge türünü görüntüle
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### Belge dosyası formatı tespiti için SSS

#### Aspose.Words for .NET kullanılarak bir belge dosyasının formatı nasıl tespit edilir?

 Aspose.Words for .NET kullanarak bir belge dosyasının formatını tespit etmek için eğitimde verilen adımları takip edebilirsiniz. Kullanmak`DetectFileFormat` yöntemi`FileFormatUtil` class belge dosyasının formatını tespit etmenize izin verecektir. Bu, bunun bir Microsoft Word 97-2003 belgesi mi, bir şablon mu, bir Office Açık XML WordprocessingML belgesi mi yoksa desteklenen diğer formatlar mı olduğunu belirlemenize olanak tanır. Eğitimde sağlanan kod, bu özelliğin uygulanmasında size yol gösterecektir.

#### Aspose.Words for .NET hangi belge formatlarını destekliyor?

Aspose.Words for .NET, Microsoft Word 97-2003 belgeleri (DOC), Şablonlar (DOT), Office Açık XML Kelime İşlemeML belgeleri (DOCX), Makrolu Office Açık XML Kelime İşlemeML belgeleri (DOCM), Office Open dahil olmak üzere çeşitli belge formatlarını destekler XML Kelime İşlemeMakro içermeyen ML şablonları (DOTX), Makrolu Office Açık XML Kelime İşlemeML şablonları (DOTM), Düz OPC belgeleri, RTF belgeleri, Microsoft Word 2003 Kelime İşlemeML belgeleri, HTML belgeleri, MHTML (Web arşivi) belgeleri, OpenDocument Metni (ODT) belgeleri, OpenDocument Metni (OTT) şablonları, MS Word 6 veya Word 95 belgeleri ve bilinmeyen belge biçimleri.

#### Biçim algılama sırasında şifrelenmiş belge dosyaları nasıl işlenir?

 Bir belge dosyasının formatını tespit ederken,`IsEncrypted` mülkiyeti`FileFormatInfo` Dosyanın şifrelenip şifrelenmediğini kontrol etmek için nesne. Dosya şifrelenmişse, bu özel durumu ele almak için dosyayı şifrelenmiş belgelere ayrılmış bir dizine kopyalamak gibi ek adımlar uygulayabilirsiniz. Şunu kullanabilirsiniz:`File.Copy` bunu yapmanın yöntemi.

#### Bir belgenin formatı bilinmediğinde ne gibi işlemler yapılmalıdır?

Bir belgenin formatı bilinmiyorsa, onu uygulamanıza özel bir şekilde ele almaya karar verebilirsiniz. Eğitimde verilen örnekte belge, bilinmeyen formattaki belgelere ayrılmış belirli bir dizine kopyalanır. Bu eylemi özel ihtiyaçlarınıza uyacak şekilde özelleştirebilirsiniz.

#### Aspose.Words for .NET'in belge formatı algılamayla birlikte kullanılabilecek başka özellikleri var mı?

Evet, Aspose.Words for .NET, Word belgelerinin işlenmesi ve işlenmesi için birçok başka özellik sunar. Örneğin, belgelerden metin, görüntü veya meta veriler çıkarmak, biçimlendirme değişiklikleri uygulamak, belgeleri birleştirmek, belgeleri farklı biçimlere dönüştürmek ve daha fazlası için kitaplığı kullanabilirsiniz.