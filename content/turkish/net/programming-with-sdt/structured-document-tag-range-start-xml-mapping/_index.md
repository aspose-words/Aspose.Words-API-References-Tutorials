---
title: Yapılandırılmış Belge Etiket Aralığı Xml Eşlemesini Başlat
linktitle: Yapılandırılmış Belge Etiket Aralığı Xml Eşlemesini Başlat
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak XML verilerini Word'deki yapılandırılmış belge etiketlerine dinamik olarak nasıl bağlayacağınızı öğrenin. Adım adım kılavuzumuzu takip edin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---
## giriiş

Hiç XML verilerini bir Word belgesine dinamik olarak eklemek istediniz mi? Şanslısın! Aspose.Words for .NET bu görevi çok kolaylaştırıyor. Bu öğreticide, yapılandırılmış belge etiketi aralığı başlangıç XML eşlemesinin derinliklerine iniyoruz. Bu özellik, özel XML parçalarını içerik kontrollerine bağlamanıza olanak tanıyarak belge içeriğinizin XML verilerinizle sorunsuz bir şekilde güncellenmesini sağlar. Belgelerinizi dinamik şaheserlere dönüştürmeye hazır.

## Önkoşullar

Kodlama kısmına geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET Library: En son sürüme sahip olduğunuzdan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya C#'ı destekleyen başka bir IDE.
3. Temel C# Bilgisi: C# programlamaya aşinalık şarttır.
4. Word Belgesi: Üzerinde çalışılacak örnek bir Word belgesi.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu, Aspose.Words for .NET'te gerekli tüm sınıflara ve yöntemlere erişebilmemizi sağlayacaktır.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using System.Text;
```

## 1. Adım: Belge Dizininizi Kurun

Her projenin bir temele ihtiyacı vardır, değil mi? Burada belge dizininizin yolunu ayarlıyoruz.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Word Belgesini Yükleyin

Daha sonra Word belgesini yüklüyoruz. Bu, XML verilerimizi ekleyeceğimiz belgedir.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
```

## 3. Adım: Özel XML Parçası Ekleme

Eklemek istediğimiz verileri içeren bir XML bölümü oluşturup bunu belgenin CustomXmlPart koleksiyonuna eklememiz gerekiyor. Bu özel XML bölümü, yapılandırılmış belge etiketlerimiz için veri kaynağı görevi görecektir.

### XML Parçası Oluşturma

Öncelikle XML kısmı için benzersiz bir kimlik oluşturun ve içeriğini tanımlayın.

```csharp
// Veri içeren bir XML parçası oluşturun ve bunu belgenin CustomXmlPart koleksiyonuna ekleyin.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

### XML Parçası İçeriğini Doğrulayın

XML kısmının doğru şekilde eklendiğinden emin olmak için içeriğini yazdırıyoruz.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
```

## 4. Adım: Yapılandırılmış Belge Etiketi Oluşturun

Yapılandırılmış Belge Etiketi (SDT), bir XML bölümüne bağlanabilen bir içerik kontrolüdür. Burada özel XML bölümümüzün içeriğini görüntüleyecek bir SDT oluşturuyoruz.

Öncelikle belgedeki SDT aralığı başlangıcını bulun.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
```

## Adım 5: SDT için XML Eşlemesini Ayarlayın

Şimdi sıra XML parçamızı SDT'ye bağlamaya geldi. Bir XML eşleme ayarlayarak, XML verilerinin hangi bölümünün SDT'de görüntülenmesi gerektiğini belirleriz.

 XPath, XML bölümünde görüntülemek istediğimiz belirli öğeye işaret eder. Burada ikinciye işaret ediyoruz.`<text>` içindeki eleman`<root>` eleman.

```csharp
// StructuredDocumentTag'imiz için bir eşleme ayarlayın
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Adım 6: Belgeyi Kaydedin

Son olarak, değişiklikleri çalışırken görmek için belgeyi kaydedin. Word belgesindeki SDT artık belirtilen XML içeriğini görüntüleyecektir.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir XML parçasını bir Word belgesindeki yapılandırılmış belge etiketine başarıyla eşlediniz. Bu güçlü özellik, dinamik ve veri odaklı belgeleri zahmetsizce oluşturmanıza olanak tanır. İster rapor, ister fatura, ister başka bir belge türü oluşturuyor olun, XML eşleme iş akışınızı önemli ölçüde kolaylaştırabilir.

## SSS'ler

### Word'de yapılandırılmış belge etiketi nedir?
İçerik denetimleri olarak da bilinen yapılandırılmış belge etiketleri, Word belgelerindeki belirli içerik türlerine yönelik kaplardır. Verileri bağlamak, düzenlemeyi kısıtlamak veya belge oluşturmada kullanıcılara rehberlik etmek için kullanılabilirler.

### XML parçası içeriğini dinamik olarak nasıl güncelleyebilirim?
 XML bölümünün içeriğini değiştirerek güncelleyebilirsiniz.`xmlPartContent` belgeye eklemeden önce dize. Basitçe dizeyi yeni verilerle güncelleyin ve`CustomXmlParts` koleksiyon.

### Aynı belgede birden fazla XML parçasını farklı SDT'lere bağlayabilir miyim?
Evet, aynı belgede birden fazla XML parçasını farklı SDT'lere bağlayabilirsiniz. Her SDT'nin kendine özgü XML bölümü ve XPath eşlemesi olabilir.

### Karmaşık XML yapılarını SDT'lerle eşlemek mümkün müdür?
Kesinlikle! XML bölümünde istenen öğeleri doğru bir şekilde işaret eden ayrıntılı XPath ifadelerini kullanarak karmaşık XML yapılarını SDT'lerle eşleyebilirsiniz.

### Bir XML bölümünü bir belgeden nasıl kaldırabilirim?
 Bir XML bölümünü aşağıdaki komutu çağırarak kaldırabilirsiniz:`Remove` konusundaki yöntem`CustomXmlParts` toplama, geçme`xmlPartId` Kaldırmak istediğiniz XML bölümünün.