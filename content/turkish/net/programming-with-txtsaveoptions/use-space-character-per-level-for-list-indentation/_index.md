---
title: Liste Girintisi İçin Düzey Başına Boşluk Karakteri Kullan
linktitle: Liste Girintisi İçin Düzey Başına Boşluk Karakteri Kullan
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te liste girintisi için seviye başına boşluk karakteri kullanma konusunda adım adım kılavuz. İyi yapılandırılmış Word belgelerini kolaylıkla oluşturun.
type: docs
weight: 10
url: /tr/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmaya, düzenlemeye ve işlemeye yönelik güçlü bir kitaplıktır. Aspose.Words'ün sunduğu özellikler arasında listelerin girintisi için seviye başına bir boşluk karakteri kullanma olanağı da bulunmaktadır. Bu kılavuzda, bu işlevselliği uygulamak için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgeleriyle Kelime İşlemeyi kolay ve verimli hale getiren popüler bir kütüphanedir. Listelerin ve girintilerin yönetimi de dahil olmak üzere, Word belgelerini oluşturmak, değiştirmek ve işlemek için geniş bir işlevsellik yelpazesi sunar.

## Belgeyi oluşturma ve içerik ekleme

İlk adım, yeni bir belge oluşturmak ve ona içerik eklemektir. Yeni bir belge örneği oluşturmak için Document sınıfını kullanın. Daha sonra metin eklemek ve birden çok girinti düzeyine sahip bir liste oluşturmak için DocumentBuilder sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Üç düzeyde girintiye sahip bir liste oluşturun
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

Bu örnekte, yeni bir belge oluşturuyoruz ve metin eklemek ve üç girinti düzeyine sahip bir liste oluşturmak için DocumentBuilder'ı kullanıyoruz. Listeye üç öğe ekledik; her öğe ek bir düzey girintili olacak şekilde.

## Liste girintisi için düzey başına bir boşluk karakteri kullanma

İçerik eklendikten sonra artık listelerin girintisini seviye başına bir boşluk karakteri kullanarak yapılandırabiliriz. Bunun için TxtSaveOptions sınıfını kullanıyoruz ve ListIndentation.Count özelliğini girinti seviyesi sayısına, ListIndentation.Character özelliğini ise kullanılacak boşluk karakterine ayarlıyoruz. İşte nasıl:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

Bu örnekte, bir TxtSaveOptions örneği oluşturuyoruz ve listede üç girinti düzeyi olduğunu belirtmek için ListIndentation.Count özelliğini 3 olarak ayarlıyoruz. Ayrıca ListIndentation.Character özelliğini girintileme için kullanmak istediğimiz boşluk karakterine (' ') ayarladık.

### Aspose.Words for .NET'in "Liste girintisi için seviye başına bir boşluk karakteri kullan" özelliği için örnek kaynak kodu

Aspose.Words for .NET'teki "Liste girintisi için seviye başına bir boşluk karakteri kullan" özelliğinin tam örnek kaynak kodunu burada bulabilirsiniz:

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

             // Üç düzeyde girintiye sahip bir liste oluşturun
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

Bu kılavuzda Aspose.Words for .NET'in "Liste girintisi için seviye başına bir boşluk karakteri kullan" işlevini uygulamak için nasıl kullanılacağını açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak, düzey başına bir boşluk karakteri kullanarak Word belgelerinizdeki listelerin girintisini kolayca yapılandırabilirsiniz. Aspose.Words, metin biçimlendirme ve liste yönetimiyle Kelime İşleme için muazzam esneklik ve güç sunarak, C# uygulamanızda iyi yapılandırılmış belgeler oluşturmanıza olanak tanır.

### Sıkça Sorulan Sorular

#### S: Aspose.Words for .NET nedir?
Aspose.Words for .NET, bir C# uygulamasında Word belgelerini oluşturmak, düzenlemek ve değiştirmek için güçlü bir kütüphanedir. Listeleri girintilemek için seviye başına bir boşluk kullanma yeteneği de dahil olmak üzere, Word belgeleriyle Kelime İşleme için birçok özellik sunar.

#### S: Aspose.Words for .NET'te liste girintisi için seviye başına bir boşluğu nasıl kullanabilirim?
Aşağıdaki adımları izleyerek liste girintisi için düzey başına bir boşluk kullanabilirsiniz:

 kullanarak yeni bir belge oluşturun.`Document` sınıf.

 Kullan`DocumentBuilder`Belgeye içerik eklemek ve birden çok girinti düzeyine sahip bir liste oluşturmak için sınıfı kullanın.

 İçeriği ekledikten ve liste girintisini yapılandırdıktan sonra,`TxtSaveOptions` sınıfı seçin ve ayarlayın`ListIndentation.Count` girinti düzeyi sayısına ve`ListIndentation.Character` uzaydaki mülk (`' '`) kullanmak.

 Belgeyi belirtilen seçeneklerle kaydedin.`Save` yöntemi`Document` sınıf.

#### S: Aspose.Words liste girintisi için diğer karakterleri destekliyor mu?
Evet, Aspose.Words listelerin girintilenmesi için diğer karakterleri destekler. Sekmeler ( gibi boşluk olmayan karakterleri kullanabilirsiniz.`'\t'` ) veya diğer özel karakterleri ayarlayarak`ListIndentation.Character` özelliği istenilen karaktere ayarlayın.

#### S: Liste girintisi için düzey başına boşluk sayısını özelleştirmek mümkün mü?
 Evet, liste girintisi için düzey başına boşluk sayısını, değerini değiştirerek özelleştirebilirsiniz.`ListIndentation.Count` içindeki mülk`TxtSaveOptions` sınıf. Her girinti düzeyi için istediğiniz boşluk sayısını belirtebilirsiniz.

#### S: Aspose.Words liste yönetimi için başka hangi özellikleri sunuyor?
Aspose.Words, Word belgelerindeki listeleri yönetmek için birçok özellik sunar. Numaralandırılmış veya madde işaretli listeler oluşturabilir, girinti düzeylerini ayarlayabilir, listelerin stilini özelleştirebilir, liste öğeleri ekleyebilir ve daha fazlasını yapabilirsiniz.