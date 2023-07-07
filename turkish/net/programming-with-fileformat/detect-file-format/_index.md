---
title: Belge Dosya Biçimini Algıla
linktitle: Belge Dosya Biçimini Algıla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belge dosyası biçimini algılamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-fileformat/detect-file-format/
---

Bu makale, belge dosyası biçimi algılama özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, farklı belge dosyalarının biçimini nasıl tespit edeceğinizi anlayabileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Dizinleri tanımlayın

 Başlamak için, dosyaları formatlarına göre depolamak istediğiniz dizinleri tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler dizininize giden gerçek yolla. "Supported", "Unknown", "Encrypted" ve "Pre97" dizinleri mevcut değilse oluşturuyoruz.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Zaten yoksa dizinleri oluşturun.
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

 Sonra kullanırız`GetFiles` yöntemi`Directory` belirtilen dizindeki dosyaların listesini almak için sınıf. Ayrıca bir`Where` yan tümcesi "Bozuk belge.docx" adlı belirli bir dosyayı hariç tutmak için.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## 3. Adım: Her dosyanın biçimini algılayın

 Listedeki her dosya arasında dolaşıyoruz ve`DetectFileFormat` yöntemi`FileFormatUtil` dosyanın biçimini algılamak için sınıf. Ayrıca algılanan belge türünü de görüntüleriz.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Belge türünü göster
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
// ... Desteklenen diğer belge biçimleri için servis talepleri ekleyin
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

### Aspose.Words for .NET ile dosya biçimi tespiti için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Zaten yoksa dizinleri oluşturun.
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

		// Belge türünü göster
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

#### Aspose.Words for .NET kullanılarak bir belge dosyasının formatı nasıl belirlenir?

 Aspose.Words for .NET kullanarak bir belge dosyasının formatını algılamak için eğitimde verilen adımları takip edebilirsiniz. Kullanmak`DetectFileFormat` yöntemi`FileFormatUtil` class, belge dosyasının biçimini algılamanıza izin verecektir. Bu, Microsoft Word 97-2003 belgesi mi, şablon mu, Office Açık XML WordprocessingML belgesi mi yoksa desteklenen diğer biçimler mi olduğunu belirlemenize olanak tanır. Öğreticide sağlanan kod, bu özelliği uygularken size yol gösterecektir.

#### Aspose.Words for .NET hangi belge formatlarını destekliyor?

Aspose.Words for .NET, Microsoft Word 97-2003 belgeleri (DOC), Şablonlar (DOT), Office Open XML WordprocessingML belgeleri (DOCX), Office Open XML WordprocessingML belgeleri (DOCM), Office Open gibi çeşitli belge biçimlerini destekler. Makrosuz XML WordprocessingML şablonları (DOTX), Makrolu Office Open XML WordprocessingML şablonları (DOTM), Flat OPC belgeleri, RTF belgeleri, Microsoft Word 2003 WordprocessingML belgeleri, HTML belgeleri, MHTML (Web arşivi) belgeleri, OpenDocument Text (ODT) belgeleri, OpenDocument Metin (OTT) şablonları, MS Word 6 veya Word 95 belgeleri ve bilinmeyen belge biçimleri.

#### Biçim tespiti sırasında şifrelenmiş belge dosyaları nasıl işlenir?

 Bir belge dosyasının biçimini algılarken,`IsEncrypted` mülkiyeti`FileFormatInfo` dosyanın şifrelenip şifrelenmediğini kontrol etmek için nesne. Dosya şifrelenmişse, bu özel durumla başa çıkmak için dosyayı şifrelenmiş belgelere ayrılmış bir dizine kopyalamak gibi ek adımlar atabilirsiniz. kullanabilirsiniz`File.Copy` bunu yapmak için yöntem.

#### Bir belgenin formatı bilinmediğinde hangi işlemler yapılmalıdır?

Bir belgenin biçimi bilinmediğinde, onu uygulamanıza özel bir şekilde işlemeye karar verebilirsiniz. Öğreticide verilen örnekte, belge, biçimi bilinmeyen belgelere ayrılmış belirli bir dizine kopyalanmıştır. Bu eylemi özel ihtiyaçlarınıza uyacak şekilde özelleştirebilirsiniz.

#### Aspose.Words for .NET'in belge formatı tespiti ile birlikte kullanılabilecek başka özellikleri var mı?

Evet, Aspose.Words for .NET, Word belgelerini işlemek ve değiştirmek için birçok başka özellik sunar. Örneğin, belgelerden metin, resim veya meta veri ayıklamak, biçimlendirme değişiklikleri uygulamak, belgeleri birleştirmek, belgeleri farklı biçimlere dönüştürmek ve daha fazlası için kitaplığı kullanabilirsiniz.