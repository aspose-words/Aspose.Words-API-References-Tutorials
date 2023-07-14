---
title: Göreceli Yatay veya Dikey Konumu Ayarla
linktitle: Göreceli Yatay veya Dikey Konumu Ayarla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki bir tablonun göreli yatay veya dikey konumunu nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablonun göreli yatay veya dikey konumunu nasıl ayarlayacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizde tablonuzun göreli yatay veya dikey konumunu ayarlayabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Belgeyi yükleme
Sözcük İşlemeyi belgeyle başlatmak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi yükle
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden ve doğru dosya adını girdiğinizden emin olun.

## 3. Adım: Tablonun göreli konumunun ayarlanması
Ardından, tablonun göreli yatay veya dikey konumunu ayarlayacağız. Aşağıdaki kodu kullanın:

```csharp
// tabloyu al
Table table = doc.FirstSection.Body.Tables[0];

//Tablonun göreli yatay konumunun tanımı
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Tablonun göreli dikey konumunu tanımlayın
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Burada, ilk bölümün gövdesinden ilk tabloyu almak için belgeyi kullanıyoruz. Ardından, tablonun göreli yatay konumunu`HorizontalAnchor` özelliğini kullanan`RelativeHorizontalPosition.Column` değer. Benzer şekilde, tablonun göreli dikey konumunu`VerticalAnchor` özelliğini kullanan`RelativeVerticalPosition.Page` değer.

## 4. Adım: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilmiş belgeyi tanımlanmış tablonun göreli konumu ile kaydetmemiz gerekir. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Göreceli Yatay Veya Dikey Konum Belirlemek için örnek kaynak kodu 

```csharp
//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablonun göreli yatay veya dikey konumunu nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, bu göreli konumu Word belgelerinizdeki tablolarınıza uygulayabilirsiniz.