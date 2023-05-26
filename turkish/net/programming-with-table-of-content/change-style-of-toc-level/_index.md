---
title: Toc Düzeyinin Stilini Değiştirme
linktitle: Toc Düzeyinin Stilini Değiştirme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki içindekiler düzeyi stilini kolayca nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-table-of-content/change-style-of-toc-level/
---

Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmak, düzenlemek ve değiştirmek için güçlü bir kitaplıktır. Aspose.Words'ün sunduğu özellikler arasında, bir belgenin içindekiler tablosunun belirli bir düzeyinin stilini değiştirebilme yeteneği vardır. Bu kılavuzda, bir Word belgesinin içindekiler tablosu düzeyinin stilini değiştirmek için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, Word belgeleriyle çalışmayı kolay ve verimli hale getiren popüler bir kitaplıktır. İçindekiler tablosunun stilini değiştirmek de dahil olmak üzere Word belgeleri oluşturmak, düzenlemek ve değiştirmek için çok çeşitli özellikler sunar.

## yeni bir belge oluşturma

İlk adım, içindekiler tablosu stilini değiştirmek istediğiniz yeni bir Word belgesi oluşturmaktır. Yeni bir belge oluşturmak için Document sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document();
```

Bu örnekte, yeni bir boş belge oluşturuyoruz.

## İçindekiler tablosu düzeyinin stilini değiştirme

Belge oluşturulduktan sonra, belge stillerine erişebilir ve içindekiler tablosunun belirli bir düzeyi için kullanılan stili değiştirebilirsiniz. Bu örnekte, içindekiler tablosunun ilk düzeyi için kullanılan stili değiştireceğiz. İşte nasıl:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

Bu örnekte, belge stillerine erişmek için Document sınıfının Styles özelliğini kullanıyoruz. Ardından, içindekiler tablosunun ilk düzeyi için kullanılan stile erişmek için StyleIdentifier.Toc1 stil tanımlayıcısını kullanırız. Son olarak, stili kalın yapmak için Font.Bold özelliğini değiştiriyoruz.

## Değiştirilen belgeyi kaydet

İçindekiler tablosunun stilinde gerekli değişiklikleri yaptıktan sonra, değiştirilen belgeyi Document sınıfının Save yöntemini kullanarak kaydedebilirsiniz. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

Bu örnekte değiştirilen belgeyi "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx" olarak kaydediyoruz.

## Aspose.Words for .NET ile "İçindekiler düzeyinin stilini değiştirme" özelliği için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Yeni bir belge oluştur
Document doc = new Document();

// İçindekiler tablosunun ilk seviyesinin stilinin değiştirilmesi
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## Çözüm

Bu kılavuzda, sağlanan C# kaynak kodunu kullanarak bir Word belgesinin içindekiler tablosu düzeyinin stilini değiştirmek için Aspose.Words for .NET'in nasıl kullanılacağını açıkladık. Sağlanan adımları izleyerek, C# uygulamanızdaki Word belgelerinizdeki içindekiler tablosunun stilini kolayca özelleştirebilirsiniz. Aspose.Words, çekici ve profesyonel Word belgeleri oluşturmanıza izin vererek, belgelerinizin stilleri ve biçimlendirmesiyle çalışmak için muazzam bir esneklik ve güç sunar.