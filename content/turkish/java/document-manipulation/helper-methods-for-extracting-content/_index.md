---
title: Aspose.Words for Java'da İçerik Çıkarmada Yardımcı Yöntemler
linktitle: İçerik Çıkarmaya İlişkin Yardımcı Yöntemler
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'yı kullanarak Word belgelerinden içeriği verimli bir şekilde nasıl çıkaracağınızı öğrenin. Bu kapsamlı kılavuzda yardımcı yöntemleri, özel biçimlendirmeyi ve daha fazlasını keşfedin.
type: docs
weight: 14
url: /tr/java/document-manipulation/helper-methods-for-extracting-content/
---

## Aspose.Words for Java'da İçerik Çıkarmaya Yönelik Yardımcı Yöntemlere Giriş

Aspose.Words for Java, geliştiricilerin Word belgeleriyle programlı olarak çalışmasına olanak tanıyan güçlü bir kütüphanedir. Word belgeleriyle çalışırken ortak görevlerden biri, onlardan içerik çıkarmaktır. Bu makalede, Aspose.Words for Java'yı kullanarak verimli bir şekilde içerik çıkarmak için bazı yardımcı yöntemleri inceleyeceğiz.

## Önkoşullar

Kod örneklerine dalmadan önce, Java projenizde Aspose.Words for Java'nın kurulu ve kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/java/).

## Yardımcı Yöntem 1: Paragrafları Stile Göre Çıkarma

```java
public static ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    // Belirtilen stildeki paragrafları toplamak için bir dizi oluşturun.
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);

    // Belirtilen stile sahip olanları bulmak için tüm paragraflara bakın.
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}
```

Word belgenizde belirli bir stile sahip paragrafları çıkarmak için bu yöntemi kullanabilirsiniz. Bu, başlıklar veya blok alıntılar gibi belirli bir biçimlendirmeye sahip içeriği çıkarmak istediğinizde kullanışlıdır.

## Yardımcı Yöntem 2: İçeriği Düğümlere Göre Çıkarma

```java
public static ArrayList<Node> extractContentBetweenNodes(Node startNode, Node endNode, boolean isInclusive) {
    // Öncelikle bu yönteme iletilen düğümlerin kullanım için geçerli olup olmadığını kontrol edin.
    verifyParameterNodes(startNode, endNode);
    
    // Çıkarılan düğümleri depolamak için bir liste oluşturun.
    ArrayList<Node> nodes = new ArrayList<Node>();

    // İşaretçilerden herhangi biri, yorumun kendisi de dahil olmak üzere bir yorumun parçasıysa işaretçiyi hareket ettirmemiz gerekir.
    // CommentRangeEnd düğümünden sonra bulunan Yorum Düğümüne iletin.
    if (endNode.getNodeType() == NodeType.COMMENT_RANGE_END && isInclusive) {
        Node node = findNextNode(NodeType.COMMENT, endNode.getNextSibling());
        if (node != null)
            endNode = node;
    }
    
    // Gerekirse işaretleyici düğümleri bölmek için bu yönteme iletilen orijinal düğümlerin kaydını tutun.
    Node originalStartNode = startNode;
    Node originalEndNode = endNode;

    //Blok düzeyindeki düğümlere (paragraflar ve tablolar) dayalı olarak içerik çıkarın. Onları bulmak için ana düğümler arasında geçiş yapın.
    // İşaretleyici düğümlerin satır içi olup olmamasına bağlı olarak ilk ve son düğümlerin içeriğini böleceğiz.
    startNode = getAncestorInBody(startNode);
    endNode = getAncestorInBody(endNode);
    boolean isExtracting = true;
    boolean isStartingNode = true;
    // Belgeden çıkardığımız geçerli düğüm.
    Node currNode = startNode;

    // İçerik çıkarmaya başlayın. Tüm blok düzeyindeki düğümleri işleyin ve özellikle ilkini bölün
    // ve gerektiğinde son düğümler, böylece paragraf biçimlendirmesi korunur.
    // Bu yöntem normal bir çıkarıcıdan biraz daha karmaşıktır çünkü faktöre ihtiyacımız var
    // Yararlı kılmak için satır içi düğümleri, alanları, yer imlerini vb. kullanarak ayıklama yaparken.
    while (isExtracting) {
        // Bir kopya elde etmek için geçerli düğümü ve alt öğelerini klonlayın.
        Node cloneNode = currNode.deepClone(true);
        boolean isEndingNode = currNode.equals(endNode);
        if (isStartingNode || isEndingNode) {
            // Her işaretçiyi ayrı ayrı işlememiz gerekiyor, bu nedenle onu ayrı bir yönteme aktarın.
            // Düğüm indekslerini korumak için ilk önce End işlenmelidir.
            if (isEndingNode) {
                // !isStartingNode: işaretçiler aynı düğümse düğümü iki kez eklemeyin.
                processMarker(cloneNode, nodes, originalEndNode, currNode, isInclusive,
                        false, !isStartingNode, false);
                isExtracting = false;
            }
            //Blok düzeyindeki başlangıç ve bitiş işaretçileri aynı düğüm olabileceğinden koşulun ayrı olması gerekir.
            if (isStartingNode) {
                processMarker(cloneNode, nodes, originalStartNode, currNode, isInclusive,
                        true, true, false);
                isStartingNode = false;
            }
        } else
            // Düğüm bir başlangıç veya bitiş işaretçisi değildir; kopyayı listeye eklemeniz yeterlidir.
            nodes.add(cloneNode);

        // Bir sonraki düğüme geçin ve onu çıkarın. Bir sonraki düğüm boşsa,
        // İçeriğin geri kalanı farklı bir bölümde bulunur.
        if (currNode.getNextSibling() == null && isExtracting) {
            // Bir sonraki bölüme geçin.
            Section nextSection = (Section) currNode.getAncestor(NodeType.SECTION).getNextSibling();
            currNode = nextSection.getBody().getFirstChild();
        } else {
            // Vücuttaki bir sonraki düğüme geçin.
            currNode = currNode.getNextSibling();
        }
    }

    // Satır içi yer imleri içeren modla uyumluluk için sonraki paragrafı (boş) ekleyin.
    if (isInclusive && originalEndNode == endNode && !originalEndNode.isComposite())
        includeNextParagraph(endNode, nodes);

    // Düğüm işaretçileri arasındaki düğümleri döndürün.
    return nodes;
}
```

Bu yöntem, ister paragraf, ister tablo, ister başka herhangi bir blok düzeyindeki öğe olsun, belirtilen iki düğüm arasındaki içeriği çıkarmanıza olanak tanır. Satır içi işaretçiler, alanlar ve yer imleri dahil olmak üzere çeşitli senaryoları yönetir.

## Yardımcı Yöntem 3: Yeni Bir Belge Oluşturma

```java
public static Document generateDocument(Document srcDoc, ArrayList<Node> nodes) throws Exception {
    Document dstDoc = new Document();
    
    // Boş belgeden ilk paragrafı kaldırın.
    dstDoc.getFirstSection().getBody().removeAllChildren();
    
    // Listedeki her düğümü yeni belgeye aktarın. Düğümün orijinal formatını koruyun.
    NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
    for (Node node : nodes) {
        Node importNode = importer.importNode(node, true);
        dstDoc.getFirstSection().getBody().appendChild(importNode);
    }
    
    return dstDoc;
}
```

Bu yöntem, kaynak belgeden düğümlerin bir listesini içe aktararak yeni bir belge oluşturmanıza olanak tanır. Düğümlerin orijinal formatını koruyarak, belirli içeriğe sahip yeni belgeler oluşturmak için kullanışlı olmasını sağlar.

## Çözüm

Word belgelerinden içerik çıkarmak, birçok belge işleme görevinin önemli bir parçası olabilir. Aspose.Words for Java, bu süreci kolaylaştıran güçlü yardımcı yöntemler sağlar. Paragrafları stile, düğümler arasındaki içeriğe göre ayıklamanız veya yeni belgeler oluşturmanız gerekiyorsa, bu yöntemler Java uygulamalarınızda Word belgeleriyle verimli bir şekilde çalışmanıza yardımcı olacaktır.

## SSS'ler

### Aspose.Words for Java'yı nasıl kurabilirim?

 Aspose.Words for Java'yı yüklemek için Aspose web sitesinden indirebilirsiniz. Ziyaret etmek[Burada](https://releases.aspose.com/words/java/) En son sürümü almak için.

### Bir Word belgesinin belirli bölümlerinden içerik çıkarabilir miyim?

Evet, bu makalede bahsedilen yöntemleri kullanarak bir Word belgesinin belirli bölümlerinden içerik çıkarabilirsiniz. Çıkarmak istediğiniz bölümü tanımlayan başlangıç ve bitiş düğümlerini belirtmeniz yeterlidir.

### Aspose.Words for Java, Java 11 ile uyumlu mu?

Evet, Aspose.Words for Java, Java 11 ve üzeri sürümlerle uyumludur. Java uygulamalarınızda sorunsuzca kullanabilirsiniz.

### Çıkarılan içeriğin formatını özelleştirebilir miyim?

Evet, oluşturulan belgedeki içe aktarılan düğümleri değiştirerek çıkarılan içeriğin biçimlendirmesini özelleştirebilirsiniz. Aspose.Words for Java ihtiyaçlarınızı karşılamak için kapsamlı biçimlendirme seçenekleri sunar.

### Aspose.Words for Java için daha fazla belge ve örneği nerede bulabilirim?

 Aspose web sitesinde Aspose.Words for Java ile ilgili kapsamlı belgeler ve örnekler bulabilirsiniz. Ziyaret etmek[https://reference.aspose.com/words/java/](https://reference.aspose.com/words/java/) ayrıntılı belgeler ve kaynaklar için.