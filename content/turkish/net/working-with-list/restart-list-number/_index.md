---
title: Liste Numarasını Yeniden Başlat
linktitle: Liste Numarasını Yeniden Başlat
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesindeki listenin numarasını nasıl sıfırlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-list/restart-list-number/
---
Bu adım adım eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki listenin numarasını nasıl sıfırlayacağınızı göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin:[Aspose.Releases]https://releases.aspose.com/words/net/.

## Adım 1: Belge ve Belge Oluşturucuyu Oluşturma

Öncelikle yeni bir belge ve ilişkili bir belge oluşturucu oluşturun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: İlk Listeyi Oluşturma ve Özelleştirme

Daha sonra mevcut bir şablonu temel alan bir liste oluşturun ve ardından düzeylerini özelleştirin:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## 3. Adım: İlk listeye öğe ekleme

İlk listeye öğe eklemek ve liste numaralarını kaldırmak için belge oluşturucuyu kullanın:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Adım 4: İkinci Listeyi Oluşturma ve Özelleştirme

Numarayı sıfırlayarak ilk listeyi yeniden kullanmak için orijinal liste düzeninin bir kopyasını oluşturun:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Gerekirse ikinci listede ek değişiklikler de yapabilirsiniz.

## Adım 5: Öğeleri ikinci listeye ekleme

İkinci listeye öğe eklemek ve liste numaralarını kaldırmak için belge oluşturucuyu tekrar kullanın:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Adım 6: Değiştirilen belgeyi kaydedin

Son olarak değiştirilen belgeyi kaydedin:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Bu yüzden ! Aspose.Words for .NET'i kullanarak bir Word belgesindeki liste numarasını başarıyla sıfırladınız.

### Liste Numarası Sıfırlaması için Örnek Kaynak Kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Şablona dayalı bir liste oluşturun.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// İlk listeyi yeniden kullanmak için orijinal liste formatının bir kopyasını oluşturarak numaralandırmayı yeniden başlatmamız gerekir.
List list2 = doc.Lists.AddCopy(list1);

// Yeni listeyi, yeni bir başlangıç numarası ayarlamak da dahil olmak üzere herhangi bir şekilde değiştirebiliriz.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### SSS'ler

#### S: Aspose.Words'te bir listenin numaralandırmasını nasıl yeniden başlatabilirim?

 C: Aspose.Words'te bir listenin numaralandırılmasını yeniden başlatmak için`ListRestartAtNumber` yöntemi`List` sınıf. Bu yöntem, listenin yeniden başlatılması gereken yeni bir arama değeri ayarlamanıza olanak tanır. Örneğin, kullanabilirsiniz`list.ListRestartAtNumber(1)` Numaralandırmayı 1'den yeniden başlatmak için

#### S: Aspose.Words'te yeniden başlatılan liste numaralandırmasının önekini ve sonekini özelleştirmek mümkün mü?

 C: Evet, Aspose.Words'te yeniden başlatılan liste numaralandırmasının önekini ve sonekini özelleştirebilirsiniz.`ListLevel` sınıf gibi özellikler sunar`ListLevel.NumberPrefix` Ve`ListLevel.NumberSuffix` bu, listedeki her düzey için önek ve son eki belirtmenize olanak tanır. Ön eki ve son eki gerektiği gibi özelleştirmek için bu özellikleri kullanabilirsiniz.

#### S: Listenin yeniden başlatılması gereken belirli bir numaralandırma değerini nasıl belirleyebilirim?

C: Listenin yeniden başlatılması gereken belirli bir sayı değerini belirtmek için`ListRestartAtNumber` İstenilen değeri argüman olarak ileten yöntem. Örneğin, numaralandırmayı 5'ten yeniden başlatmak için şunu kullanabilirsiniz:`list.ListRestartAtNumber(5)`.

#### S: Aspose.Words'te çok seviyeli liste numaralandırmayı yeniden başlatmak mümkün mü?

 C: Evet, Aspose.Words birden fazla liste düzeyinde yeniden numaralandırmayı destekler. Şunu uygulayabilirsiniz:`ListRestartAtNumber` Numaralandırmayı tek tek yeniden başlatmak için her liste düzeyindeki yöntemi kullanın. Örneğin, kullanabilirsiniz`list.Levels[0].ListRestartAtNumber(1)` ilk liste düzeyini 1'den yeniden başlatmak için ve`list.Levels[1].ListRestartAtNumber(1)` 1'den başlayarak ikinci düzey listeyi yeniden başlatmak için.



