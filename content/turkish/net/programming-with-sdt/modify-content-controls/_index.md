---
title: İçerik Kontrollerini Değiştirin
linktitle: İçerik Kontrollerini Değiştirin
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word'deki yapılandırılmış belge etiketlerini nasıl değiştireceğinizi öğrenin. Metni, açılır menüleri ve görselleri adım adım güncelleyin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/modify-content-controls/
---
## giriiş

Daha önce Word belgeleriyle çalıştıysanız ve Aspose.Words for .NET'i kullanarak düz metin, açılır listeler veya resimler gibi yapılandırılmış içerik kontrollerini değiştirmeniz gerekiyorsa, doğru yerdesiniz! Yapılandırılmış Belge Etiketleri (SDT'ler), belge otomasyonunu daha kolay ve daha esnek hale getiren güçlü araçlardır. Bu eğitimde, bu SDT'leri ihtiyaçlarınıza uyacak şekilde nasıl değiştirebileceğinizi ele alacağız. İster metni güncelliyor, ister açılır menü seçimlerini değiştiriyor, ister görselleri değiştiriyor olun, bu kılavuz süreç boyunca size adım adım yol gösterecektir.

## Önkoşullar

İçerik kontrollerini değiştirmenin en ince ayrıntılarına geçmeden önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET Kurulu: Aspose.Words kütüphanesinin kurulu olduğundan emin olun. Değilse, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).

2. Temel C# Bilgisi: Bu eğitimde temel C# programlama kavramlarına aşina olduğunuz varsayılmaktadır.

3. .NET Geliştirme Ortamı: .NET uygulamalarını çalıştırmak için Visual Studio benzeri bir IDE'ye sahip olmanız gerekir.

4. Örnek Bir Belge: Çeşitli SDT türlerini içeren örnek bir Word belgesi kullanacağız. Örnektekini kullanabilir veya kendinizinkini oluşturabilirsiniz.

5.  Aspose Dokümantasyonuna Erişim: Daha ayrıntılı bilgi için bkz.[Aspose.Words belgeleri](https://reference.aspose.com/words/net/).

## Ad Alanlarını İçe Aktar

Aspose.Words ile çalışmaya başlamak için ilgili ad alanlarını C# projenize aktarmanız gerekir. İşte bunu nasıl yapacağınız:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Bu ad alanları, Word belgelerinizdeki yapılandırılmış belge etiketlerini değiştirmek için gerekli sınıflara ve yöntemlere erişmenizi sağlayacaktır.

## 1. Adım: Belge Yolunuzu Ayarlayın

 Herhangi bir değişiklik yapmadan önce belgenizin yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin saklandığı gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Structured document tags.docx");
```

## Adım 2: Yapılandırılmış Belge Etiketlerinde Döngü Yapın

 SDT'leri değiştirmek için öncelikle belgedeki tüm SDT'ler arasında döngü yapmanız gerekir. Bu, kullanılarak yapılır.`GetChildNodes` türdeki tüm düğümleri alma yöntemi`StructuredDocumentTag`.

```csharp
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // SDT'leri türlerine göre değiştirin
}
```

## 3. Adım: Düz Metin SDT'lerini değiştirin

SDT düz metin türüyse içeriğini değiştirebilirsiniz. Öncelikle mevcut içeriği temizleyin, ardından yeni metin ekleyin.

```csharp
if (sdt.SdtType == SdtType.PlainText)
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
}
```

 Açıklama: Burada,`RemoveAllChildren()`SDT'nin mevcut içeriğini temizler. Daha sonra yeni bir tane oluşturuyoruz`Paragraph`Ve`Run` Yeni metni eklemek için nesneyi seçin.

## 4. Adım: Açılır Liste SDT'lerini değiştirin

 Açılır liste SDT'leri için, seçilen öğeyi şuraya erişerek değiştirebilirsiniz:`ListItems` koleksiyon. Burada listedeki üçüncü öğeyi seçiyoruz.

```csharp
if (sdt.SdtType == SdtType.DropDownList)
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
}
```

Açıklama: Bu kod parçacığı, açılır listeden dizin 2'deki (üçüncü öğe) öğeyi seçer. Endeksi ihtiyaçlarınıza göre ayarlayın.

## Adım 5: Resim SDT'lerini değiştirin

Resim SDT'sindeki bir görüntüyü güncellemek için mevcut görüntüyü yenisiyle değiştirebilirsiniz.

```csharp
if (sdt.SdtType == SdtType.Picture)
{
    Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
}
```

 Açıklama: Bu kod, şeklin bir görüntü içerip içermediğini kontrol eder ve ardından onu, şu konumda bulunan yeni bir görüntüyle değiştirir:`ImagesDir`.

## Adım 6: Değiştirilen Belgenizi Kaydedin

Gerekli tüm değişiklikleri yaptıktan sonra, orijinal belgenizi olduğu gibi korumak için değiştirilen belgeyi yeni bir adla kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

Açıklama: Bu, belgeyi yeni bir dosya adıyla kaydeder, böylece onu orijinalinden kolayca ayırt edebilirsiniz.

## Çözüm

İlgili adımları anladıktan sonra Aspose.Words for .NET kullanarak bir Word belgesindeki içerik kontrollerini değiştirmek çok kolaydır. İster metni güncelliyor, ister açılır menüleri değiştiriyor, ister görselleri değiştiriyor olun, Aspose.Words bu görevler için güçlü bir API sağlar. Bu öğreticiyi takip ederek belgenizin yapılandırılmış içerik kontrollerini etkili bir şekilde yönetebilir ve özelleştirebilir, belgelerinizi daha dinamik ve ihtiyaçlarınıza göre uyarlanmış hale getirebilirsiniz.

## SSS

1. Yapılandırılmış Belge Etiketi (SDT) nedir?

SDT'ler, Word belgelerindeki metin kutuları, açılır listeler veya resimler gibi belge içeriğini yönetmeye ve biçimlendirmeye yardımcı olan öğelerdir.

2. Bir SDT'ye nasıl yeni bir açılır öğe ekleyebilirim?

 Yeni bir öğe eklemek için şunu kullanın:`ListItems` özellik ve yeni bir özellik ekleyin`SdtListItem` koleksiyona.

3. Bir belgeden SDT'leri kaldırmak için Aspose.Words'ü kullanabilir miyim?

Evet, belgenin düğümlerine erişip istediğiniz SDT'yi silerek SDT'leri kaldırabilirsiniz.

4. Diğer öğelerin içine yerleştirilmiş SDT'leri nasıl işleyebilirim?

 Kullanın`GetChildNodes` iç içe SDT'lere erişmek için uygun parametrelere sahip yöntem.

5. Değiştirmem gereken SDT belgede görünmüyorsa ne yapmalıyım?

SDT'nin gizli olmadığından veya korunmadığından emin olun. Belge ayarlarını kontrol edin ve kodunuzun SDT türünü doğru şekilde hedeflediğinden emin olun.


### Aspose.Words for .NET kullanarak İçerik Kontrollerini Değiştirmek için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
	switch (sdt.SdtType)
	{
		case SdtType.PlainText:
		{
			sdt.RemoveAllChildren();
			Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
			Run run = new Run(doc, "new text goes here");
			para.AppendChild(run);
			break;
		}
		case SdtType.DropDownList:
		{
			SdtListItem secondItem = sdt.ListItems[2];
			sdt.ListItems.SelectedValue = secondItem;
			break;
		}
		case SdtType.Picture:
		{
			Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
			if (shape.HasImage)
			{
				shape.ImageData.SetImage(ImagesDir + "Watermark.png");
			}
			break;
		}
	}
}
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

İşte bu! Aspose.Words for .NET'i kullanarak Word belgenizdeki farklı içerik kontrol türlerini başarıyla değiştirdiniz.