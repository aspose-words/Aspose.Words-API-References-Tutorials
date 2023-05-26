---
title: Liste Girintisi İçin Düzey Başına Boşluk Karakteri Kullanın
linktitle: Liste Girintisi İçin Düzey Başına Boşluk Karakteri Kullanın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te liste girintisi için seviye başına bir boşluk karakteri kullanmaya yönelik adım adım kılavuz. İyi yapılandırılmış Word belgelerini kolaylıkla oluşturun.
type: docs
weight: 10
url: /tr/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmak, düzenlemek ve değiştirmek için güçlü bir kitaplıktır. Aspose.Words'ün sunduğu özellikler arasında, liste girintileri için seviye başına bir boşluk karakteri kullanma olasılığı yer alır. Bu kılavuzda, bu işlevi uygulamak için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, Word belgeleriyle çalışmayı kolay ve verimli hale getiren popüler bir kitaplıktır. Listelerin ve girintilerin yönetimi de dahil olmak üzere Word belgelerini oluşturmak, değiştirmek ve işlemek için çok çeşitli işlevler sunar.

## Belge oluşturma ve içerik ekleme

İlk adım, yeni bir belge oluşturmak ve ona içerik eklemektir. Yeni bir belge örneği oluşturmak için Document sınıfını kullanın. Ardından, metin eklemek ve birden çok girinti düzeyine sahip bir liste oluşturmak için DocumentBuilder sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Üç girinti düzeyi içeren bir liste oluşturun
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

Bu örnekte, yeni bir belge oluşturuyoruz ve DocumentBuilder'ı metin eklemek ve üç girinti düzeyine sahip bir liste oluşturmak için kullanıyoruz. Listeye üç öğe ekledik, her öğe ek bir düzey girintili.

## Liste girintisi için seviye başına bir boşluk karakteri kullanma

İçerik eklendikten sonra artık listelerin girintisini seviye başına bir boşluk karakteri kullanarak yapılandırabiliriz. Bunun için TxtSaveOptions sınıfını kullanıyoruz ve ListIndentation.Count özelliğini girinti seviyeleri sayısına ve ListIndentation.Character özelliğini kullanılacak boşluk karakterine ayarlıyoruz. İşte nasıl:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

Bu örnekte, bir TxtSaveOptions örneği oluşturuyoruz ve listede üç girinti düzeyi olduğunu belirtmek için ListIndentation.Count özelliğini 3 olarak ayarlıyoruz. Ayrıca ListIndentation.Character özelliğini girinti için kullanmak istediğimiz boşluk karakterine (' ') ayarlıyoruz.

### Aspose.Words for .NET ile "Liste girintisi için seviye başına bir boşluk karakteri kullan" özelliği için örnek kaynak kodu

Aspose.Words for .NET ile "Liste girintisi için seviye başına bir boşluk karakteri kullan" özelliği için tam örnek kaynak kodunu burada bulabilirsiniz:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Belge dizininizin yolu
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Belgeyi oluşturun ve içerik ekleyin
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Üç girinti düzeyi içeren bir liste oluşturun
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Liste girintisi için düzey başına bir boşluk karakteri kullanın
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Belgeyi belirtilen seçeneklerle kaydedin
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Çözüm

Bu kılavuzda, "Liste girintisi için düzey başına bir boşluk karakteri kullan" işlevini uygulamak için Aspose.Words for .NET'in nasıl kullanılacağını açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak, Word belgelerinizdeki listelerin girintisini düzey başına bir boşluk karakteri kullanarak kolayca yapılandırabilirsiniz. Aspose.Words, C# uygulamanızda iyi yapılandırılmış belgeler oluşturmanıza izin vererek, metin formatlama ve liste yönetimi ile çalışmak için muazzam bir esneklik ve güç sunar.