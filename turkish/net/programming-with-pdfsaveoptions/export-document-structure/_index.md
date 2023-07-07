---
title: Word Belge Yapısını PDF Belgesine Aktar
linktitle: Word Belge Yapısını PDF Belgesine Aktar
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Word Belge Yapısını PDF Belgesine Aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/export-document-structure/
---

Bu makale, Word Belge Yapısını PDF Belgesine Aktar özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgenin yapısını nasıl dışa aktaracağınızı ve belgenin yapısı görünür şekilde bir PDF oluşturmayı öğrenebileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Ardından, işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte, belgenin "Paragraphs.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## 3. Adım: PDF olarak kaydetme seçeneklerini yapılandırın

 PDF dosyasını düzenlerken belge yapısını dışa aktarmak ve yapıyı Adobe Acrobat Pro'nun "İçerik" gezinme bölmesinde görünür kılmak için,`PdfSaveOptions` ile nesne`ExportDocumentStructure` özellik ayarlandı`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## 4. Adım: Belgeyi, belge yapısıyla PDF olarak kaydedin

Son olarak, daha önce yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Bu kadar ! Bir belge yapısını başarıyla dışa aktardınız ve Aspose.Words for .NET kullanarak belge yapısının görünür olduğu bir PDF oluşturdunuz.

### Aspose.Words for .NET ile belge yapısını dışa aktarmak için örnek kaynak kodu


```csharp

            // Belgeler dizininin yolu.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // Dosya boyutu artırılacak ve yapı "İçerik" gezinme bölmesinde görünür olacak
            // .pdf dosyasını düzenlerken Adobe Acrobat Pro'nun
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Çözüm

Bu eğitimde, bir Word belgesinin yapısının Aspose.Words for .NET kullanılarak bir PDF belgesine nasıl aktarılacağını açıkladık. Ana hatlarıyla belirtilen adımları izleyerek, belge yapınızın görünür olduğu bir PDF'i kolayca oluşturabilir ve belgede gezinmeyi ve arama yapmayı kolaylaştırabilirsiniz. Word belgelerinizin yapısını dışa aktarmak ve iyi yapılandırılmış PDF'ler oluşturmak için Aspose.Words for .NET'in özelliklerini kullanın.

### Sıkça Sorulan Sorular

#### S: Bir Word belgesinin yapısını bir PDF belgesine dışa aktarmak nedir?
Y: Bir Word belgesinin yapısını bir PDF belgesine dışa aktarmak, görünür bir belge yapısına sahip bir PDF oluşturur. Belge yapısı genellikle başlıklar, bölümler, paragraflar ve belgenin diğer yapılandırılmış öğelerini içerir. Bu yapı, PDF belgesinde gezinmek ve arama yapmak için yararlı olabilir.

#### S: Aspose.Words for .NET kullanarak bir Word belgesinin yapısını bir PDF belgesine nasıl aktarabilirim?
C: Aspose.Words for .NET kullanarak bir Word belgesinin yapısını bir PDF belgesine dışa aktarmak için şu adımları izleyin:

 örneğini oluşturun`Document` Word belgesine giden yolu belirten sınıf.

 örneğini oluşturun`PdfSaveOptions` sınıflandırın ve ayarlayın`ExportDocumentStructure` mülkiyet`true`. Bu, belge yapısını dışa aktaracak ve PDF dosyasını düzenlerken Adobe Acrobat Pro'nun "İçerik" gezinme bölmesinde görünmesini sağlayacaktır.

 Kullan`Save` yöntemi`Document`kaydetme seçeneklerini belirterek belgeyi PDF biçiminde kaydetmek için sınıf.

#### S: Adobe Acrobat Pro ile bir PDF belgesinin yapısını nasıl görüntüleyebilirim?
C: Bir PDF belgesinin yapısını Adobe Acrobat Pro ile görüntülemek için şu adımları izleyin:

PDF belgesini Adobe Acrobat Pro'da açın.

Sol gezinme çubuğunda, "İçerik" gezinme bölmesini görüntülemek için "İçerik" simgesini tıklayın.

"İçerik" gezinme bölmesinde, başlıklar, bölümler ve diğer yapılandırılmış öğelerle birlikte belge yapısını göreceksiniz.