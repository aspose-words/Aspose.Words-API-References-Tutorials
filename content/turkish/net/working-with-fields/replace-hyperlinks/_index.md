---
title: Köprüleri Değiştir
linktitle: Köprüleri Değiştir
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgelerindeki köprüleri değiştirin. Köprüleri değiştirmek için adım adım talimatlar.
type: docs
weight: 10
url: /tr/net/working-with-fields/replace-hyperlinks/
---

Burada, Aspose.Words for .NET işlevselliğini kullanarak köprüleri değiştirmek için aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. Bu kodu kullanmadan önce projenize Aspose.Words kütüphanesini eklediğinizden emin olun.

## 1. Adım: Belge dizini yolunu ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Belgeler dizininize giden ve aşağıdakileri içeren doğru yolu belirttiğinizden emin olun:`Hyperlinks.docx` dosya.

## Adım 2: Köprüleri içeren belgeyi yükleyin

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Burada bir örneğini oluşturuyoruz.`Document` belirtilen dosyadan sınıf.

## 3. Adım: Köprüleri bulmak için alanlara göz atın

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Bazı köprü bağlantılar yerel olabilir (belge içindeki yer imlerine bağlantılar), bunları göz ardı ederiz.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Bu döngü, belgedeki tüm alanlardan geçerek tür alanlarını arar`FieldType.FieldHyperlink` . Bu türde bir alan bulunduğunda, bunun yerel bir bağlantı olup olmadığını kontrol ederiz.`SubAddress` mülk. Değilse, bağlantı adresini şununla değiştiririz:`"http://www.aspose.com"` ve sonuç`"Aspose - The .NET & Java Component Editor"`.

## 4. Adım: Değiştirilen belgeyi kaydedin

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Son olarak, değiştirilen belgeyi değiştirilen köprülerle birlikte belirtilen bir dosyaya kaydederiz.

### Köprüleri Aspose.Words for .NET ile değiştirmek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Bazı köprü bağlantılar yerel olabilir (belge içindeki yer imlerine bağlantılar), bunları göz ardı ederiz.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Bu, Aspose.Words for .NET kullanarak bir belgedeki köprüleri değiştirmek için kullanılan örnek kaynak kodudur.

### SSS'ler

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki köprüleri nasıl değiştirebilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesindeki köprüleri değiştirmek için şu komutu kullanabilirsiniz:`Document.Range.Replace`Aranacak metni ve değiştirilecek metni belirten yöntem. Arama ve değiştirme parametrelerini ayarlamak için uygun seçenekleri kullandığınızdan emin olun.

#### S: Bir Word belgesindeki yalnızca belirli köprüleri Aspose.Words for .NET ile değiştirmek mümkün müdür?

C: Evet, Aspose.Words for .NET ile bir Word belgesindeki yalnızca belirli köprüleri değiştirmek mümkündür. Değiştirilecek köprüleri, bağlantı URL'si, bağlantı metni veya diğer ilgili özellikler gibi belirli kriterleri kullanarak filtreleyebilirsiniz. Daha sonra değiştirme işlemini yalnızca eşleşen köprülere uygulayabilirsiniz.

#### S: Aspose.Words for .NET ile değiştirirken üstbilgi, altbilgi veya dipnotlardaki köprüleri nasıl yok sayabilirim?

C: Aspose.Words for .NET ile değiştirirken üstbilgi, altbilgi veya dipnotlardaki köprüleri yok saymak için gelişmiş arama seçeneklerini kullanabilir ve uygun arama sınırlarını belirleyebilirsiniz. Örneğin, aramayı belgenin ana bölümleriyle sınırlayabilir ve üstbilgileri, altbilgileri veya dipnotları hariç tutabilirsiniz.

#### S: Köprü bağlantılarını belgenin diğer bölümlerine giden dahili bağlantılarla değiştirmek mümkün müdür?

 C: Evet, Aspose.Words for .NET ile köprü bağlantılarını belgenin diğer bölümlerine giden dahili bağlantılarla değiştirmek mümkündür. Dahili bağlantılar oluşturmak için çapaları veya metin kimliklerini kullanabilir ve ardından bunları kullanarak değiştirebilirsiniz.`Document.Range.Replace` Uygun seçeneklerle yöntem.

#### S: Köprüleri Aspose.Words for .NET ile değiştirmek renkler veya stiller gibi bağlantı özelliklerini korur mu?

C: Evet, köprüleri Aspose.Words for .NET ile değiştirirken renkler veya stiller gibi bağlantı özellikleri korunur. Tutarlı bir sonuç elde etmek için değiştirilen metinde aynı biçimlendirme özelliklerini belirtebilirsiniz.