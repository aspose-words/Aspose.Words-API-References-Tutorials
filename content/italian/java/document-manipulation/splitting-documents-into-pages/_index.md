---
title: Suddivisione di documenti in pagine in Aspose.Words per Java
linktitle: Suddivisione dei documenti in pagine
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come dividere i documenti in pagine utilizzando Aspose.Words per Java. Guida passo passo con codice sorgente per un'elaborazione efficiente dei documenti.
type: docs
weight: 23
url: /it/java/document-manipulation/splitting-documents-into-pages/
---

Se lavori con l'elaborazione di documenti in Java, Aspose.Words per Java è una potente API che può aiutarti a dividere i documenti in pagine separate in modo efficiente. In questo tutorial passo passo ti guideremo attraverso il processo di suddivisione dei documenti utilizzando il codice sorgente fornito. Al termine di questo tutorial sarai in grado di dividere i documenti con facilità, migliorando le tue capacità di gestione dei documenti.

## 1. Introduzione

Aspose.Words for Java è una libreria Java che consente di manipolare i documenti Word a livello di codice. Un'attività comune è suddividere un documento in pagine separate, che può essere utile per vari scopi, come l'archiviazione, la stampa o l'elaborazione dei documenti.

## 2. Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
-  Libreria Aspose.Words per Java, che puoi scaricare[Qui](https://releases.aspose.com/words/java/).

## 3. Configurazione dell'ambiente

Per iniziare, configura il tuo ambiente di sviluppo come segue:

- Crea un progetto Java nel tuo ambiente di sviluppo integrato (IDE) preferito.
- Aggiungi la libreria Aspose.Words per Java al tuo progetto. Puoi fare riferimento a[documentazione](https://reference.aspose.com/words/java/) per istruzioni dettagliate.

## 4. Comprendere il codice sorgente

Il codice sorgente che hai fornito è progettato per dividere un documento in pagine separate. Analizziamo i componenti chiave:

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- Estraiamo il nome base e l'estensione del documento di input.
- Carichiamo il documento utilizzando Aspose.Words per Java.

## 5. Dividere i documenti passo dopo passo

### 5.1. Caricamento del documento

```java
Document doc = new Document(docName);
```

 In questo passaggio, carichiamo il documento di input in un file`Document` object, che ci consente di lavorare con il contenuto del documento.

### 5.2. Inizializzazione di DocumentPageSplitter

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

 Inizializziamo a`DocumentPageSplitter` oggetto con il nostro documento caricato. Questa classe è fornita da Aspose.Words per Java e ci aiuta a dividere il documento in pagine.

### 5.3. Salvataggio di ogni pagina

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

In questo passaggio, iteriamo su ogni pagina del documento e la salviamo come documento separato. È possibile specificare il percorso della directory in cui verranno salvate le pagine divise.

## 6. Esecuzione del codice

Per eseguire correttamente questo codice, assicurati di aver configurato il tuo ambiente e aggiunto la libreria Aspose.Words per Java al tuo progetto. Quindi, esegui il codice e il tuo documento sarà diviso in pagine separate.

## Codice sorgente DocumentPageSplitter

```java
/// <riepilogo>
/// Divide un documento in più documenti, uno per pagina.
///</summary>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <riepilogo>
/// Inizializza una nuova istanza della classe <see cref="DocumentPageSplitter"/>.
/// Questo metodo divide il documento in sezioni in modo che ogni pagina inizi e termini in corrispondenza di un limite di sezione.
/// Si consiglia di non modificare successivamente il documento.
///</summary>
/// <param name="source">Documento di origine</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <riepilogo>
/// Ottiene il documento di una pagina.
///</summary>
/// <param name="pageIndex">
/// Indice in base 1 di una pagina.
///</param>
/// <restituisce>
/// Il <see cref="Documento"/>.
///</returns>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <riepilogo>
/// Ottiene il documento di un intervallo di pagine.
///</summary>
//<param name="startIndex">
/// Indice in base 1 della pagina iniziale.
///</param>
/// <param name="endIndex">
/// Indice in base 1 della pagina finale.
///</param>
/// <restituisce>
/// Il <see cref="Documento"/>.
///</returns>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <riepilogo>
/// Fornisce metodi per estrarre i nodi di un documento di cui viene eseguito il rendering su pagine specificate.
///</summary>
class PageNumberFinder
{
// Associa il nodo ai numeri di pagina iniziale/finale.
// Viene utilizzato per sovrascrivere i numeri di pagina di base forniti dal raccoglitore quando il documento viene diviso.
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
// Associa il numero di pagina a un elenco di nodi trovati su quella pagina.
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <riepilogo>
/// Inizializza una nuova istanza della classe <see cref="PageNumberFinder"/>.
///</summary>
/// <param name="collector">Un'istanza del raccoglitore che dispone di record del modello di layout per il documento.</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <riepilogo>
/// Recupera l'indice in base 1 di una pagina su cui inizia il nodo.
///</summary>
/// <param nome="nodo">
/// Il nodo.
///</param>
/// <restituisce>
/// Indice delle pagine.
///</returns>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <riepilogo>
/// Recupera l'indice in base 1 di una pagina su cui termina il nodo.
///</summary>
/// <param nome="nodo">
/// Il nodo.
///</param>
/// <restituisce>
/// Indice delle pagine.
///</returns>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <riepilogo>
//Restituisce il numero di pagine su cui si estende il nodo specificato. Restituisce 1 se il nodo è contenuto in una pagina.
///</summary>
/// <param nome="nodo">
/// Il nodo.
///</param>
/// <restituisce>
/// Indice delle pagine.
///</returns>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <riepilogo>
/// Restituisce un elenco di nodi contenuti in qualsiasi punto della pagina o delle pagine specificate che corrispondono al tipo di nodo specificato.
///</summary>
/// <param name="startPage">
/// La pagina iniziale.
///</param>
/// <param name="endPage">
/// La pagina finale.
///</param>
/// <param name="nodeType">
///Il tipo di nodo.
///</param>
/// <restituisce>
/// <see cref="IList{T}"/>.
///</returns>
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
		// Alcune pagine possono essere vuote.
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
/// <riepilogo>
/// Divide i nodi visualizzati su due o più pagine in nodi separati in modo che vengano comunque visualizzati nello stesso modo
/// ma non appaiono più su una pagina.
///</summary>
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
	// Visita tutti i compositi che sono eventualmente suddivisi su pagine e dividili in nodi separati.
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <riepilogo>
/// Viene chiamato da <see cref="SectionSplitter"/> per aggiornare i numeri di pagina dei nodi divisi.
///</summary>
/// <param nome="nodo">
/// Il nodo.
///</param>
/// <param name="startPage">
/// La pagina iniziale.
///</param>
/// <param name="endPage">
/// La pagina finale.
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
	// Aggiungi ciascun nodo a un elenco che rappresenta i nodi trovati su ciascuna pagina.
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//Le intestazioni/piè di pagina seguono le sezioni e non sono divisi da soli.
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
/// <riepilogo>
/// Divide il testo della sequenza specificata in due sequenze.
/// Inserisce la nuova esecuzione subito dopo l'esecuzione specificata.
///</summary>
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
/// <riepilogo>
/// Divide un documento in più sezioni in modo che ogni pagina inizi e termini in corrispondenza del limite di una sezione.
///</summary>
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
	// Se è presente una sezione precedente, prova a copiare eventuali piè di pagina di intestazione collegati.
	// Altrimenti non appariranno nel documento estratto se manca la sezione precedente.
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
	// Se il paragrafo contiene solo interruzioni di sezione, aggiungi un falso inseguimento.
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
		// Rimuovi la numerazione dell'elenco dal paragrafo clonato ma lascia lo stesso rientro
		// poiché il paragrafo dovrebbe far parte dell'articolo precedente.
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		// Reimposta la spaziatura dei paragrafi divisi nelle tabelle poiché una spaziatura aggiuntiva potrebbe farli apparire diversi.
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
		// Corregge l'interruzione di pagina alla fine della sezione.
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	// Aggiungi una nuova numerazione delle pagine anche per il corpo della sezione.
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
	// Un nodo può estendersi su più pagine, quindi viene restituito un elenco di posizioni divise.
	//Il nodo diviso è il primo nodo nella pagina successiva.
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
		// Se la pagina del nodo figlio è cambiata, questa è la posizione divisa.
		// Aggiungi questo alla lista.
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
	// Dividi i compositi all'indietro, in modo che i nodi clonati vengano inseriti nell'ordine corretto.
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	// Sposta tutti i nodi trovati nella pagina successiva nel nodo copiato. Gestire i nodi delle righe separatamente.
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
		// Se abbiamo a che fare con una riga, dobbiamo aggiungere celle fittizie per la riga clonata.
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
	// Inserisci il nodo diviso dopo l'originale.
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	// Aggiorna i nuovi numeri di pagina del nodo base e del nodo clonato, inclusi i suoi discendenti.
	// Questa sarà solo una singola pagina poiché il composito clonato è diviso per essere su una pagina.
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

## Conclusione

Ora hai imparato come dividere un documento in pagine separate utilizzando Aspose.Words per Java. Questa guida fornisce un tutorial completo passo passo con esempi di codice sorgente. Puoi personalizzare ed estendere ulteriormente questo codice per soddisfare i tuoi requisiti specifici quando lavori con i documenti.
Certamente! Aggiungiamo una sezione FAQ alla nostra guida sulla suddivisione dei documenti in pagine utilizzando Aspose.Words per Java.

## Domande frequenti

### Come posso aggiungere Aspose.Words per Java al mio progetto?

Per aggiungere Aspose.Words per Java al tuo progetto, procedi nel seguente modo:

1.  Scarica la libreria Aspose.Words per Java da[Qui](https://releases.aspose.com/words/java/).
2. Aggiungi il file JAR scaricato al classpath del tuo progetto.
3. Ora puoi iniziare a utilizzare Aspose.Words per Java nel tuo progetto.

### Posso dividere documenti in altri formati, come PDF o DOCX?

No, questa guida copre specificamente la suddivisione dei documenti nel formato DOC utilizzando Aspose.Words per Java. Se devi dividere documenti in altri formati, potresti dover esplorare altre librerie o strumenti che supportano tali formati.

### Aspose.Words per Java è una libreria gratuita?

 No, Aspose.Words per Java non è una libreria gratuita. È un prodotto commerciale a pagamento. Puoi visitare il[Aspose.Words per la pagina dei prezzi Java](https://purchase.aspose.com/words/java) per ulteriori informazioni sulla licenza e sui dettagli sui prezzi.

### Posso dividere i documenti in dimensioni e formati di pagina personalizzati?

Sì, puoi personalizzare le dimensioni e i formati della pagina dei documenti divisi modificando le proprietà di impostazione della pagina in Aspose.Words per Java. Fare riferimento alla documentazione di Aspose.Words per i dettagli su come personalizzare le impostazioni della pagina in base alle proprie esigenze.

### Ci sono limitazioni sul numero di pagine che possono essere divise?

Aspose.Words per Java non impone limitazioni specifiche sul numero di pagine che puoi dividere. Tuttavia, tieni presente che documenti molto grandi potrebbero richiedere più memoria e tempo di elaborazione. Prestare attenzione alle risorse di sistema quando si lavora con documenti di grandi dimensioni.

### Come posso gestire intestazioni e piè di pagina durante la divisione dei documenti?

Intestazioni e piè di pagina possono essere gestiti durante la divisione dei documenti utilizzando la libreria Aspose.Words per Java. Puoi copiare il contenuto di intestazione e piè di pagina dal documento originale ai documenti divisi, assicurandoti che vengano conservati correttamente. Potrebbe essere necessario personalizzare questo processo in base ai requisiti specifici di intestazione e piè di pagina.