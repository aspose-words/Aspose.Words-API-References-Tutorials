---
title: Sayfa Aralığına Göre
linktitle: Sayfa Aralığına Göre
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET Adım adım kılavuzunu kullanarak bir Word belgesinden sayfa aralığına göre kolayca ayıklayın.
type: docs
weight: 10
url: /tr/net/split-document/by-page-range/
---

## giriiş
Bu eğitimde, Aspose.Words for .NET'in "Sayfa Aralığına Göre" işlevini anlamanız ve kullanmanız için size adım adım rehberlik edeceğiz. Bu özellik, belirli bir sayfa aralığını kullanarak büyük bir Word belgesinin belirli bir bölümünü çıkarmanıza olanak tanır. Daha sonra anlamanızı ve kullanmanızı kolaylaştırmak için size eksiksiz kaynak kodu ve Markdown çıktı biçimleri sağlayacağız.

## Gereksinimler
Başlamadan önce, aşağıdakilerin yerinde olduğundan emin olun:

1. Geliştirme makinenizde kurulu Aspose.Words for .NET.
2. Belirli bir bölümünü ayıklamak istediğiniz büyük bir Word dosyası.

Artık gereksinimleri ele aldığımıza göre, Sayfa Aralığına Göre özelliğini kullanma adımlarına geçebiliriz.

## 1. Adım: Belge başlatma ve yükleme
Geliştirme ortamınızı kurduktan sonra, belirli bir bölümü çıkarmak istediğiniz Word belgesini başlatmanız ve yüklemeniz gerekir. İşte kullanılacak kod:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Name_of_large_document.docx");
```

"YOUR_DOCUMENTS_DIRECTORY" yerine belgeler dizininizin gerçek yolunu ve "Name_of_large_document.docx" yerine büyük Word dosyanızın adını yazdığınızdan emin olun.

## 2. Adım: Belgenin bir kısmını çıkarma
 Artık belgeyi yüklediğimize göre, belirli kısmı kullanarak çıkartabiliriz.`ExtractPages` istenen sayfa aralığında çalışır. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
Document extractedPages = doc.ExtractPages(3, 6);
```

Bu örnekte, orijinal belgeden 3-6. sayfaları çıkarıyoruz. Sayfa numaralarını ihtiyaçlarınıza göre ayarlayabilirsiniz.

## 3. Adım: Çıkarılan parçayı kaydedin
İstenen sayfaları çıkardıktan sonra, onları yeni bir Word belgesine kaydedebiliriz. İşte nasıl:

```csharp
extractedPages.Save(dataDir + "Document_Extraits.ParRangeDePages.docx");
```

Çıktı dosyanız için "Document_Extraits.ParPlageDePages.docx" öğesini istediğiniz adla değiştirdiğinizden emin olun.

### Aspose.Words for .NET kullanan By Page Range için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

// Belgenin bir parçasını alın.
Document extractedPages = doc.ExtractPages(3, 6);
extractedPages.Save(dataDir + "SplitDocument.ByPageRange.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET'ten "Sayfa Aralığına Göre"nin nasıl kullanılacağını öğrendiniz. Artık belirli bir sayfa aralığını kullanarak büyük bir Word belgesinin belirli bölümlerini kolayca çıkarabilirsiniz. Aspose'un diğer güçlü özellikleriyle daha fazlasını denemekten çekinmeyin. .Özel ihtiyaçlarınızı karşılayacak kelimeler.

