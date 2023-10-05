---
title: Satır Formatı Sayfalar Arasında Kesmeyi Devre Dışı Bırak
linktitle: Satır Formatı Sayfalar Arasında Kesmeyi Devre Dışı Bırak
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde birden çok sayfadaki bir tablo için satır sonunu nasıl devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/row-format-disable-break-across-pages/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde çok sayfalı bir tablonun satır sonunun nasıl devre dışı bırakılacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablonuzdaki tüm satırlar için satır kesmeyi devre dışı bırakabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme
Belgeyle Sözcük İşleme'yi başlatmak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden ve doğru dosya adını girdiğinizden emin olun.

## 3. Adım: Tablo satır sonunu devre dışı bırakın
Daha sonra tablodaki tüm satırlar için satır kesmeyi devre dışı bırakacağız. Aşağıdaki kodu kullanın:

```csharp
// Masayı geri al
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Tablodaki tüm satırlar için satır sonunu devre dışı bırak
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Burada belgeyi ilk tabloyu getirmek için kullanıyoruz ve ardından foreach döngüsü kullanarak tablodaki tüm satırları yineliyoruz. Döngünün içinde, her satır için satır kesmeyi devre dışı bırakırız.`RowFormat.AllowBreakAcrossPages`mülkiyet`false`.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi tablo satırı sonu devre dışı bırakılarak kaydetmemiz gerekir. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Sayfalar Arasında Kesmeyi Devre Dışı Bırakma Satır Formatı için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Tablodaki tüm satırlar için sayfalar arası bölmeyi devre dışı bırakın.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde çok sayfalı bir tablonun satır sonunun nasıl devre dışı bırakılacağını öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak bu devre dışı bırakma işlemini Word belgelerinizdeki tablolarınıza uygulayabilirsiniz.