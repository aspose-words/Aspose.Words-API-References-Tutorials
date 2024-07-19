---
title: Tercih Edilen Genişlik Tipini Al
linktitle: Tercih Edilen Genişlik Tipini Al
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word tablosundaki bir hücrenin tipini ve tercih edilen genişlik değerini nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/retrieve-preferred-width-type/
---

Bu eğitimde, tercih edilen genişlik tipini ve değerini Aspose.Words for .NET kullanarak bir Word belgesindeki tablo hücresinden nasıl alacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, tercih edilen genişlik türünü (mutlak, göreli veya otomatik) ve Word belge tablolarınızdaki belirli bir hücrenin değerini alabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme
Belgeyle Sözcük İşleme'yi başlatmak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Tables.docx");
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden ve doğru dosya adını girdiğinizden emin olun.

## 3. Adım: Tercih edilen genişlik türünü ve değerini alma
Daha sonra, belirli bir tablo hücresi için tercih edilen genişlik türünü ve değerini alacağız. Aşağıdaki kodu kullanın:

```csharp
// Masayı geri al
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Otomatik masa ayarını etkinleştirin
table. AllowAutoFit = true;

// İlk satırın ilk hücresini al
Cell firstCell = table.FirstRow.FirstCell;

// Tercih edilen genişlik türünü ve değerini alın
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

Burada ilk tabloyu getirmek için belgeyi kullanıyoruz, ardından otomatik tablo uyumunu etkinleştiriyoruz.`AllowAutoFit` mülk. Daha sonra tablonun ilk satırının ilk hücresini alıyoruz. Bu hücreden tercih edilen genişlik tipini şu komutla alabiliriz:`PreferredWidth.Type` mülk ve değeri ile`PreferredWidth.Value` mülk.

### Aspose.Words for .NET kullanarak Tercih Edilen Genişlik Tipini Alma için örnek kaynak kodu 

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
Bu eğitimde, tercih edilen genişlik tipini ve değerini Aspose.Words for .NET kullanarak bir Word belgesindeki tablo hücresinden nasıl alacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, bu bilgiyi Word belge tablolarınızdaki belirli hücreler için alabilirsiniz.