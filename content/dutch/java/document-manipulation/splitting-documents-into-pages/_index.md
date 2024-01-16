---
title: Documenten opsplitsen in pagina's in Aspose.Words voor Java
linktitle: Documenten opsplitsen in pagina's
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u documenten in pagina's kunt splitsen met Aspose.Words voor Java. Stap-voor-stap handleiding met broncode voor efficiënte documentverwerking.
type: docs
weight: 23
url: /nl/java/document-manipulation/splitting-documents-into-pages/
---

Als u met documentverwerking in Java werkt, is Aspose.Words voor Java een krachtige API waarmee u documenten efficiënt in afzonderlijke pagina's kunt opsplitsen. In deze stapsgewijze zelfstudie begeleiden we u door het proces van het splitsen van documenten met behulp van de meegeleverde broncode. Aan het einde van deze zelfstudie kunt u documenten eenvoudig splitsen, waardoor uw mogelijkheden voor documentbeheer worden verbeterd.

## 1. Inleiding

Aspose.Words voor Java is een Java-bibliotheek waarmee u Word-documenten programmatisch kunt manipuleren. Een veel voorkomende taak is het opsplitsen van een document in afzonderlijke pagina's, wat handig kan zijn voor verschillende doeleinden, zoals archiveren, afdrukken of documentverwerking.

## 2. Vereisten

Voordat we in de code duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Words voor Java-bibliotheek, die u kunt downloaden[hier](https://releases.aspose.com/words/java/).

## 3. Uw omgeving instellen

Om aan de slag te gaan, stelt u uw ontwikkelomgeving als volgt in:

- Maak een Java-project in de Integrated Development Environment (IDE) van uw voorkeur.
- Voeg de Aspose.Words voor Java-bibliotheek toe aan uw project. U kunt verwijzen naar de[documentatie](https://reference.aspose.com/words/java/) voor gedetailleerde instructies.

## 4. De broncode begrijpen

De broncode die u heeft opgegeven, is ontworpen om een document in afzonderlijke pagina's op te splitsen. Laten we de belangrijkste componenten opsplitsen:

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- We extraheren de basisnaam en extensie van het invoerdocument.
- We laden het document met Aspose.Words voor Java.

## 5. Documenten stap voor stap splitsen

### 5.1. Het document laden

```java
Document doc = new Document(docName);
```

 In deze stap laden we het invoerdocument in een`Document` object, waardoor we met de inhoud van het document kunnen werken.

### 5.2. Initialiseren van de DocumentPageSplitter

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

 Wij initialiseren a`DocumentPageSplitter` object met ons geladen document. Deze klasse wordt geleverd door Aspose.Words voor Java en helpt ons het document in pagina's te splitsen.

### 5.3. Elke pagina opslaan

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

In deze stap doorlopen we elke pagina van het document en slaan we deze op als een afzonderlijk document. U kunt het mappad opgeven waar de gesplitste pagina's worden opgeslagen.

## 6. De code uitvoeren

Om deze code succesvol uit te voeren, moet u ervoor zorgen dat u uw omgeving heeft ingesteld en de Aspose.Words voor Java-bibliotheek aan uw project heeft toegevoegd. Voer vervolgens de code uit en uw document wordt opgesplitst in afzonderlijke pagina's.

## DocumentPageSplitter-broncode

```java
/// <samenvatting>
/// Splitst een document op in meerdere documenten, één per pagina.
///</samenvatting>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <samenvatting>
/// Initialiseert een nieuw exemplaar van de klasse <see cref="DocumentPageSplitter"/>.
/// Bij deze methode wordt het document in secties gesplitst, zodat elke pagina begint en eindigt op een sectiegrens.
/// Het wordt aanbevolen om het document achteraf niet te wijzigen.
///</samenvatting>
/// <param name="source">Brondocument</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <samenvatting>
/// Haalt het document van een pagina op.
///</samenvatting>
/// <paramnaam = "paginaIndex">
/// 1-gebaseerde index van een pagina.
///</param>
/// <retourneert>
/// Het <zie cref="Document"/>.
/// </retourneert>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <samenvatting>
/// Haalt het document van een paginabereik op.
///</samenvatting>
//<paramnaam="startIndex">
/// 1-gebaseerde index van de startpagina.
///</param>
/// <paramnaam="endIndex">
/// 1-gebaseerde index van de eindpagina.
///</param>
/// <retourneert>
/// Het <zie cref="Document"/>.
/// </retourneert>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <samenvatting>
/// Biedt methoden voor het extraheren van knooppunten van een document die op bepaalde pagina's worden weergegeven.
///</samenvatting>
class PageNumberFinder
{
// Wijst een knooppunt toe aan een start-/eindpaginanummer.
// Dit wordt gebruikt om basispaginanummers te overschrijven die door het verzamelprogramma worden verstrekt wanneer het document wordt gesplitst.
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
// Wijst het paginanummer toe aan een lijst met knooppunten die op die pagina zijn gevonden.
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <samenvatting>
/// Initialiseert een nieuw exemplaar van de klasse <see cref="PageNumberFinder"/>.
///</samenvatting>
/// <param name="collector">Een verzamelinstantie die lay-outmodelrecords voor het document heeft.</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <samenvatting>
/// Haalt de op 1 gebaseerde index op van een pagina waarop het knooppunt begint.
///</samenvatting>
/// <paramnaam="knooppunt">
/// Het knooppunt.
///</param>
/// <retourneert>
/// Pagina-index.
/// </retourneert>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <samenvatting>
/// Haalt de op 1 gebaseerde index op van een pagina waarop het knooppunt eindigt.
///</samenvatting>
/// <paramnaam="knooppunt">
/// Het knooppunt.
///</param>
/// <retourneert>
/// Pagina-index.
/// </retourneert>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <samenvatting>
//Geeft terug hoeveel pagina's het opgegeven knooppunt beslaat. Geeft 1 terug als het knooppunt zich binnen één pagina bevindt.
///</samenvatting>
/// <paramnaam="knooppunt">
/// Het knooppunt.
///</param>
/// <retourneert>
/// Pagina-index.
/// </retourneert>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <samenvatting>
/// Geeft een lijst met knooppunten terug die zich ergens op de opgegeven pagina bevinden of pagina's die overeenkomen met het opgegeven knooppunttype.
///</samenvatting>
/// <param name="startPagina">
/// De startpagina.
///</param>
/// <param name="endPage">
/// De eindpagina.
///</param>
/// <paramnaam="nodeType">
/// Het knooppunttype.
///</param>
/// <retourneert>
/// De <see cref="IList{T}"/>.
/// </retourneert>
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
		// Sommige pagina's kunnen leeg zijn.
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
/// <samenvatting>
/// Splitst knooppunten die over twee of meer pagina's verschijnen op in afzonderlijke knooppunten, zodat ze nog steeds op dezelfde manier verschijnen
/// maar verschijnen niet meer op een pagina.
///</samenvatting>
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
	// Bezoek eventuele composieten die mogelijk over pagina's zijn verdeeld en splits ze op in afzonderlijke knooppunten.
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <samenvatting>
/// Dit wordt aangeroepen door <see cref="SectionSplitter"/> om paginanummers van gesplitste knooppunten bij te werken.
///</samenvatting>
/// <paramnaam="knooppunt">
/// Het knooppunt.
///</param>
/// <param name="startPagina">
/// De startpagina.
///</param>
/// <param name="endPage">
/// De eindpagina.
///</param>
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
	// Voeg elk knooppunt toe aan een lijst die de knooppunten vertegenwoordigt die op elke pagina worden gevonden.
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//Kop- en voetteksten volgen secties en worden niet op zichzelf gesplitst.
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
/// <samenvatting>
/// Splitst de tekst van de opgegeven run in twee runs.
/// Voegt de nieuwe run in vlak na de opgegeven run.
///</samenvatting>
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
/// <samenvatting>
/// Splitst een document in meerdere secties, zodat elke pagina begint en eindigt op een sectiegrens.
///</samenvatting>
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
	// Als er een vorige sectie is, probeer dan eventuele gekoppelde koptekstvoetteksten te kopiëren.
	// Anders verschijnen ze niet in een uitgepakt document als de vorige sectie ontbreekt.
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
	// Als de alinea alleen een sectie-einde bevat, voeg dan nep-run-in toe.
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
		// Verwijder de lijstnummering uit de gekloonde alinea, maar laat de inspringing hetzelfde
		// omdat de paragraaf geacht wordt deel uit te maken van het voorgaande item.
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		// Stel de afstand van gesplitste alinea's in tabellen opnieuw in, omdat extra afstand ervoor kan zorgen dat ze er anders uitzien.
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
		// Corrigeert het pagina-einde aan het einde van de sectie.
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	// Voeg ook een nieuwe paginanummering toe voor de hoofdtekst van de sectie.
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
	// Een knooppunt kan zich over meerdere pagina's uitstrekken, dus er wordt een lijst met gesplitste posities geretourneerd.
	//Het gesplitste knooppunt is het eerste knooppunt op de volgende pagina.
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
		// Als de pagina van het onderliggende knooppunt is gewijzigd, is dit de gesplitste positie.
		// Voeg dit toe aan de lijst.
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
	// Splits composieten achterwaarts, zodat de gekloonde knooppunten in de juiste volgorde worden ingevoegd.
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	// Verplaats alle knooppunten op de volgende pagina naar het gekopieerde knooppunt. Behandel rijknooppunten afzonderlijk.
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
		// Als we met een rij te maken hebben, moeten we dummycellen toevoegen voor de gekloonde rij.
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
	// Plaats het gesplitste knooppunt na het origineel.
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	// Werk de nieuwe paginanummers van het basisknooppunt en het gekloonde knooppunt bij, inclusief de onderliggende knooppunten.
	// Dit zal slechts één pagina zijn, omdat de gekloonde composiet wordt gesplitst om op één pagina te staan.
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

## Conclusie

U hebt nu geleerd hoe u een document in afzonderlijke pagina's kunt splitsen met Aspose.Words voor Java. Deze handleiding biedt een uitgebreide stapsgewijze zelfstudie met broncodevoorbeelden. U kunt deze code verder aanpassen en uitbreiden om te voldoen aan uw specifieke vereisten bij het werken met documenten.
Zeker! Laten we een sectie met veelgestelde vragen toevoegen aan onze handleiding over het splitsen van documenten in pagina's met behulp van Aspose.Words voor Java.

## Veelgestelde vragen

### Hoe voeg ik Aspose.Words voor Java toe aan mijn project?

Volg deze stappen om Aspose.Words voor Java aan uw project toe te voegen:

1.  Download de Aspose.Words voor Java-bibliotheek van[hier](https://releases.aspose.com/words/java/).
2. Voeg het gedownloade JAR-bestand toe aan het klassenpad van uw project.
3. U kunt nu Aspose.Words voor Java in uw project gaan gebruiken.

### Kan ik documenten in andere formaten splitsen, zoals PDF of DOCX?

Nee, deze handleiding behandelt specifiek het splitsen van documenten in het DOC-formaat met behulp van Aspose.Words voor Java. Als u documenten in andere indelingen moet splitsen, moet u mogelijk andere bibliotheken of tools verkennen die deze indelingen ondersteunen.

### Is Aspose.Words voor Java een gratis bibliotheek?

 Nee, Aspose.Words voor Java is geen gratis bibliotheek. Het is een commercieel product waarvoor licentiekosten gelden. U kunt een bezoek brengen aan de[Aspose.Words voor Java-prijspagina](https://purchase.aspose.com/words/java) voor meer informatie over licentie- en prijsdetails.

### Kan ik documenten opsplitsen in aangepaste paginaformaten en -indelingen?

Ja, u kunt de paginaformaten en -indelingen van de gesplitste documenten aanpassen door de eigenschappen voor de pagina-instelling in Aspose.Words voor Java te wijzigen. Raadpleeg de Aspose.Words-documentatie voor details over hoe u pagina-instellingen kunt aanpassen aan uw vereisten.

### Zijn er beperkingen op het aantal pagina's dat kan worden gesplitst?

Aspose.Words voor Java legt geen specifieke beperkingen op aan het aantal pagina's dat u kunt splitsen. Houd er echter rekening mee dat zeer grote documenten mogelijk meer geheugen en verwerkingstijd vereisen. Houd rekening met systeembronnen wanneer u met grote documenten werkt.

### Hoe kan ik omgaan met kop- en voetteksten bij het splitsen van documenten?

Kop- en voetteksten kunnen worden verwerkt bij het splitsen van documenten met behulp van de Aspose.Words voor Java-bibliotheek. U kunt de kop- en voettekstinhoud van het originele document naar de gesplitste documenten kopiëren, zodat deze correct behouden blijven. Mogelijk moet u dit proces aanpassen op basis van uw specifieke kop- en voettekstvereisten.