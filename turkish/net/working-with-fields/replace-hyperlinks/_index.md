---
title: Köprüleri Değiştir
linktitle: Köprüleri Değiştir
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerindeki köprüleri değiştirin. Köprüleri değiştirmek için adım adım talimatlar.
type: docs
weight: 10
url: /tr/net/working-with-fields/replace-hyperlinks/
---

Aspose.Words for .NET işlevselliğini kullanarak köprüleri değiştirmek için aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz. Bu kodu kullanmadan önce Aspose.Words kütüphanesini projenize dahil ettiğinizden emin olun.

## 1. Adım: Belge dizini yolunu ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 içeren belgeler dizininizin doğru yolunu belirttiğinizden emin olun.`Hyperlinks.docx` dosya.

## 2. Adım: Köprüleri içeren belgeyi yükleyin

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Burada bir örneğini oluşturuyoruz`Document` belirtilen dosyadan sınıf.

## 3. Adım: Köprüleri bulmak için alanlara göz atın

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Bazı köprüler yerel olabilir (belge içindeki yer imlerine bağlantılar), onları yok sayarız.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Bu döngü, tür alanlarını arayan belgedeki tüm alanlardan geçer.`FieldType.FieldHyperlink` . Bu tür bir alan bulunduğunda, yerel bir bağlantı olup olmadığını kontrol ederek kontrol ederiz.`SubAddress` mülk. Değilse, bağlantı adresini şu şekilde değiştiririz:`"http://www.aspose.com"` ve ile sonuç`"Aspose - The .NET & Java Component Editor"`.

## 4. Adım: Değiştirilen belgeyi kaydedin

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Son olarak, değiştirilen belgeyi değiştirilen köprülerle birlikte belirtilen bir dosyaya kaydederiz.

### Aspose.Words for .NET ile köprüleri değiştirmek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Bazı köprüler yerel olabilir (belge içindeki yer imlerine bağlantılar), onları yok sayarız.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Bu, Aspose.Words for .NET kullanan bir belgedeki köprüleri değiştirmek için örnek kaynak kodudur.

### SSS

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki köprüleri nasıl değiştirebilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesindeki köprüleri değiştirmek için`Document.Range.Replace`aranacak metni ve değiştirilecek metni belirten yöntem. Arama ve değiştirme parametrelerini ayarlamak için uygun seçenekleri kullandığınızdan emin olun.

#### S: Aspose.Words for .NET ile bir Word belgesindeki yalnızca belirli köprüleri değiştirmek mümkün mü?

C: Evet, bir Word belgesindeki yalnızca belirli köprüleri Aspose.Words for .NET ile değiştirmek mümkündür. Bağlantı URL'si, bağlantı metni veya diğer ilgili özellikler gibi belirli ölçütleri kullanarak değiştirilecek köprüleri filtreleyebilirsiniz. Ardından, değiştirmeyi yalnızca eşleşen köprülere uygulayabilirsiniz.

#### S: Aspose.Words for .NET ile değiştirirken üstbilgiler, altbilgiler veya dipnotlardaki köprüleri nasıl yok sayabilirim?

C: Aspose.Words for .NET ile değiştirirken üstbilgiler, altbilgiler veya dipnotlardaki köprüleri yok saymak için gelişmiş arama seçeneklerini kullanabilir ve uygun arama sınırlarını belirleyebilirsiniz. Örneğin, aramayı belgenin ana bölümleriyle sınırlayabilir ve üst bilgileri, alt bilgileri veya dipnotları hariç tutabilirsiniz.

#### S: Köprüleri belgenin diğer bölümlerine dahili bağlantılarla değiştirmek mümkün müdür?

 C: Evet, Aspose.Words for .NET ile köprüleri belgenin diğer bölümlerine giden dahili bağlantılarla değiştirmek mümkündür. Dahili bağlantılar oluşturmak için çapaları veya metin kimliklerini kullanabilir ve ardından bunları kullanarak değiştirebilirsiniz.`Document.Range.Replace` Uygun seçeneklerle yöntem.

#### S: Köprüleri Aspose.Words for .NET ile değiştirmek, renkler veya stiller gibi bağlantı özelliklerini koruyor mu?

C: Evet, köprüleri Aspose.Words for .NET ile değiştirirken, renkler veya stiller gibi bağlantı özellikleri korunur. Tutarlı bir sonuç elde etmek için değiştirme metninde aynı biçimlendirme özelliklerini belirtebilirsiniz.