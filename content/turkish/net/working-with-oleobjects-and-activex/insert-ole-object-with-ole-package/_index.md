---
title: Ole Paketi ile Word'e Ole Nesnesi Ekleme
linktitle: Ole Paketi ile Word'e Ole Nesnesi Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak OLE nesnelerini Word belgelerine nasıl ekleyeceğinizi öğrenin. Dosyaları sorunsuz bir şekilde gömmek için ayrıntılı adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---
## giriiş

Bir dosyayı bir Word belgesine gömmek istediyseniz doğru yerdesiniz. İster ZIP dosyası, ister Excel sayfası, ister başka bir dosya türü olsun, onu doğrudan Word belgenize yerleştirmek inanılmaz derecede yararlı olabilir. Bunu, belgenizde her türlü hazineyi saklayabileceğiniz gizli bir bölmenin olması gibi düşünün. Bugün bunu Aspose.Words for .NET kullanarak nasıl yapacağımızı anlatacağız. Bir Word sihirbazı olmaya hazır mısınız? Hadi dalalım!

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Words for .NET: Henüz yapmadıysanız adresinden indirin.[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya başka herhangi bir .NET geliştirme ortamı.
3. Temel C# Anlayışı: Uzman olmanıza gerek yok, ancak C#'ı nasıl kullanacağınızı bilmek yardımcı olacaktır.
4. Belge Dizini: Belgeleri saklayabileceğiniz ve alabileceğiniz bir klasör.

## Ad Alanlarını İçe Aktar

Öncelikle isim alanlarımızı düzene koyalım. Projenize aşağıdaki ad alanlarını eklemeniz gerekir:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Bunu küçük adımlara bölelim, böylece takip edilmesi kolay olur.

## 1. Adım: Belgenizi Ayarlayın

Boş bir tuvali olan bir sanatçı olduğunuzu hayal edin. Öncelikle Word belgemiz olan boş tuvalimize ihtiyacımız var. Bunu nasıl ayarlayacağınız aşağıda açıklanmıştır:

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Bu kod yeni bir Word belgesini başlatır ve belgemize içerik eklemek için kullanacağımız DocumentBuilder'ı kurar.

## Adım 2: Ole Nesnenizi Okuyun

Daha sonra yerleştirmek istediğiniz dosyayı okuyalım. Bunu gizli bölmenizde saklamak istediğiniz hazineyi almak gibi düşünün:

```csharp
byte[] bs = File.ReadAllBytes(dataDir + "Zip file.zip");
```

Bu satır, ZIP dosyanızdaki tüm baytları okur ve bunları bir bayt dizisinde saklar.

## Adım 3: Ole Nesnesini Ekleyin

Şimdi işin sihirli kısmı geliyor. Dosyayı Word belgemize gömeceğiz:

```csharp
using (Stream stream = new MemoryStream(bs))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);
    OlePackage olePackage = shape.OleFormat.OlePackage;
    olePackage.FileName = "filename.zip";
    olePackage.DisplayName = "displayname.zip";
}
```

 Burada bayt dizisinden bir bellek akışı oluşturuyoruz ve bunu kullanıyoruz.`InsertOleObject` belgeye yerleştirme yöntemini kullanın. Ayrıca gömülü nesnenin dosya adını ve görünen adını da ayarladık.

## 4. Adım: Belgenizi Kaydedin

Son olarak şaheserimizi kaydedelim:

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Bu, belgeyi gömülü dosyanızla birlikte belirtilen dizine kaydeder.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir OLE nesnesini bir Word belgesine başarıyla gömdünüz. Bu, belgenizin içine her an ortaya çıkabilecek gizli bir mücevher eklemek gibidir. Bu teknik, teknik dokümantasyondan dinamik raporlara kadar çeşitli uygulamalar için inanılmaz derecede faydalı olabilir. 

## SSS'ler

### Bu yöntemi kullanarak başka dosya türlerini gömebilir miyim?
Evet, Excel sayfaları, PDF'ler ve resimler gibi çeşitli dosya türlerini gömebilirsiniz.

### Aspose.Words için lisansa ihtiyacım var mı?
 Evet, geçerli bir lisansa ihtiyacınız var. Alabilirsin[geçici lisans](https://purchase.aspose.com/temporary-license/) değerlendirme için.

### OLE nesnesinin görünen adını nasıl özelleştirebilirim?
 Ayarlayabilirsiniz`DisplayName` mülkiyeti`OlePackage` özelleştirmek için.

### Aspose.Words .NET Core ile uyumlu mu?
Evet, Aspose.Words hem .NET Framework'ü hem de .NET Core'u destekler.

### Katıştırılmış OLE nesnesini Word belgesinde düzenleyebilir miyim?
Hayır, OLE nesnesini doğrudan Word'ün içinden düzenleyemezsiniz. Yerel uygulamasında açmanız gerekir.