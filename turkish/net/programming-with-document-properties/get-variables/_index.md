---
title: Değişkenleri Al
linktitle: Değişkenleri Al
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile belge değişkenlerini almak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/get-variables/
---

Bu öğreticide, Aspose.Words for .NET ile bir belgeden değişkenleri almak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgede tanımlanan değişkenlere erişmenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, değişkenleri almak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
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

Bu kod, belge değişkenlerindeki her anahtar/değer çiftini yineler ve her değişkenin adını ve değerini alır. Değişkenler daha sonra her bir değişkenin bilgilerini görüntülemek için birleştirilir.

### Aspose.Words for .NET kullanarak Get Variables için örnek kaynak kodu

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

 bölümünde doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeden değişkenleri nasıl alacağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek değişkenlere kendi belgelerinizden kolayca erişebilir ve bunları görüntüleyebilirsiniz.