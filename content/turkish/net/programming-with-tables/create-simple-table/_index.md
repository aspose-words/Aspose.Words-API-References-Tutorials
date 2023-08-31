---
title: Basit Tablo Oluştur
linktitle: Basit Tablo Oluştur
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde nasıl basit bir tablo oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/create-simple-table/
---

Bu derste Aspose.Words for .NET kullanarak bir Word belgesinde basit bir tablonun nasıl oluşturulacağını öğreneceğiz. Kodu anlamak ve bu özelliği uygulamak için adım adım kılavuzu takip edeceğiz. Bu eğitimin sonunda, Word belgelerinizde programlı olarak özel tablolar oluşturabileceksiniz.

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

"BELGELERİNİZ DİZİNİ"ni belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Diziyi oluşturma
Daha sonra belge oluşturucunun sağladığı yöntemleri kullanarak tabloyu oluşturacağız. Aşağıdaki kodu kullanın:

```csharp
// Dizi yapımına başla
builder. StartTable();

// İlk sıranın ilk hücresinin inşaatı
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// İlk sıranın ikinci hücresinin inşaatı
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//İlk satırı bitirmek ve yeni bir satır başlatmak için aşağıdaki yöntemi çağırın
builder. EndRow();

// İkinci sıranın ilk hücresinin inşaatı
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// İkinci sıranın ikinci hücresinin inşaatı
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// İkinci satırı sonlandırmak için sonraki yöntemi çağırın
builder. EndRow();

// Masanın yapımının bittiğini gösteren gösterge
builder. EndTable();
```

 Burada tabloyu adım adım oluşturmak için belge oluşturucuyu kullanıyoruz. arayarak başlıyoruz`StartTable()` tabloyu başlatmak için kullanın, ardından kullanın`InsertCell()` hücreleri eklemek için ve`Write()` Her hücreye içerik eklemek için Biz de kullanıyoruz`EndRow()` Bir satırı bitirmek ve yeni bir satıra başlamak için. Sonunda diyoruz`EndTable()` Masa yapımının tamamlandığını belirtmek için.

## 4. Adım: Belgeyi kaydedin
Son olarak kaydetmemiz gerekiyor

  oluşturulan tablonun bulunduğu belge. Aşağıdaki kodu kullanın:

```csharp
// Belgeyi kaydet
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Çıktı belgesi için doğru yolu ve dosya adını belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Basit Tablo Oluşturma için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Masayı oluşturmaya başlayın.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// İkinci hücreyi oluşturun.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Satırı sonlandırıp yeni bir satır başlatmak için aşağıdaki yöntemi çağırın.
	builder.EndRow();
	// İkinci satırın ilk hücresini oluşturun.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// İkinci hücreyi oluşturun.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Masayı oluşturmayı bitirdiğimizi belirtin.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde basit bir tablonun nasıl oluşturulacağını öğrendik. Bu adım adım kılavuzu izleyerek ve verilen C# kodunu uygulayarak, Word belgelerinizde programlı olarak özel tablolar oluşturabilirsiniz. Bu özellik, verilerinizi yapılandırılmış ve net bir şekilde biçimlendirmenize ve düzenlemenize olanak tanır.