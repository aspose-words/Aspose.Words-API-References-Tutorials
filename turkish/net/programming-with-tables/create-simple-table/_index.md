---
title: Basit Tablo Oluştur
linktitle: Basit Tablo Oluştur
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesinde basit tablo oluşturmayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/create-simple-table/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde nasıl basit bir tablo oluşturacağımızı öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım bir kılavuz izleyeceğiz. Bu eğitimin sonunda, Word belgelerinizde programlı olarak özel tablolar oluşturabileceksiniz.

## Adım 1: Proje Kurulumu
1. Visual Studio'yu başlatın ve yeni bir C# projesi oluşturun.
2. Aspose.Words for .NET kitaplığına bir referans ekleyin.

## Adım 2: Belgeyi oluşturma ve belge oluşturucuyu başlatma
Tabloyu oluşturmaya başlamak için yeni bir belge oluşturmamız ve belge oluşturucuyu başlatmamız gerekiyor. Bu adımları takip et:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi oluşturun ve belge oluşturucuyu başlatın
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

"BELGELER DİZİNİNİZİ", belgeler dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Diziyi oluşturma
Ardından, belge oluşturucu tarafından sağlanan yöntemleri kullanarak tabloyu oluşturacağız. Aşağıdaki kodu kullanın:

```csharp
// Dizi oluşturmaya başla
builder. StartTable();

// İlk sıranın ilk hücresinin yapımı
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Birinci sıranın ikinci hücresinin yapımı
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//İlk satırı bitirmek ve yeni bir satır başlatmak için aşağıdaki yöntemi çağırın
builder. EndRow();

// İkinci sıranın ilk hücresinin yapımı
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// İkinci sıranın ikinci hücresinin inşası
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// İkinci satırı bitirmek için sonraki yöntemi çağırın
builder. EndRow();

// Tablonun yapımının bittiğinin göstergesi
builder. EndTable();
```

 Burada tabloyu adım adım oluşturmak için belge oluşturucuyu kullanıyoruz. arayarak başlıyoruz`StartTable()` tabloyu başlatmak için, ardından kullanın`InsertCell()` hücreleri eklemek ve`Write()` her hücreye içerik eklemek için. biz de kullanıyoruz`EndRow()` bir satırı bitirmek ve yeni bir satır başlatmak için. Sonunda diyoruz`EndTable()` tablo yapımının tamamlandığını belirtmek için.

## 4. Adım: Belgeyi kaydedin
Son olarak, kaydetmemiz gerekiyor

  oluşturulan tablonun bulunduğu belge. Aşağıdaki kodu kullanın:

```csharp
// belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Create Simple Table için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Tabloyu oluşturmaya başlayın.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// İkinci hücreyi oluşturun.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Satırı bitirmek ve yeni bir satır başlatmak için aşağıdaki yöntemi çağırın.
	builder.EndRow();
	// İkinci satırın ilk hücresini oluşturun.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// İkinci hücreyi oluşturun.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Tabloyu oluşturmayı bitirdiğimizin işareti.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde nasıl basit bir tablo oluşturacağımızı öğrendik. Bu adım adım kılavuzu izleyerek ve sağlanan C# kodunu uygulayarak, Word belgelerinizde programlı olarak özel tablolar oluşturabilirsiniz. Bu özellik, verilerinizi yapılandırılmış ve net bir şekilde biçimlendirmenize ve düzenlemenize olanak tanır.