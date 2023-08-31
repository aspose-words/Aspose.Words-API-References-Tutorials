---
title: Word Belgesindeki İçindekiler Tablosunu Kaldırma
linktitle: Word Belgesindeki İçindekiler Tablosunu Kaldırma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesindeki içindekiler tablosunu nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/remove-content/remove-table-of-contents/
---
Bu eğitimde, .NET için Aspose.Words kütüphanesini kullanarak bir Word belgesindeki içindekiler tablosunu nasıl kaldıracağınız konusunda size yol göstereceğiz. İçindekiler tablosu bazen gereksiz veya gereksiz olabilir ve bu kod onu etkili bir şekilde kaldırmanıza yardımcı olacaktır. Kodu anlamanıza ve kendi .NET projenizde uygulamanıza yardımcı olacak adım adım bir kılavuz sağlayacağız.

## Önkoşullar
Başlamadan önce aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- .NET için Aspose.Words kütüphanesi projenizde yüklü
- Silmek istediğiniz içindekiler tablosunu içeren bir Word belgesi

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, Word belgenizin konumuna giden dizin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin
 Daha sonra, Word belgesini bir örneğine yükleyeceğiz.`Document` kullanarak sınıf`Load` yöntem.

```csharp
// Belgeyi yükleyin
Document doc = new Document(dataDir + "your-document.docx");
```

## 3. Adım: İçindekiler tablosunu silin
 İçindekiler tablosunu kaldırmak için TOC (içindekiler tablosu) türü üzerinden döngü yapacağız`FieldStart` belgedeki düğümler. Bu düğümleri saklayacağız, böylece onlara hızlı bir şekilde erişebilir ve silinecek düğümlerin bir listesini oluşturabiliriz.

```csharp
// Hızlı erişim için TOC alanlarının FieldStart düğümlerini belgede saklayın.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Bu, belirtilen TOC içinde bulunan düğümleri saklayan bir listedir. Bu yöntemin sonunda silinecekler.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Belirtilen TOC indeksinin mevcut olup olmadığını kontrol edin.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Bu düğümleri saklamak ve sonunda hepsini silmek daha güvenlidir.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // FieldTOC türünde bir FieldEnd düğümüyle karşılaştığımızda,
     //Mevcut TOC'nin sonunda olduğumuzu biliyoruz ve burada duruyoruz.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Aspose.Words for .NET kullanarak İçindekiler Tablosunu Kaldırmak için örnek kaynak kodu 
```csharp

//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Belgeyi yükleyin
Document doc = new Document(dataDir + "your-document.docx");

// Hızlı erişim için TOC alanlarının FieldStart düğümlerini belgede saklayın.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Bu, belirtilen TOC içinde bulunan düğümleri saklayan bir listedir. Bu yöntemin sonunda kaldırılacaklardır.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// İletilen dizin tarafından belirtilen TOC'nin mevcut olduğundan emin olun.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Bu düğümleri saklamak ve daha sonra hepsini bir kerede silmek daha güvenlidir.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// FieldTOC türünde bir FieldEnd düğümüyle karşılaştığımızda,
	// Mevcut TOC'nin sonunda olduğumuzu biliyoruz ve burada duruyoruz.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Çözüm
Bu eğitimde, .NET için Aspose.Words kütüphanesini kullanarak içindekiler tablosunu bir Word belgesinden kaldırmak için adım adım bir kılavuz sunduk. Sağlanan kodu ve talimatları izleyerek içindekiler tablosunu kolayca ortadan kaldırabilir ve belgenizin düzenini iyileştirebilirsiniz. Dizin yolunu ve dosya adlarını özel ihtiyaçlarınıza göre uyarlamayı unutmayın.

### SSS'ler

#### S: Bir Word belgesindeki içindekiler tablosunu kaldırmak için neden Aspose.Words kullanmalıyım?

C: Aspose.Words, .NET uygulamalarında Word belgelerini düzenlemek için kullanılan güçlü ve çok yönlü bir sınıf kütüphanesidir. Aspose.Words'ü kullanarak içindekiler tablosunu belgelerinizden etkili bir şekilde kaldırabilirsiniz; bu, içindekiler tablosunun gereksiz veya gereksiz olduğu durumlarda yararlı olabilir. Bu, belgenizin içeriğini özelleştirmenize ve genel sunumunu iyileştirmenize olanak tanır.

#### S: Aspose.Words for .NET'e nasıl belge yüklerim?

C: Bir Word belgesindeki içindekiler tablosunu kaldırmak için, önce Aspose.Words'ün Load() yöntemini kullanarak belgeyi belleğe yüklemelisiniz. Belirli bir dizinden belge yüklemek için örnek kod:

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "your-document.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin gerçek yolu ile.

#### S: Aspose.Words kullanarak bir belgedeki içindekiler kısmını nasıl kaldırabilirim?

 C: İçindekiler Tablosunu kaldırmak için, işlemi yinelemeniz gerekir.`FieldStart` belgedeki TOC düğümlerini yazın. Hızlı erişim için bu düğümleri saklayabilir ve silinecek düğümlerin bir listesini oluşturabilirsiniz. İşte örnek bir kod:

```csharp
// Hızlı erişim için TOC alanlarının FieldStart düğümlerini belgede saklayın.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Bu, belirtilen TOC içinde bulunan düğümleri depolamak için kullanılan bir listedir. Bu yöntemin sonunda silinecekler.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Belirtilen içindekiler dizininin mevcut olup olmadığını kontrol edin.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Bu düğümleri saklamak ve sonunda hepsini silmek daha güvenlidir.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// FieldTOC türünde bir FieldEnd düğümüyle karşılaştığımızda,
//Mevcut TOC'nin sonunda olduğumuzu biliyoruz ve burada duruyoruz.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### S: Düzenlenen belge Aspose.Words for .NET'te nasıl kaydedilir?

C: İçindekiler tablosunu sildikten sonra, değiştirilen belgeyi Save() yöntemini kullanarak kaydetmelisiniz. Düzenlenen belge için istenen çıktı dosyası yolunu ve biçimini (örneğin, DOCX) belirtin. İşte örnek bir kod:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```