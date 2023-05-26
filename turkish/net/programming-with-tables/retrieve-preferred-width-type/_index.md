---
title: Tercih Edilen Genişlik Tipini Al
linktitle: Tercih Edilen Genişlik Tipini Al
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word tablosundaki bir hücrenin tipini ve tercih edilen genişlik değerini nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/retrieve-preferred-width-type/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablo hücresinden tercih edilen genişlik tipini ve değerini almayı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu öğreticinin sonunda, Word belge tablolarınızdaki belirli bir hücre için tercih edilen genişlik türünü (mutlak, göreli veya otomatik) ve bunun değerini alabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme
Belgeyle çalışmaya başlamak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//belgeyi yükle
Document doc = new Document(dataDir + "Tables.docx");
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden ve doğru dosya adını girdiğinizden emin olun.

## 3. Adım: Tercih edilen genişlik tipini ve değerini alma
Ardından, belirli bir tablo hücresi için tercih edilen genişlik tipini ve değerini alacağız. Aşağıdaki kodu kullanın:

```csharp
// tabloyu al
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Otomatik tablo ayarını etkinleştirin
table. AllowAutoFit = true;

// İlk satırın ilk hücresini al
Cell firstCell = table.FirstRow.FirstCell;

// Tercih edilen genişlik tipini ve değerini alın
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

Burada ilk tabloyu getirmek için belgeyi kullanıyoruz, ardından otomatik tabloyu`AllowAutoFit` mülk. Sonra tablonun ilk satırının ilk hücresini alırız. Bu hücreden, tercih edilen genişlik tipini şu şekilde alabiliriz:`PreferredWidth.Type` özelliği ve değeri ile`PreferredWidth.Value` mülk.

### Aspose.Words for .NET kullanarak Tercih Edilen Genişlik Tipini Al için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablo hücresinden tercih edilen genişlik tipini ve değerini almayı öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, Word belge tablolarınızdaki belirli hücreler için bu bilgileri alabilirsiniz.