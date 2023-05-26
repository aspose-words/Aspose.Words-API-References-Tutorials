---
title: Satır Biçimi Sayfalar Arasında Arayı Devre Dışı Bırak
linktitle: Satır Biçimi Sayfalar Arasında Arayı Devre Dışı Bırak
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde birden çok sayfada bir tablo için satır sonunu nasıl devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/row-format-disable-break-across-pages/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde çok sayfalı bir tablonun satır sonunu nasıl devre dışı bırakacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablonuzdaki tüm satırlar için satır kesmeyi devre dışı bırakabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme
Belgeyle çalışmaya başlamak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//belgeyi yükle
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden ve doğru dosya adını girdiğinizden emin olun.

## 3. Adım: Tablo satır sonunu devre dışı bırakın
Ardından, tablodaki tüm satırlar için satır kesmeyi devre dışı bırakacağız. Aşağıdaki kodu kullanın:

```csharp
// tabloyu al
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Tablodaki tüm satırlar için satır sonunu devre dışı bırak
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Burada ilk tabloyu getirmek için belgeyi kullanıyoruz ve ardından bir foreach döngüsü kullanarak tablodaki tüm satırları yineliyoruz. Döngünün içinde, ayarlayarak her satır için satır kesmeyi devre dışı bırakırız.`RowFormat.AllowBreakAcrossPages` mülkiyet`false`.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi tablo satır sonu devre dışı bırakılmış olarak kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Sayfalar Arasında Arayı Devre Dışı Bırakmak için Satır Biçimi için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Tablodaki tüm satırlar için sayfalar arasında bölmeyi devre dışı bırakın.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde çok sayfalı bir tablonun satır sonunu nasıl devre dışı bırakacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, bu devre dışı bırakmayı Word belgelerinizdeki tablolarınıza uygulayabilirsiniz.