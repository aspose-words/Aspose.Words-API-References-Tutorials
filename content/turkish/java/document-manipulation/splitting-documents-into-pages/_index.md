---
title: Aspose.Words for Java'da Belgeleri Sayfalara Bölme
linktitle: Belgeleri Sayfalara Bölme
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java kullanarak belgeleri sayfalara nasıl böleceğinizi öğrenin. Verimli belge işleme için kaynak kodlu adım adım kılavuz.
type: docs
weight: 23
url: /tr/java/document-manipulation/splitting-documents-into-pages/
---

Java'da belge işlemeyle çalışıyorsanız Aspose.Words for Java, belgeleri verimli bir şekilde ayrı sayfalara bölmenize yardımcı olabilecek güçlü bir API'dir. Bu adım adım eğitimde, sağlanan kaynak kodunu kullanarak belgeleri bölme sürecinde size rehberlik edeceğiz. Bu eğitimin sonunda belgeleri kolaylıkla bölebilecek ve belge yönetimi becerilerinizi geliştirebileceksiniz.

## 1. Giriş

Aspose.Words for Java, Word belgelerini programlı olarak değiştirmenizi sağlayan bir Java kütüphanesidir. Yaygın görevlerden biri, bir belgeyi arşivleme, yazdırma veya belge işleme gibi çeşitli amaçlar için yararlı olabilecek ayrı sayfalara bölmektir.

## 2. Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
-  İndirebileceğiniz Aspose.Words for Java kütüphanesi[Burada](https://releases.aspose.com/words/java/).

## 3. Ortamınızı Kurmak

Başlamak için geliştirme ortamınızı aşağıdaki gibi ayarlayın:

- Tercih ettiğiniz Entegre Geliştirme Ortamında (IDE) bir Java projesi oluşturun.
- Aspose.Words for Java kütüphanesini projenize ekleyin. Şuraya başvurabilirsiniz:[dokümantasyon](https://reference.aspose.com/words/java/) ayrıntılı talimatlar için.

## 4. Kaynak Kodunu Anlamak

Sağladığınız kaynak kodu, bir belgeyi ayrı sayfalara bölmek için tasarlanmıştır. Temel bileşenleri parçalayalım:

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- Giriş belgesinin temel adını ve uzantısını çıkarıyoruz.
- Belgeyi Aspose.Words for Java kullanarak yüklüyoruz.

## 5. Belgeleri Adım Adım Bölme

### 5.1. Belgeyi Yükleme

```java
Document doc = new Document(docName);
```

 Bu adımda giriş belgesini bir dosyaya yüklüyoruz.`Document` belgenin içeriğiyle çalışmamızı sağlayan nesne.

### 5.2. DocumentPageSplitter'ı Başlatma

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

 Bir başlatıyoruz`DocumentPageSplitter` Yüklenen belgemizle nesne. Bu sınıf Aspose.Words for Java tarafından sağlanır ve belgeyi sayfalara bölmemize yardımcı olur.

### 5.3. Her Sayfayı Kaydetme

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

Bu adımda belgenin her sayfasını yineleyerek ayrı bir belge olarak kaydediyoruz. Bölünmüş sayfaların kaydedileceği dizin yolunu belirleyebilirsiniz.

## 6. Kodu Çalıştırma

Bu kodu başarıyla çalıştırmak için ortamınızı kurduğunuzdan ve Aspose.Words for Java kütüphanesini projenize eklediğinizden emin olun. Ardından kodu yürütün; belgenizin ayrı sayfalara bölünmesini sağlayın.

## DocumentPageSplitter Kaynak Kodu

```java
/// <özet>
/// Bir belgeyi her sayfada bir tane olacak şekilde birden çok belgeye böler.
/// </özet>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <özet>
/// <see cref="DocumentPageSplitter"/> sınıfının yeni bir örneğini başlatır.
/// Bu yöntem, her sayfanın bir bölüm sınırında başlayıp biteceği şekilde belgeyi bölümlere ayırır.
/// Daha sonra belgede değişiklik yapılmaması tavsiye edilir.
/// </özet>
/// <param name="source">Kaynak belge</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <özet>
/// Bir sayfanın belgesini alır.
/// </özet>
/// <param name = "pageIndex">
/// 1 tabanlı bir sayfa dizini.
/// </param>
/// <geri döner>
/// <see cref="Belge"/>.
/// </dönüş>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <özet>
/// Bir sayfa aralığının belgesini alır.
/// </özet>
//<param name = "startIndex">
/// 1 tabanlı başlangıç sayfasının dizini.
/// </param>
/// <param adı = "endIndex">
/// 1 tabanlı bitiş sayfasının dizini.
/// </param>
/// <geri döner>
/// <see cref="Belge"/>.
/// </dönüş>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <özet>
/// Belirli sayfalarda oluşturulan bir belgenin düğümlerini ayıklamak için yöntemler sağlar.
/// </özet>
class PageNumberFinder
{
// Düğümü başlangıç/bitiş sayfa numaralarıyla eşler.
// Bu, belge bölündüğünde toplayıcı tarafından sağlanan temel sayfa numaralarını geçersiz kılmak için kullanılır.
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
// Sayfa numarasını o sayfada bulunan düğümlerin listesiyle eşler.
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <özet>
/// <see cref="PageNumberFinder"/> sınıfının yeni bir örneğini başlatır.
/// </özet>
/// <param name="collector">Belge için düzen modeli kayıtlarını içeren bir toplayıcı örneği.</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <özet>
/// Düğümün başladığı sayfanın 1 tabanlı dizinini alır.
/// </özet>
/// <param adı = "düğüm">
/// Düğüm.
/// </param>
/// <geri döner>
/// Sayfa dizini.
/// </dönüş>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <özet>
/// Düğümün bittiği sayfanın 1 tabanlı dizinini alır.
/// </özet>
/// <param adı = "düğüm">
/// Düğüm.
/// </param>
/// <geri döner>
/// Sayfa dizini.
/// </dönüş>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <özet>
//Belirtilen düğümün kaç sayfaya yayıldığını döndürür. Düğüm bir sayfada yer alıyorsa 1 değerini döndürür.
/// </özet>
/// <param adı = "düğüm">
/// Düğüm.
/// </param>
/// <geri döner>
/// Sayfa dizini.
/// </dönüş>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <özet>
/// Belirtilen sayfanın veya belirtilen düğüm türüyle eşleşen sayfaların herhangi bir yerinde bulunan düğümlerin listesini döndürür.
/// </özet>
/// <param name="başlangıçSayfası">
/// Başlangıç Sayfası.
/// </param>
/// <param adı = "endPage">
/// Son Sayfa.
/// </param>
/// <param adı = "nodeType">
/// Düğüm Türü.
/// </param>
/// <geri döner>
/// <see cref="IList{T}"/>.
/// </dönüş>
public ArrayList<Node> retrieveAllNodesOnPages(int startPage, int endPage, /*NodeType*/int nodeType) throws Exception
{
	if (startPage < 1 || startPage > collector.getDocument().getPageCount())
	{
		throw new IllegalStateException("'startPage' is out of range");
	}
	if (endPage < 1 || endPage > collector.getDocument().getPageCount() || endPage < startPage)
	{
		throw new IllegalStateException("'endPage' is out of range");
	}
	checkPageListsPopulated();
	ArrayList<Node> pageNodes = new ArrayList<>();
	for (int page = startPage; page <= endPage; page++)
	{
		// Bazı sayfalar boş olabilir.
		if (!reversePageLookup.containsKey(page))
		{
			continue;
		}
		for (Node node : reversePageLookup.get(page))
		{
			if (node.getParentNode() != null
				&& (nodeType == NodeType.ANY || node.getNodeType() == nodeType)
				&& !pageNodes.contains(node))
			{
				pageNodes.add(node);
			}
		}
	}
	return pageNodes;
}
/// <özet>
/// İki veya daha fazla sayfada görünen düğümleri, aynı şekilde görünmelerini sağlayacak şekilde ayrı düğümlere böler
/// ancak artık sayfada görünmüyor.
/// </özet>
public void splitNodesAcrossPages() throws Exception
{
	for (Paragraph paragraph : (Iterable<Paragraph>) collector.getDocument().getChildNodes(NodeType.PARAGRAPH, true))
	{
		if (getPage(paragraph) != getPageEnd(paragraph))
		{
			splitRunsByWords(paragraph);
		}
	}
	clearCollector();
	// Sayfalara bölünmüş olması muhtemel tüm kompozitleri ziyaret edin ve bunları ayrı düğümlere bölün.
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <özet>
/// Bu, bölünmüş düğümlerin sayfa numaralarını güncellemek için <see cref="SectionSplitter"/> tarafından çağrılır.
/// </özet>
/// <param adı = "düğüm">
/// Düğüm.
/// </param>
/// <param name="başlangıçSayfası">
/// Başlangıç Sayfası.
/// </param>
/// <param adı = "endPage">
/// Son Sayfa.
/// </param>
void addPageNumbersForNode(Node node, int startPage, int endPage)
{
	if (startPage > 0)
	{
		nodeStartPageLookup.put(node, startPage);
	}
	if (endPage > 0)
	{
		nodeEndPageLookup.put(node, endPage);
	}
}
private boolean isHeaderFooterType(Node node)
{
	return node.getNodeType() == NodeType.HEADER_FOOTER || node.getAncestor(NodeType.HEADER_FOOTER) != null;
}
private void checkPageListsPopulated() throws Exception {
	if (reversePageLookup != null)
	{
		return;
	}
	reversePageLookup = new HashMap<Integer, ArrayList<Node>>();
	// Her düğümü, her sayfada bulunan düğümleri temsil eden bir listeye ekleyin.
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//Üstbilgiler/Altbilgiler bölümleri takip eder ve kendi başlarına bölünmezler.
		if (isHeaderFooterType(node))
		{
			continue;
		}
		int startPage = getPage(node);
		int endPage = getPageEnd(node);
		for (int page = startPage; page <= endPage; page++)
		{
			if (!reversePageLookup.containsKey(page))
			{
				reversePageLookup.put(page, new ArrayList<Node>());
			}
			reversePageLookup.get(page).add(node);
		}
	}
}
private void splitRunsByWords(Paragraph paragraph) throws Exception {
	for (Run run : paragraph.getRuns())
	{
		if (getPage(run) == getPageEnd(run))
		{
			continue;
		}
		splitRunByWords(run);
	}
}
private void splitRunByWords(Run run)
{
	String[] words = reverseWord(run.getText());
	for (String word : words)
	{
		int pos = run.getText().length() - word.length() - 1;
		if (pos > 1)
		{
			splitRun(run, run.getText().length() - word.length() - 1);
		}
	}
}
private static String[] reverseWord(String str) {
	String words[] = str.split(" ");
	String reverseWord = "";
	for (String w : words) {
		StringBuilder sb = new StringBuilder(w);
		sb.reverse();
		reverseWord += sb.toString() + " ";
	}
	return reverseWord.split(" ");
}
/// <özet>
/// Belirtilen çalıştırmanın metnini iki çalıştırmaya böler.
/// Yeni çalıştırmayı belirtilen çalıştırmanın hemen sonrasına ekler.
/// </özet>
private void splitRun(Run run, int position)
{
	Run afterRun = (Run) run.deepClone(true);
	afterRun.setText(run.getText().substring(position));
	run.setText(run.getText().substring((0), (0) + (position)));
	run.getParentNode().insertAfter(afterRun, run);
}
private void clearCollector() throws Exception
{
	collector.clear();
	collector.getDocument().updatePageLayout();
	nodeStartPageLookup.clear();
	nodeEndPageLookup.clear();
}
}
class PageNumberFinderFactory
{
public static PageNumberFinder create(Document document) throws Exception
{
	LayoutCollector layoutCollector = new LayoutCollector(document);
	document.updatePageLayout();
	PageNumberFinder pageNumberFinder = new PageNumberFinder(layoutCollector);
	pageNumberFinder.splitNodesAcrossPages();
	return pageNumberFinder;
}
}
/// <özet>
/// Belgeyi birden çok bölüme bölerek her sayfanın bir bölüm sınırında başlayıp bitmesini sağlar.
/// </özet>
class SectionSplitter extends DocumentVisitor
{
private PageNumberFinder pageNumberFinder;
public SectionSplitter(PageNumberFinder pageNumberFinder)
{
	this.pageNumberFinder = pageNumberFinder;
}
public int visitParagraphStart(Paragraph paragraph) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(paragraph);
}
public int visitTableStart(Table table) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(table);
}
public int visitRowStart(Row row) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(row);
}
public int visitCellStart(Cell cell) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(cell);
}
public int visitStructuredDocumentTagStart(StructuredDocumentTag sdt) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(sdt);
}
public int visitSmartTagStart(SmartTag smartTag) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(smartTag);
}
public int visitSectionStart(Section section) throws Exception {
	Section previousSection = (Section) section.getPreviousSibling();
	// Önceki bir bölüm varsa, bağlantılı üstbilgi altbilgilerini kopyalamayı deneyin.
	// Aksi takdirde, önceki bölümün eksik olması durumunda çıkarılan belgede görünmezler.
	if (previousSection != null)
	{
		HeaderFooterCollection previousHeaderFooters = previousSection.getHeadersFooters();
		if (!section.getPageSetup().getRestartPageNumbering())
		{
			section.getPageSetup().setRestartPageNumbering(true);
			section.getPageSetup().setPageStartingNumber(previousSection.getPageSetup().getPageStartingNumber() +
												   pageNumberFinder.pageSpan(previousSection));
		}
		for (HeaderFooter previousHeaderFooter : (Iterable<HeaderFooter>) previousHeaderFooters)
		{
			if (section.getHeadersFooters().getByHeaderFooterType(previousHeaderFooter.getHeaderFooterType()) == null)
			{
				HeaderFooter newHeaderFooter =
					(HeaderFooter) previousHeaderFooters.getByHeaderFooterType(previousHeaderFooter.getHeaderFooterType()).deepClone(true);
				section.getHeadersFooters().add(newHeaderFooter);
			}
		}
	}
	return continueIfCompositeAcrossPageElseSkip(section);
}
public int visitSmartTagEnd(SmartTag smartTag) throws Exception {
	splitComposite(smartTag);
	return VisitorAction.CONTINUE;
}
public int visitStructuredDocumentTagEnd(StructuredDocumentTag sdt) throws Exception {
	splitComposite(sdt);
	return VisitorAction.CONTINUE;
}
public int visitCellEnd(Cell cell) throws Exception {
	splitComposite(cell);
	return VisitorAction.CONTINUE;
}
public int visitRowEnd(Row row) throws Exception {
	splitComposite(row);
	return VisitorAction.CONTINUE;
}
public int visitTableEnd(Table table) throws Exception {
	splitComposite(table);
	return VisitorAction.CONTINUE;
}
public int visitParagraphEnd(Paragraph paragraph) throws Exception {
	// Paragraf yalnızca bölüm sonu içeriyorsa, sahte giriş ekleyin.
	if (paragraph.isEndOfSection() && paragraph.getChildNodes().getCount() == 1 &&
		"\f".equals(paragraph.getChildNodes().get(0).getText()))
	{
		Run run = new Run(paragraph.getDocument());
		paragraph.appendChild(run);
		int currentEndPageNum = pageNumberFinder.getPageEnd(paragraph);
		pageNumberFinder.addPageNumbersForNode(run, currentEndPageNum, currentEndPageNum);
	}
	for (Node cloneNode : splitComposite(paragraph))
	{
		Paragraph clonePara = (Paragraph) cloneNode;
		// Liste numaralandırmasını kopyalanan paragraftan kaldırın ancak girintiyi aynı bırakın
		// paragrafın önceki öğenin bir parçası olması gerektiği için.
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		// Ek aralıklar farklı görünmelerine neden olabileceğinden, tablolarda bölünmüş paragrafların aralıklarını sıfırlayın.
		if (paragraph.isInCell())
		{
			clonePara.getParagraphFormat().setSpaceBefore(0.0);
			paragraph.getParagraphFormat().setSpaceAfter(0.0);
		}
	}
	return VisitorAction.CONTINUE;
}
public int visitSectionEnd(Section section) throws Exception {
	for (Node cloneNode : splitComposite(section))
	{
		Section cloneSection = (Section) cloneNode;
		cloneSection.getPageSetup().setSectionStart(SectionStart.NEW_PAGE);
		cloneSection.getPageSetup().setRestartPageNumbering(true);
		cloneSection.getPageSetup().setPageStartingNumber(section.getPageSetup().getPageStartingNumber() +
													(section.getDocument().indexOf(cloneSection) -
													 section.getDocument().indexOf(section)));
		cloneSection.getPageSetup().setDifferentFirstPageHeaderFooter(false);
		// Bölümün sonundaki sayfa sonunu düzeltir.
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	// Bölümün gövdesi için de yeni sayfa numaralandırması ekleyin.
	pageNumberFinder.addPageNumbersForNode(section.getBody(), pageNumberFinder.getPage(section),
		pageNumberFinder.getPageEnd(section));
	return VisitorAction.CONTINUE;
}
private /*VisitorAction*/int continueIfCompositeAcrossPageElseSkip(CompositeNode composite) throws Exception {
	return pageNumberFinder.pageSpan(composite) > 1
		? VisitorAction.CONTINUE
		: VisitorAction.SKIP_THIS_NODE;
}
private ArrayList<Node> splitComposite(CompositeNode composite) throws Exception {
	ArrayList<Node> splitNodes = new ArrayList<>();
	for (Node splitNode : findChildSplitPositions(composite))
	{
		splitNodes.add(splitCompositeAtNode(composite, splitNode));
	}
	return splitNodes;
}
private Iterable<Node> findChildSplitPositions(CompositeNode node) throws Exception {
	// Bir düğüm birden fazla sayfaya yayılabilir, dolayısıyla bölünmüş konumların bir listesi döndürülür.
	//Bölünmüş düğüm bir sonraki sayfadaki ilk düğümdür.
	ArrayList<Node> splitList = new ArrayList<Node>();
	int startingPage = pageNumberFinder.getPage(node);
	Node[] childNodes = node.getNodeType() == NodeType.SECTION
		? ((Section) node).getBody().getChildNodes().toArray()
		: node.getChildNodes().toArray();
	for (Node childNode : childNodes)
	{
		int pageNum = pageNumberFinder.getPage(childNode);
		if (childNode instanceof Run)
		{
			pageNum = pageNumberFinder.getPageEnd(childNode);
		}
		// Alt düğümün sayfası değiştiyse bu bölünmüş konumdur.
		// Bunu listeye ekleyin.
		if (pageNum > startingPage)
		{
			splitList.add(childNode);
			startingPage = pageNum;
		}
		if (pageNumberFinder.pageSpan(childNode) > 1)
		{
			pageNumberFinder.addPageNumbersForNode(childNode, pageNum, pageNum);
		}
	}
	// Kompozitleri geriye doğru bölerek klonlanan düğümlerin doğru sıraya eklenmesini sağlayın.
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	// Sonraki sayfada bulunan tüm düğümleri kopyalanan düğüme taşıyın. Satır düğümlerini ayrı ayrı işleyin.
	if (baseNode.getNodeType() != NodeType.ROW)
	{
		CompositeNode composite = cloneNode;
		if (baseNode.getNodeType() == NodeType.SECTION)
		{
			cloneNode = (CompositeNode) baseNode.deepClone(true);
			Section section = (Section) cloneNode;
			section.getBody().removeAllChildren();
			composite = section.getBody();
		}
		while (node != null)
		{
			Node nextNode = node.getNextSibling();
			composite.appendChild(node);
			node = nextNode;
		}
	}
	else
	{
		// Eğer bir satırla uğraşıyorsak klonlanan satır için kukla hücreler eklememiz gerekir.
		int targetPageNum = pageNumberFinder.getPage(targetNode);
		Node[] childNodes = baseNode.getChildNodes().toArray();
		for (Node childNode : childNodes)
		{
			int pageNum = pageNumberFinder.getPage(childNode);
			if (pageNum == targetPageNum)
			{
				if (cloneNode.getNodeType() == NodeType.ROW)
					((Row) cloneNode).ensureMinimum();
				if (cloneNode.getNodeType() == NodeType.CELL)
					((Cell) cloneNode).ensureMinimum();
				cloneNode.getLastChild().remove();
				cloneNode.appendChild(childNode);
			}
			else if (pageNum == currentPageNum)
			{
				cloneNode.appendChild(childNode.deepClone(false));
				if (cloneNode.getLastChild().getNodeType() != NodeType.CELL)
				{
					((CompositeNode) cloneNode.getLastChild()).appendChild(
						((CompositeNode) childNode).getFirstChild().deepClone(false));
				}
			}
		}
	}
	// Bölünmüş düğümü orijinalin arkasına ekleyin.
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	// Alt düğümler de dahil olmak üzere temel düğümün ve klonlanmış düğümün yeni sayfa numaralarını güncelleyin.
	// Klonlanan kompozit tek sayfada olacak şekilde bölündüğünden bu yalnızca tek bir sayfa olacaktır.
	int currentEndPageNum = pageNumberFinder.getPageEnd(baseNode);
	pageNumberFinder.addPageNumbersForNode(baseNode, currentPageNum, currentEndPageNum - 1);
	pageNumberFinder.addPageNumbersForNode(cloneNode, currentEndPageNum, currentEndPageNum);
	for (Node childNode : (Iterable<Node>) cloneNode.getChildNodes(NodeType.ANY, true))
	{
		pageNumberFinder.addPageNumbersForNode(childNode, currentEndPageNum, currentEndPageNum);
	}
	return cloneNode;
}
}

class SplitPageBreakCorrector
{
private static final String PAGE_BREAK_STR = "\f";
private static final char PAGE_BREAK = '\f';
public static void processSection(Section section)
{
	if (section.getChildNodes().getCount() == 0)
	{
		return;
	}
	Body lastBody = (Body) Arrays.stream(new Iterator[]{section.getChildNodes().iterator()}).reduce((first, second) -> second)
		.orElse(null);
	RunCollection runs = (RunCollection) lastBody.getChildNodes(NodeType.RUN, true).iterator();
	Run run  = Arrays.stream(runs.toArray()).filter(p -> p.getText().endsWith(PAGE_BREAK_STR)).findFirst().get();
	if (run != null)
	{
		removePageBreak(run);
	}
}
public void removePageBreakFromParagraph(Paragraph paragraph)
{
	Run run = (Run) paragraph.getFirstChild();
	if (PAGE_BREAK_STR.equals(run.getText()))
	{
		paragraph.removeChild(run);
	}
}
private void processLastParagraph(Paragraph paragraph)
{
	Node lastNode = paragraph.getChildNodes().get(paragraph.getChildNodes().getCount() - 1);
	if (lastNode.getNodeType() != NodeType.RUN)
	{
		return;
	}
	Run run = (Run) lastNode;
	removePageBreak(run);
}
private static void removePageBreak(Run run)
{
	Paragraph paragraph = run.getParentParagraph();
	if (PAGE_BREAK_STR.equals(run.getText()))
	{
		paragraph.removeChild(run);
	}
	else if (run.getText().endsWith(PAGE_BREAK_STR))
	{
		run.setText(StringUtils.stripEnd(run.getText(), String.valueOf(PAGE_BREAK)));
	}
	if (paragraph.getChildNodes().getCount() == 0)
	{
		CompositeNode parent = paragraph.getParentNode();
		parent.removeChild(paragraph);
	}
}
}
```

## Çözüm

Artık Aspose.Words for Java kullanarak bir belgeyi ayrı sayfalara nasıl böleceğinizi öğrendiniz. Bu kılavuz, kaynak kodu örnekleriyle kapsamlı bir adım adım eğitim sağlar. Belgelerle çalışırken özel gereksinimlerinizi karşılamak için bu kodu daha da özelleştirebilir ve genişletebilirsiniz.
Kesinlikle! Aspose.Words for Java kullanarak belgeleri sayfalara bölmeyle ilgili kılavuzumuza bir SSS bölümü ekleyelim.

## SSS'ler

### Aspose.Words for Java'yı projeme nasıl eklerim?

Aspose.Words for Java'yı projenize eklemek için şu adımları izleyin:

1.  Aspose.Words for Java kütüphanesini şu adresten indirin:[Burada](https://releases.aspose.com/words/java/).
2. İndirdiğiniz JAR dosyasını projenizin sınıf yoluna ekleyin.
3. Artık projenizde Aspose.Words for Java'yı kullanmaya başlayabilirsiniz.

### PDF veya DOCX gibi diğer formatlardaki belgeleri bölebilir miyim?

Hayır, bu kılavuz özellikle Aspose.Words for Java kullanılarak DOC formatındaki belgelerin bölünmesini kapsar. Belgeleri başka biçimlerde bölmeniz gerekiyorsa bu biçimleri destekleyen diğer kitaplıkları veya araçları keşfetmeniz gerekebilir.

### Aspose.Words for Java ücretsiz bir kütüphane midir?

 Hayır, Aspose.Words for Java ücretsiz bir kütüphane değildir. Lisans ücreti olan ticari bir üründür. Ziyaret edebilirsiniz[Aspose.Words for Java fiyatlandırma sayfası](https://purchase.aspose.com/words/java) Lisanslama ve fiyatlandırma ayrıntıları hakkında daha fazla bilgi için.

### Belgeleri özel sayfa boyutlarına ve formatlarına bölebilir miyim?

Evet, Aspose.Words for Java'daki sayfa düzeni özelliklerini değiştirerek bölünmüş belgelerin sayfa boyutlarını ve formatlarını özelleştirebilirsiniz. Sayfa ayarlarını gereksinimlerinize göre nasıl özelleştireceğinize ilişkin ayrıntılar için Aspose.Words belgelerine bakın.

### Bölünebilecek sayfa sayısında herhangi bir sınırlama var mı?

Aspose.Words for Java, bölebileceğiniz sayfa sayısına özel sınırlamalar getirmez. Ancak çok büyük belgelerin daha fazla bellek ve işlem süresi gerektirebileceğini unutmayın. Büyük belgelerle çalışırken sistem kaynaklarına dikkat edin.

### Belgeleri bölerken üstbilgileri ve altbilgileri nasıl işleyebilirim?

Aspose.Words for Java kütüphanesi kullanılarak belgeleri bölerken üstbilgiler ve altbilgiler işlenebilir. Üstbilgi ve altbilgi içeriğini orijinal belgeden bölünmüş belgelere kopyalayarak bunların doğru şekilde korunmasını sağlayabilirsiniz. Bu işlemi özel üstbilgi ve altbilgi gereksinimlerinize göre özelleştirmeniz gerekebilir.