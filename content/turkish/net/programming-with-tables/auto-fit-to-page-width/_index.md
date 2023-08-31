---
title: Sayfa Genişliğine Otomatik Sığdır
linktitle: Sayfa Genişliğine Otomatik Sığdır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde bir tabloyu sayfa genişliğine nasıl otomatik olarak sığdıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/auto-fit-to-page-width/
---

Bu eğitimde, bir Word belgesindeki tabloyu sayfa genişliğine otomatik olarak sığdırmak için Aspose.Words for .NET'in nasıl kullanılacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerindeki tabloları programlı olarak değiştirebileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi Oluşturma ve Yapılandırma
Kelime İşleme'yi tabloyla başlatmak için bir belge oluşturmamız ve belge oluşturucuyu yapılandırmamız gerekir. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi ve belge oluşturucuyu oluşturun
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## Adım 3: Tabloyu Ekleme ve Yapılandırma
Daha sonra belgeye sayfanın genişliğinin yarısını kaplayan genişliğe sahip bir tablo ekleyeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Tabloyu ekleyin ve genişliğini yapılandırın
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Burada tabloyu oluşturmaya başlamak, hücreleri eklemek ve tablonun tercih edilen genişliğini sayfa genişliğinin %50'sine ayarlamak için belge oluşturucuyu kullanıyoruz. Daha sonra her hücreye metin ekliyoruz.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi, sayfanın genişliğine göre ayarlanmış tabloyla kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
// Değiştirilen belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.
  
### Aspose.Words for .NET kullanarak Sayfa Genişliğine Otomatik Sığdır için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Sayfa genişliğinin yarısını kaplayan genişliğe sahip bir tablo ekleyin.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde bir tabloyu sayfa genişliğine otomatik olarak nasıl sığdıracağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, Word belgelerinizdeki tabloları programlı olarak değiştirebilirsiniz. Bu özellik, tablonun genişliğini sayfaya göre dinamik olarak uyarlamanıza olanak tanır, böylece profesyonel ve görsel olarak çekici bir belge sunar.