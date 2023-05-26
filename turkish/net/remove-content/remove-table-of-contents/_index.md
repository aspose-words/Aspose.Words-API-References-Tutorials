---
title: İçindekiler Tablosunu Kaldır
linktitle: İçindekiler Tablosunu Kaldır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesinden içindekileri nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/remove-content/remove-table-of-contents/
---

Bu öğreticide, .NET için Aspose.Words kitaplığını kullanarak bir Word belgesinden içindekiler tablosunu nasıl kaldıracağınızı anlatacağız. İçindekiler tablosu bazen gereksiz veya gereksiz olabilir ve bu kod, onu etkili bir şekilde kaldırmanıza yardımcı olacaktır. Kodu anlamanıza ve kendi .NET projenizde uygulamanıza yardımcı olacak adım adım bir kılavuz sağlayacağız.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı
- Silmek istediğiniz içindekiler tablosunu içeren bir Word belgesi

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin
 Ardından, Word belgesini bir örneğine yükleyeceğiz.`Document` kullanarak sınıf`Load` yöntem.

```csharp
//belgeyi yükle
Document doc = new Document(dataDir + "your-document.docx");
```

## 3. Adım: İçindekiler tablosunu silin
 İçindekiler tablosunu kaldırmak için, içindekiler (içindekiler tablosu) türünden geçeceğiz`FieldStart` belgedeki düğümler. Bu düğümleri hızlı bir şekilde erişebilmemiz ve silinecek düğümlerin bir listesini oluşturabilmemiz için saklayacağız.

```csharp
// Hızlı erişim için içindekiler alanlarının FieldStart düğümlerini belgede saklayın.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Bu, belirtilen TOC içinde bulunan düğümleri depolamak için bir listedir. Bu yöntemin sonunda silinecekler.
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
     // Bu düğümleri depolamak ve sonunda hepsini silmek daha güvenlidir.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // FieldTOC türünde bir FieldEnd düğümüyle karşılaştığımızda,
     // mevcut TOK'un sonunda olduğumuzu biliyoruz ve burada duruyoruz.
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

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
//belgeyi yükle
Document doc = new Document(dataDir + "your-document.docx");

// Hızlı erişim için içindekiler alanlarının FieldStart düğümlerini belgede saklayın.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Bu, belirtilen TOC içinde bulunan düğümleri depolamak için bir listedir. Bu yöntemin sonunda kaldırılacaklar.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Geçirilen dizin tarafından belirtilen TOC'nin var olduğundan emin olun.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Bu düğümleri saklamak ve daha sonra hepsini birden silmek daha güvenlidir.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// FieldTOC türünde bir FieldEnd düğümüyle karşılaştığımızda,
	// mevcut TOK'un sonunda olduğumuzu biliyoruz ve burada duruyoruz.
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
Bu öğreticide, .NET için Aspose.Words kitaplığını kullanarak bir Word belgesinden içindekiler tablosunu kaldırmak için adım adım bir kılavuz sunduk. Sağlanan kodu ve yönergeleri izleyerek içindekiler tablosunu kolayca ortadan kaldırabilir ve belgenizin düzenini iyileştirebilirsiniz. Dizin yolunu ve dosya adlarını özel ihtiyaçlarınıza göre uyarlamayı unutmayın.