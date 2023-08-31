---
title: Tablo İçeriği Hizalamasıyla Markdown'a Aktarma
linktitle: Tablo İçeriği Hizalamasıyla Markdown'a Aktarma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak tablo içeriğini farklı hizalamalarla Markdown dosyalarına nasıl aktaracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Burada, .NET için Aspose.Words kütüphanesini kullanarak içeriği tablo içeriği hizalamayla bir Markdown dosyasına aktarmaya yardımcı olan aşağıdaki C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır. Bu kodu kullanmadan önce projenize Aspose.Words kütüphanesini eklediğinizden emin olun.

## 1. Adım: Belge dizini yolunu ayarlayın

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Düzenlenen belgenin kaydedileceği belge dizininize giden doğru yolu belirttiğinizden emin olun.

## Adım 2: Bir belge ve belge oluşturucu oluşturun

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Burada bir örneğini oluşturuyoruz`Document` sınıf ve bir örnek`DocumentBuilder` belgeyi değiştirmemize ve öğeler eklememize izin verecek sınıf.

## 3. Adım: Farklı paragraf hizalamalarına sahip hücreleri tabloya ekleyin

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Tabloya hücre eklemek ve her hücre için farklı paragraf hizalamaları ayarlamak için Belge Oluşturucu'yu kullanıyoruz.

## 4. Adım: Markdown dışa aktarma seçeneklerini ayarlayın ve değiştirilen belgeyi kaydedin

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Markdown dışa aktarma seçeneklerini farklı tablo içeriği hizalamalarıyla ayarlıyoruz, ardından değiştirilen belgeyi her hizalama seçeneğini kullanarak kaydediyoruz.

### Aspose.Words for .NET kullanılarak tablo içeriği hizalamayla Markdown'a aktarılacak örnek kaynak kodu

```csharp

            
	// Belgeler dizininin yolu.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Tablo içindeki tüm paragrafların hizalanmasını sağlar.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Bu durumda hizalama ilgili tablo sütunundaki ilk paragraftan alınacaktır.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Değiştirilen belgeyi kaydet
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
