---
title: Word Belgesi Yapısını PDF Belgesine Aktarma
linktitle: Word Belgesi Yapısını PDF Belgesine Aktarma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word Belgesi Yapısını PDF Belgesine Aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/export-document-structure/
---

Bu makale, Aspose.Words for .NET ile Word Belgesi Yapısını PDF Belgesine Dışa Aktar özelliğinin nasıl kullanılacağı hakkında adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgenin yapısını nasıl dışa aktaracağınızı ve belgenin yapısının görünür olduğu bir PDF oluşturmayı anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için belgelerinizin bulunduğu dizinin yolunu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Daha sonra işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte belgenin "Paragraphs.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## 3. Adım: PDF olarak kaydetme seçeneklerini yapılandırın

 PDF dosyasını düzenlerken belge yapısını dışa aktarmak ve yapıyı Adobe Acrobat Pro'nun "İçerik" gezinme bölmesinde görünür kılmak için,`PdfSaveOptions` ile nesne`ExportDocumentStructure` özellik şu şekilde ayarlandı:`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Adım 4: Belgeyi, belge yapısıyla PDF olarak kaydedin

Son olarak daha önce yapılandırdığımız kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET'i kullanarak bir belge yapısını başarıyla dışa aktardınız ve belge yapısının görünür olduğu bir PDF oluşturdunuz.

### Aspose.Words for .NET ile belge yapısını dışa aktarmak için örnek kaynak kodu


```csharp

            // Belgeler dizininin yolu.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // Dosya boyutu artırılacak ve yapı "İçerik" gezinme bölmesinde görünecek
            // Adobe Acrobat Pro'nun .pdf dosyasını düzenlerken.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinin yapısının PDF belgesine nasıl aktarılacağını açıkladık. Özetlenen adımları izleyerek, belge yapınızın görünür olduğu bir PDF'yi kolayca oluşturabilir, böylece belgede gezinmeyi ve arama yapmayı kolaylaştırabilirsiniz. Aspose.Words for .NET'in özelliklerini kullanarak Word belgelerinizin yapısını dışa aktarın ve iyi yapılandırılmış PDF'ler oluşturun.

### Sıkça Sorulan Sorular

#### S: Bir Word belgesinin yapısını PDF belgesine aktarmak nedir?
C: Bir Word belgesinin yapısını PDF belgesine aktarmak, görünür belge yapısına sahip bir PDF oluşturur. Belge yapısı genellikle başlıklar, bölümler, paragraflar ve belgenin diğer yapılandırılmış öğelerini içerir. Bu yapı, PDF belgesinde gezinme ve arama yapmak için yararlı olabilir.

#### S: Aspose.Words for .NET'i kullanarak bir Word belgesinin yapısını PDF belgesine nasıl aktarabilirim?
C: Aspose.Words for .NET kullanarak bir Word belgesinin yapısını PDF belgesine aktarmak için şu adımları izleyin:

 Bir örneğini oluşturun`Document` Word belgesinin yolunu belirten sınıf.

 Bir örneğini oluşturun`PdfSaveOptions` sınıfı seçin ve ayarlayın`ExportDocumentStructure`mülkiyet`true`. Bu, belge yapısını dışa aktaracak ve PDF dosyasını düzenlerken Adobe Acrobat Pro'nun "İçerik" gezinme bölmesinde görünür hale getirecektir.

 Kullan`Save` yöntemi`Document`Kaydetme seçeneklerini belirterek belgeyi PDF formatında kaydetmek için sınıf.

#### S: Adobe Acrobat Pro ile bir PDF belgesinin yapısını nasıl görüntüleyebilirim?
C: Bir PDF belgesinin yapısını Adobe Acrobat Pro ile görüntülemek için şu adımları izleyin:

PDF belgesini Adobe Acrobat Pro'da açın.

Sol gezinme çubuğunda, "İçerik" gezinme bölmesini görüntülemek için "İçerik" simgesini tıklayın.

"İçerik" gezinme bölmesinde, başlıklar, bölümler ve diğer yapılandırılmış öğelerle birlikte belge yapısını göreceksiniz.