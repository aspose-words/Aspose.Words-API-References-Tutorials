---
title: Разделение документов на страницы в Aspose.Words для Java
linktitle: Разделение документов на страницы
second_title: API обработки Java-документов Aspose.Words
description: Узнайте, как разбивать документы на страницы с помощью Aspose.Words для Java. Пошаговое руководство с исходным кодом для эффективной обработки документов.
type: docs
weight: 23
url: /ru/java/document-manipulation/splitting-documents-into-pages/
---

Если вы работаете с обработкой документов на Java, Aspose.Words for Java — это мощный API, который поможет вам эффективно разбивать документы на отдельные страницы. В этом пошаговом руководстве мы проведем вас через процесс разделения документов, используя предоставленный исходный код. К концу этого руководства вы сможете с легкостью разделять документы, улучшая свои возможности управления документами.

## 1. Введение

Aspose.Words for Java — это библиотека Java, которая позволяет программно манипулировать документами Word. Одной из распространенных задач является разделение документа на отдельные страницы, что может быть полезно для различных целей, таких как архивирование, печать или обработка документов.

## 2. Предварительные условия

Прежде чем мы углубимся в код, убедитесь, что у вас есть следующие предварительные условия:

- В вашей системе установлен Java Development Kit (JDK).
-  Библиотека Aspose.Words для Java, которую вы можете скачать[здесь](https://releases.aspose.com/words/java/).

## 3. Настройка среды

Для начала настройте среду разработки следующим образом:

- Создайте проект Java в предпочитаемой вами интегрированной среде разработки (IDE).
- Добавьте в свой проект библиотеку Aspose.Words for Java. Вы можете обратиться к[документация](https://reference.aspose.com/words/java/) для получения подробных инструкций.

## 4. Понимание исходного кода

Предоставленный вами исходный код предназначен для разделения документа на отдельные страницы. Давайте разберем ключевые компоненты:

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- Мы извлекаем базовое имя и расширение из входного документа.
- Мы загружаем документ с помощью Aspose.Words для Java.

## 5. Разделение документов шаг за шагом

### 5.1. Загрузка документа

```java
Document doc = new Document(docName);
```

 На этом этапе мы загружаем входной документ в`Document` объект, который позволяет нам работать с содержимым документа.

### 5.2. Инициализация DocumentPageSplitter

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

 Мы инициализируем`DocumentPageSplitter` объект с нашим загруженным документом. Этот класс предоставляется Aspose.Words для Java и помогает нам разделить документ на страницы.

### 5.3. Сохраняйте каждую страницу

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

На этом этапе мы просматриваем каждую страницу документа и сохраняем ее как отдельный документ. Вы можете указать путь к каталогу, в котором будут сохранены разделенные страницы.

## 6. Запуск кода

Чтобы успешно запустить этот код, убедитесь, что вы настроили свою среду и добавили в свой проект библиотеку Aspose.Words for Java. Затем выполните код, и ваш документ будет разделен на отдельные страницы.

## Исходный код DocumentPageSplitter

```java
/// <сводка>
/// Разбивает документ на несколько документов, по одному на страницу.
/// </сводка>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <сводка>
/// Инициализирует новый экземпляр класса <see cref="DocumentPageSplitter"/>.
/// Этот метод разбивает документ на разделы, так что каждая страница начинается и заканчивается в граничном разделе.
/// После этого документ не рекомендуется изменять.
/// </сводка>
/// <param name="source">Исходный документ</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <сводка>
///Получает документ страницы.
/// </сводка>
/// <param name="pageIndex">
/// Индекс страницы на основе 1.
///</парам>
/// <возвращается>
/// <см. Cref="Документ"/>.
/// </возврат>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <сводка>
/// Получает документ диапазона страниц.
/// </сводка>
//<param name="startIndex">
/// Индекс стартовой страницы на основе 1.
///</парам>
/// <param name="endIndex">
/// Индекс конечной страницы на основе 1.
///</парам>
/// <возвращается>
/// <см. Cref="Документ"/>.
/// </возврат>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <сводка>
/// Предоставляет методы для извлечения узлов документа, отображаемых на указанных страницах.
/// </сводка>
class PageNumberFinder
{
// Сопоставляет узел с номерами начальной/конечной страницы.
// Это используется для переопределения базовых номеров страниц, предоставленных сборщиком при разделении документа.
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
// Сопоставляет номер страницы со списком узлов, найденных на этой странице.
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <сводка>
/// Инициализирует новый экземпляр класса <see cref="PageNumberFinder"/>.
/// </сводка>
/// <param name="collector">Экземпляр сборщика, имеющий записи модели макета для документа.</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <сводка>
/// Получает индекс страницы, отсчитываемый от 1, с которой начинается узел.
/// </сводка>
/// <имя параметра="узел">
///Узел.
///</парам>
/// <возвращается>
/// Индекс страницы.
/// </возврат>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <сводка>
/// Получает индекс страницы, отсчитываемый от 1, на которой заканчивается узел.
/// </сводка>
/// <имя параметра="узел">
///Узел.
///</парам>
/// <возвращается>
/// Индекс страницы.
/// </возврат>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <сводка>
//Возвращает количество страниц, охватываемых указанным узлом. Возвращает 1, если узел содержится на одной странице.
/// </сводка>
/// <имя параметра="узел">
///Узел.
///</парам>
/// <возвращается>
/// Индекс страницы.
/// </возврат>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <сводка>
///Возвращает список узлов, содержащихся в любом месте указанной страницы или страниц, соответствующих указанному типу узла.
/// </сводка>
/// <param name="startPage">
/// Стартовая страница.
///</парам>
/// <param name="endPage">
///Конечная страница.
///</парам>
/// <param name="nodeType">
///Тип узла.
///</парам>
/// <возвращается>
///The <see cref="IList{T}"/>.
/// </возврат>
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
		// Некоторые страницы могут быть пустыми.
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
/// <сводка>
/// Разделяет узлы, которые появляются на двух или более страницах, на отдельные узлы, чтобы они по-прежнему выглядели одинаково.
///но больше не появляются на странице.
/// </сводка>
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
	// Посетите любые составные элементы, которые могут быть разделены на страницы, и разделите их на отдельные узлы.
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <сводка>
/// Это вызывается <see cref="SectionSplitter"/> для обновления номеров страниц разделенных узлов.
/// </сводка>
/// <имя параметра="узел">
///Узел.
///</парам>
/// <param name="startPage">
/// Стартовая страница.
///</парам>
/// <param name="endPage">
///Конечная страница.
///</парам>
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
	// Добавьте каждый узел в список, представляющий узлы, найденные на каждой странице.
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//Верхние/нижние колонтитулы следуют за разделами и не разделяются сами по себе.
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
/// <сводка>
/// Разбивает текст указанного прогона на два прогона.
///Вставляет новый запуск сразу после указанного запуска.
/// </сводка>
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
/// <сводка>
/// Разделяет документ на несколько разделов, так что каждая страница начинается и заканчивается в граничном разделе.
/// </сводка>
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
	// Если существует предыдущий раздел, попытайтесь скопировать все связанные верхние и нижние колонтитулы.
	// В противном случае они не появятся в извлеченном документе, если предыдущий раздел отсутствует.
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
	// Если абзац содержит только разрыв раздела, добавьте ложный переход.
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
		// Удалите нумерацию списка из клонированного абзаца, но оставьте индекс прежним.
		// поскольку абзац должен быть частью предыдущего пункта.
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		// Сбросьте интервал разделенных абзацев в таблицах, поскольку из-за дополнительного интервала они могут выглядеть по-другому.
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
		// Исправляет разрыв страницы в конце раздела.
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	// Также добавьте новую нумерацию страниц для тела раздела.
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
	// Узел может охватывать несколько страниц, поэтому возвращается список разделенных позиций.
	//Разделенный узел — это первый узел на следующей странице.
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
		// Если страница дочернего узла изменилась, то это позиция разделения.
		// Добавьте это в список.
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
	// Разделите композиты назад, чтобы клонированные узлы были вставлены в правильном порядке.
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	// Переместите все узлы, найденные на следующей странице, в скопированный узел. Обрабатывайте узлы строк отдельно.
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
		// Если мы имеем дело со строкой, нам нужно добавить фиктивные ячейки для клонированной строки.
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
	// Вставьте узел разделения после оригинала.
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	// Обновите новые номера страниц базового узла и клонированного узла, включая его потомков.
	// Это будет только одна страница, поскольку клонированная композиция разделена на одну страницу.
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

## Заключение

Теперь вы узнали, как разделить документ на отдельные страницы с помощью Aspose.Words для Java. В этом руководстве представлено подробное пошаговое руководство с примерами исходного кода. Вы можете дополнительно настроить и расширить этот код в соответствии с вашими конкретными требованиями при работе с документами.
Конечно! Давайте добавим раздел часто задаваемых вопросов в наше руководство по разбиению документов на страницы с помощью Aspose.Words for Java.

## Часто задаваемые вопросы

### Как добавить Aspose.Words для Java в мой проект?

Чтобы добавить Aspose.Words for Java в свой проект, выполните следующие действия:

1.  Загрузите библиотеку Aspose.Words для Java с сайта[здесь](https://releases.aspose.com/words/java/).
2. Добавьте загруженный файл JAR в путь к классам вашего проекта.
3. Теперь вы можете начать использовать Aspose.Words for Java в своем проекте.

### Могу ли я разделить документы в других форматах, например PDF или DOCX?

Нет, в этом руководстве конкретно рассматривается разделение документов в формате DOC с помощью Aspose.Words для Java. Если вам нужно разделить документы в других форматах, вам может потребоваться изучить другие библиотеки или инструменты, поддерживающие эти форматы.

### Является ли Aspose.Words для Java бесплатной библиотекой?

 Нет, Aspose.Words for Java не является бесплатной библиотекой. Это коммерческий продукт с лицензионным сбором. Вы можете посетить[Страница цен на Aspose.Words для Java](https://purchase.aspose.com/words/java) для получения дополнительной информации о лицензировании и ценах.

### Могу ли я разделить документы на страницы произвольного размера и формата?

Да, вы можете настроить размеры и форматы страниц разделенных документов, изменив свойства настройки страницы в Aspose.Words для Java. Обратитесь к документации Aspose.Words для получения подробной информации о том, как настроить параметры страницы в соответствии с вашими требованиями.

### Существуют ли какие-либо ограничения на количество страниц, которые можно разделить?

Aspose.Words for Java не накладывает особых ограничений на количество страниц, которые можно разделить. Однако имейте в виду, что очень большие документы могут потребовать больше памяти и времени обработки. Помните о системных ресурсах при работе с большими документами.

### Как я могу обрабатывать верхние и нижние колонтитулы при разделении документов?

Верхние и нижние колонтитулы можно обрабатывать при разделении документов с помощью библиотеки Aspose.Words для Java. Вы можете скопировать содержимое верхнего и нижнего колонтитула из исходного документа в разделенные документы, гарантируя их правильное сохранение. Возможно, вам придется настроить этот процесс в соответствии с вашими конкретными требованиями к верхнему и нижнему колонтитулу.