---
title: Göreli Yatay veya Dikey Konumu Ayarla
linktitle: Göreli Yatay veya Dikey Konumu Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde bir tablonun göreceli yatay veya dikey konumunu nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

Bu derste, Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablonun göreceli yatay veya dikey konumunun nasıl ayarlanacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizdeki tablonuzun göreceli yatay veya dikey konumunu ayarlayabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi yükleme
Belgeyle Sözcük İşleme'yi başlatmak için şu adımları izleyin:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden ve doğru dosya adını girdiğinizden emin olun.

## Adım 3: Tablonun göreceli konumunu ayarlama
Daha sonra tablonun göreceli yatay veya dikey konumunu ayarlayacağız. Aşağıdaki kodu kullanın:

```csharp
// Masayı geri al
Table table = doc.FirstSection.Body.Tables[0];

//Tablonun göreceli yatay konumunun tanımı
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Tablonun göreceli dikey konumunu tanımlayın
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Burada belgeyi, ilk bölümün gövdesinden ilk tabloyu almak için kullanıyoruz. Daha sonra tablonun göreceli yatay konumunu şu şekilde ayarlıyoruz:`HorizontalAnchor` özelliğini kullanarak`RelativeHorizontalPosition.Column` değer. Benzer şekilde, tablonun göreceli dikey konumunu da şu şekilde belirleriz:`VerticalAnchor` özelliğini kullanarak`RelativeVerticalPosition.Page` değer.

## Adım 4: Değiştirilen belgeyi kaydetme
Son olarak, değiştirilen belgeyi, tanımlanan tablonun göreceli konumuyla kaydetmemiz gerekiyor. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Göreceli Yatay veya Dikey Konumu Ayarlama için örnek kaynak kodu 

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
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki bir tablonun göreceli yatay veya dikey konumunun nasıl ayarlanacağını öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, bu göreceli konumu Word belgelerinizdeki tablolarınıza uygulayabilirsiniz.