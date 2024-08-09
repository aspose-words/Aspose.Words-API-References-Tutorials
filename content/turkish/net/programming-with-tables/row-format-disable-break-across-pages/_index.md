---
title: Satır Formatı Sayfalar Arasında Kesmeyi Devre Dışı Bırak
linktitle: Satır Formatı Sayfalar Arasında Kesmeyi Devre Dışı Bırak
second_title: Aspose.Words Belge İşleme API'si
description: Tablo okunabilirliğini ve formatını korumak için Aspose.Words for .NET'i kullanarak Word belgelerindeki sayfalar arasında satır sonlarını nasıl devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/row-format-disable-break-across-pages/
---
## giriiş

Word belgelerindeki tablolarla çalışırken satırların sayfalara bölünmediğinden emin olmak isteyebilirsiniz; bu, belgelerinizin okunabilirliğini ve biçimlendirmesini korumak için önemli olabilir. Aspose.Words for .NET sayfalar arasında satır sonlarını devre dışı bırakmanın kolay bir yolunu sunar.

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki sayfalar arasındaki satır sonlarını devre dışı bırakma sürecinde size yol göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi kuruldu.
- Birden çok sayfaya yayılan bir tablo içeren bir Word belgesi.

## Ad Alanlarını İçe Aktar

Öncelikle projenize gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## 1. Adım: Belgeyi Yükleyin

Birden fazla sayfaya yayılan tabloyu içeren belgeyi yükleyin.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Adım 2: Tabloya Erişin

Belgedeki ilk tabloya erişin. Bu, değiştirmek istediğiniz tablonun belgedeki ilk tablo olduğunu varsayar.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## 3. Adım: Tüm Satırlar için Sayfalar Arasında Geçişi Devre Dışı Bırakma

 Tablodaki her satırda döngü yapın ve`AllowBreakAcrossPages`mülkiyet`false`. Bu, satırların sayfalar arasında bölünmemesini sağlar.

```csharp
// Tablodaki tüm satırlar için sayfalar arası bölmeyi devre dışı bırakın.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Adım 4: Belgeyi Kaydedin

Değiştirilen belgeyi belirttiğiniz dizine kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki sayfalar arasındaki satır sonlarının nasıl devre dışı bırakılacağını gösterdik. Yukarıda özetlenen adımları izleyerek tablo satırlarınızın sağlam kalmasını ve sayfalara bölünmemesini sağlayarak belgenin okunabilirliğini ve biçimlendirmesini koruyabilirsiniz.

## SSS'ler

### Tüm satırlar yerine belirli bir satır için sayfalar arasındaki satır sonlarını devre dışı bırakabilir miyim?  
 Evet, istediğiniz satıra erişip satır sonlarını ayarlayarak belirli satırlar için satır sonlarını devre dışı bırakabilirsiniz.`AllowBreakAcrossPages`mülkiyet`false`.

### Bu yöntem birleştirilmiş hücreli tablolar için işe yarar mı?  
 Evet, bu yöntem birleştirilmiş hücreli tablolar için işe yarar. Mülkiyet`AllowBreakAcrossPages` hücre birleşmesinden bağımsız olarak tüm satıra uygulanır.

### Tablo başka bir tablonun içine yerleştirilmişse bu yöntem işe yarar mı?  
Evet, iç içe geçmiş tablolara aynı şekilde erişebilir ve bunları değiştirebilirsiniz. Yuvalanmış tabloya dizinine veya diğer özelliklerine göre doğru bir şekilde başvuruda bulunduğunuzdan emin olun.

### Bir satırın sayfalar arasında bölünmeye izin verip vermediğini nasıl kontrol edebilirim?  
 Bir satırın sayfalar arasında bölünmeye izin verip vermediğini şu adrese erişerek kontrol edebilirsiniz:`AllowBreakAcrossPages` mülkiyeti`RowFormat` ve değerini kontrol ediyoruz.

### Bu ayarı bir belgedeki tüm tablolara uygulamanın bir yolu var mı?  
Evet, belgedeki tüm tablolar arasında geçiş yapabilir ve bu ayarı her birine uygulayabilirsiniz.