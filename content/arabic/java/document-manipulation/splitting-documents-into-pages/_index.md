---
title: تقسيم المستندات إلى صفحات في Aspose.Words لـ Java
linktitle: تقسيم المستندات إلى صفحات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية تقسيم المستندات إلى صفحات باستخدام Aspose.Words for Java. دليل خطوة بخطوة مع الكود المصدري لمعالجة المستندات بكفاءة.
type: docs
weight: 23
url: /ar/java/document-manipulation/splitting-documents-into-pages/
---

إذا كنت تعمل على معالجة المستندات في Java، فإن Aspose.Words for Java عبارة عن واجهة برمجة تطبيقات قوية يمكنها مساعدتك في تقسيم المستندات إلى صفحات منفصلة بكفاءة. في هذا البرنامج التعليمي خطوة بخطوة، سنرشدك خلال عملية تقسيم المستندات باستخدام كود المصدر المقدم. بحلول نهاية هذا البرنامج التعليمي، ستكون قادرًا على تقسيم المستندات بسهولة، مما يؤدي إلى تحسين قدرات إدارة المستندات لديك.

## 1 المقدمة

Aspose.Words for Java هي مكتبة Java تسمح لك بمعالجة مستندات Word برمجيًا. إحدى المهام الشائعة هي تقسيم مستند إلى صفحات منفصلة، وهو ما يمكن أن يكون مفيدًا لأغراض مختلفة، مثل الأرشفة أو الطباعة أو معالجة المستندات.

## 2. المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Words لمكتبة Java، والتي يمكنك تنزيلها[هنا](https://releases.aspose.com/words/java/).

## 3. إعداد البيئة الخاصة بك

للبدء، قم بإعداد بيئة التطوير الخاصة بك على النحو التالي:

- قم بإنشاء مشروع Java في بيئة التطوير المتكاملة (IDE) المفضلة لديك.
- أضف مكتبة Aspose.Words for Java إلى مشروعك. يمكنك الرجوع إلى[توثيق](https://reference.aspose.com/words/java/) للحصول على تعليمات مفصلة.

## 4. فهم كود المصدر

تم تصميم كود المصدر الذي قدمته لتقسيم المستند إلى صفحات منفصلة. دعونا نحلل المكونات الرئيسية:

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- نقوم باستخراج الاسم الأساسي وامتداد مستند الإدخال.
- نقوم بتحميل المستند باستخدام Aspose.Words لـ Java.

## 5. تقسيم المستندات خطوة بخطوة

### 5.1. تحميل الوثيقة

```java
Document doc = new Document(docName);
```

 في هذه الخطوة، نقوم بتحميل مستند الإدخال إلى ملف`Document` الكائن، والذي يسمح لنا بالعمل مع محتوى المستند.

### 5.2. تهيئة DocumentPageSplitter

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

 نقوم بتهيئة أ`DocumentPageSplitter` كائن مع وثيقتنا المحملة. يتم توفير هذا الفصل بواسطة Aspose.Words لـ Java ويساعدنا على تقسيم المستند إلى صفحات.

### 5.3. حفظ كل صفحة

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

في هذه الخطوة، نقوم بمراجعة كل صفحة من المستند وحفظها كمستند منفصل. يمكنك تحديد مسار الدليل حيث سيتم حفظ الصفحات المقسمة.

## 6. تشغيل الكود

لتشغيل هذا الكود بنجاح، تأكد من أنك قمت بإعداد البيئة الخاصة بك وإضافة مكتبة Aspose.Words for Java إلى مشروعك. بعد ذلك، قم بتنفيذ التعليمات البرمجية، وسيتم تقسيم المستند الخاص بك إلى صفحات منفصلة.

## DocumentPageSplitter كود المصدر

```java
/// <الملخص>
/// يقسم المستند إلى مستندات متعددة، واحدة لكل صفحة.
/// </ملخص>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <الملخص>
/// تهيئة مثيل جديد للفئة <see cref="DocumentPageSplitter"/>.
/// تقوم هذه الطريقة بتقسيم المستند إلى أقسام بحيث تبدأ كل صفحة وتنتهي عند حد القسم.
/// يوصى بعدم تعديل المستند بعد ذلك.
/// </ملخص>
/// <param name="source">المستند المصدر</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <الملخص>
/// يحصل على وثيقة الصفحة.
/// </ملخص>
/// <param name="pageIndex">
/// 1-فهرس للصفحة.
/// </param>
/// <إرجاع>
/// <see cref="Document"/>.
/// </إرجاع>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <الملخص>
/// الحصول على وثيقة نطاق الصفحات.
/// </ملخص>
//<param name="startIndex">
/// 1-فهرس لصفحة البداية.
/// </param>
/// <param name="endIndex">
/// 1-فهرس صفحة النهاية.
/// </param>
/// <إرجاع>
/// <see cref="Document"/>.
/// </إرجاع>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <الملخص>
/// يوفر طرقًا لاستخراج عقد المستند التي يتم عرضها على صفحات محددة.
/// </ملخص>
class PageNumberFinder
{
// عقدة الخرائط إلى أرقام صفحات البداية/النهاية.
// يُستخدم هذا لتجاوز أرقام الصفحات الأساسية التي يوفرها المجمع عند تقسيم المستند.
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
// يقوم بتعيين رقم الصفحة إلى قائمة العقد الموجودة في تلك الصفحة.
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <الملخص>
/// تهيئة مثيل جديد للفئة <see cref="PageNumberFinder"/>.
/// </ملخص>
/// <param name="collector">مثيل جامع يحتوي على سجلات نموذج تخطيط للمستند.</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <الملخص>
/// استرداد الفهرس المستند إلى 1 للصفحة التي تبدأ بها العقدة.
/// </ملخص>
/// <param name="node">
/// العقدة.
/// </param>
/// <إرجاع>
/// فهرس الصفحة.
/// </إرجاع>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <الملخص>
/// استرداد الفهرس المستند إلى 1 للصفحة التي تنتهي عندها العقدة.
/// </ملخص>
/// <param name="node">
/// العقدة.
/// </param>
/// <إرجاع>
/// فهرس الصفحة.
/// </إرجاع>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <الملخص>
//إرجاع عدد الصفحات التي تمتد عليها العقدة المحددة. يُرجع 1 إذا كانت العقدة موجودة في صفحة واحدة.
/// </ملخص>
/// <param name="node">
/// العقدة.
/// </param>
/// <إرجاع>
/// فهرس الصفحة.
/// </إرجاع>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <الملخص>
/// إرجاع قائمة العقد الموجودة في أي مكان على الصفحة المحددة أو الصفحات التي تطابق نوع العقدة المحدد.
/// </ملخص>
/// <param name="startPage">
/// صفحة البداية.
/// </param>
/// <param name="endPage">
/// صفحة النهاية.
/// </param>
/// <param name="nodeType">
/// نوع العقدة.
/// </param>
/// <إرجاع>
/// <see cref="IList{T}"/>.
/// </إرجاع>
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
		// يمكن أن تكون بعض الصفحات فارغة.
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
/// <الملخص>
/// يقسم العقد التي تظهر على صفحتين أو أكثر إلى عقد منفصلة بحيث تظل تظهر بنفس الطريقة
/// ولكنها لم تعد تظهر عبر الصفحة.
/// </ملخص>
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
	// قم بزيارة أي مركبات قد تكون مقسمة عبر الصفحات وقسمها إلى عقد منفصلة.
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <الملخص>
/// يتم استدعاء هذا بواسطة <see cref="SectionSplitter"/> لتحديث أرقام صفحات العقد المقسمة.
/// </ملخص>
/// <param name="node">
/// العقدة.
/// </param>
/// <param name="startPage">
/// صفحة البداية.
/// </param>
/// <param name="endPage">
/// صفحة النهاية.
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
	// أضف كل عقدة إلى القائمة التي تمثل العقد الموجودة في كل صفحة.
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//تتبع الرؤوس والتذييلات الأقسام ولا يتم تقسيمها من تلقاء نفسها.
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
/// <الملخص>
/// يقسم النص الخاص بالتشغيل المحدد إلى تشغيلين.
/// يقوم بإدراج التشغيل الجديد مباشرة بعد التشغيل المحدد.
/// </ملخص>
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
/// <الملخص>
/// يقسم المستند إلى أقسام متعددة بحيث تبدأ كل صفحة وتنتهي عند حد القسم.
/// </ملخص>
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
	// إذا كان هناك قسم سابق، فحاول نسخ أي تذييلات رأس مرتبطة.
	// وإلا فلن تظهر في المستند المستخرج إذا كان القسم السابق مفقودًا.
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
	// إذا كانت الفقرة تحتوي على فاصل مقطعي فقط، فأضف تشغيلًا مزيفًا.
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
		// قم بإزالة ترقيم القائمة من الفقرة المستنسخة مع ترك المسافة البادئة كما هي
		// حيث من المفترض أن تكون الفقرة جزءًا من العنصر السابق.
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		// قم بإعادة ضبط المسافات بين الفقرات المقسمة في الجداول لأن المسافات الإضافية قد تؤدي إلى ظهورها بشكل مختلف.
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
		// يصحح فاصل الصفحات في نهاية المقطع.
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	// أضف ترقيمًا جديدًا للصفحات لنص القسم أيضًا.
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
	// قد تمتد العقدة عبر صفحات متعددة، لذلك يتم إرجاع قائمة بالمواضع المقسمة.
	//العقدة المقسمة هي العقدة الأولى في الصفحة التالية.
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
		// إذا تغيرت صفحة العقدة الفرعية، فهذا هو موضع الانقسام.
		// أضف هذا إلى القائمة.
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
	// قم بتقسيم المركبات إلى الخلف، بحيث يتم إدراج العقد المستنسخة بالترتيب الصحيح.
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	// انقل جميع العقد الموجودة في الصفحة التالية إلى العقدة المنسوخة. التعامل مع عقد الصف بشكل منفصل.
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
		// إذا كنا نتعامل مع صف، فنحن بحاجة إلى إضافة خلايا وهمية للصف المستنسخ.
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
	// أدخل العقدة المقسمة بعد العقدة الأصلية.
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	// قم بتحديث أرقام الصفحات الجديدة للعقدة الأساسية والعقدة المستنسخة، بما في ذلك أحفادها.
	// ستكون هذه صفحة واحدة فقط حيث سيتم تقسيم المركب المستنسخ ليكون على صفحة واحدة.
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

## خاتمة

لقد تعلمت الآن كيفية تقسيم مستند إلى صفحات منفصلة باستخدام Aspose.Words for Java. يوفر هذا الدليل برنامجًا تعليميًا شاملاً خطوة بخطوة مع أمثلة التعليمات البرمجية المصدر. يمكنك تخصيص هذا الرمز وتوسيعه بشكل أكبر لتلبية متطلباتك المحددة عند العمل مع المستندات.
بالتأكيد! دعونا نضيف قسم الأسئلة الشائعة إلى دليلنا حول تقسيم المستندات إلى صفحات باستخدام Aspose.Words for Java.

## الأسئلة الشائعة

### كيف يمكنني إضافة Aspose.Words for Java إلى مشروعي؟

لإضافة Aspose.Words for Java إلى مشروعك، اتبع الخطوات التالية:

1.  قم بتنزيل مكتبة Aspose.Words for Java من[هنا](https://releases.aspose.com/words/java/).
2. أضف ملف JAR الذي تم تنزيله إلى مسار الفصل الخاص بمشروعك.
3. يمكنك الآن البدء في استخدام Aspose.Words for Java في مشروعك.

### هل يمكنني تقسيم المستندات بتنسيقات أخرى، مثل PDF أو DOCX؟

لا، يغطي هذا الدليل على وجه التحديد تقسيم المستندات بتنسيق DOC باستخدام Aspose.Words for Java. إذا كنت بحاجة إلى تقسيم المستندات بتنسيقات أخرى، فقد تحتاج إلى استكشاف مكتبات أو أدوات أخرى تدعم تلك التنسيقات.

### هل Aspose.Words for Java مكتبة مجانية؟

 لا، Aspose.Words for Java ليست مكتبة مجانية. إنه منتج تجاري برسوم ترخيص. يمكنك زيارة[Aspose.Words لصفحة تسعير Java](https://purchase.aspose.com/words/java) لمزيد من المعلومات حول تفاصيل الترخيص والتسعير.

### هل يمكنني تقسيم المستندات إلى أحجام وتنسيقات صفحات مخصصة؟

نعم، يمكنك تخصيص أحجام الصفحات وتنسيقات المستندات المقسمة عن طريق تعديل خصائص إعداد الصفحة في Aspose.Words for Java. راجع وثائق Aspose.Words للحصول على تفاصيل حول كيفية تخصيص إعدادات الصفحة وفقًا لمتطلباتك.

### هل هناك أي قيود على عدد الصفحات التي يمكن تقسيمها؟

لا يفرض Aspose.Words for Java قيودًا محددة على عدد الصفحات التي يمكنك تقسيمها. ومع ذلك، ضع في اعتبارك أن المستندات الكبيرة جدًا قد تتطلب المزيد من الذاكرة ووقت المعالجة. انتبه لموارد النظام عند العمل مع المستندات الكبيرة.

### كيف يمكنني التعامل مع الرؤوس والتذييلات عند تقسيم المستندات؟

يمكن معالجة الرؤوس والتذييلات عند تقسيم المستندات باستخدام مكتبة Aspose.Words for Java. يمكنك نسخ محتوى الرأس والتذييل من المستند الأصلي إلى المستندات المقسمة، مما يضمن حفظها بشكل صحيح. قد تحتاج إلى تخصيص هذه العملية بناءً على متطلبات الرأس والتذييل المحددة لديك.