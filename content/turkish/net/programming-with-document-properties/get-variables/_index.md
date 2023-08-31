---
title: Değişkenleri Al
linktitle: Değişkenleri Al
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belge değişkenlerini almak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/get-variables/
---

Bu eğitimde, Aspose.Words for .NET ile bir belgeden değişkenleri almak için C# kaynak kodunu size anlatacağız. Bu özellik, bir belgede tanımlanan değişkenlere erişmenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda değişkenleri almak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Değişkenleri alma

Şimdi belgede tanımlanan değişkenleri alacağız. Aşağıdaki kodu kullanın:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Bu kod, belge değişkenlerindeki her anahtar/değer çifti üzerinde yinelenir ve her değişkenin adını ve değerini alır. Daha sonra değişkenler, her değişkene ilişkin bilgileri görüntülemek için birleştirilir.

### Aspose.Words for .NET kullanarak Değişkenleri Al için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeden değişkenleri nasıl alacağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu takip ederek değişkenlere kendi belgelerinizden kolayca erişebilir ve bunları görüntüleyebilirsiniz.