---
title: Usuń spis treści z dokumentu programu Word
linktitle: Usuń spis treści z dokumentu programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak usunąć spis treści z dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/remove-content/remove-table-of-contents/
---
W tym samouczku przeprowadzimy Cię przez proces usuwania spisu treści z dokumentu programu Word przy użyciu biblioteki Aspose.Words dla platformy .NET. Spis treści może czasami być zbędny lub niepotrzebny, a ten kod pomoże Ci go skutecznie usunąć. Udostępnimy przewodnik krok po kroku, który pomoże Ci zrozumieć i wdrożyć kod we własnym projekcie .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Praktyczna znajomość języka programowania C#
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim projekcie
- Dokument programu Word zawierający spis treści, który chcesz usunąć

## Krok 1: Zdefiniuj katalog dokumentów
 Najpierw musisz ustawić ścieżkę katalogu do lokalizacji dokumentu programu Word. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie odpowiednią ścieżką.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Prześlij dokument
 Następnie załadujemy dokument Word do instancji pliku`Document` klasa za pomocą`Load` metoda.

```csharp
// Załaduj dokument
Document doc = new Document(dataDir + "your-document.docx");
```

## Krok 3: Usuń spis treści
 Aby usunąć spis treści, przejdziemy przez typ TOC (spis treści).`FieldStart` węzły w dokumencie. Będziemy przechowywać te węzły, abyśmy mogli szybko uzyskać do nich dostęp i utworzyć listę węzłów do usunięcia.

```csharp
// Przechowuj węzły FieldStart pól spisu treści w dokumencie, aby uzyskać szybki dostęp.
List<FieldStart> fieldStarts = new List<FieldStart>();
// To jest lista przechowująca węzły znalezione w określonym spisie treści. Zostaną one usunięte po zakończeniu tej metody.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Sprawdź, czy istnieje określony indeks spisu treści.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Bezpieczniej jest przechowywać te węzły i na koniec je wszystkie usunąć.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Kiedy napotkamy węzeł FieldEnd typu FieldTOC,
     //wiemy, że dotarliśmy do końca bieżącego spisu treści i na tym się zatrzymujemy.
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


### Przykładowy kod źródłowy narzędzia Usuń spis treści przy użyciu Aspose.Words dla .NET 
```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Załaduj dokument
Document doc = new Document(dataDir + "your-document.docx");

// Przechowuj węzły FieldStart pól spisu treści w dokumencie, aby uzyskać szybki dostęp.
List<FieldStart> fieldStarts = new List<FieldStart>();
// To jest lista przechowująca węzły znalezione w określonym spisie treści. Zostaną one usunięte na końcu tej metody.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Upewnij się, że spis treści określony w przekazanym indeksie istnieje.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Bezpieczniej jest przechowywać te węzły i później usunąć je wszystkie na raz.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Gdy napotkamy węzeł FieldEnd typu FieldTOC,
	// wiemy, że dotarliśmy do końca bieżącego spisu treści i na tym się zatrzymujemy.
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

## Wniosek
W tym samouczku przedstawiliśmy przewodnik krok po kroku dotyczący usuwania spisu treści z dokumentu programu Word przy użyciu biblioteki Aspose.Words dla platformy .NET. Postępując zgodnie z dostarczonym kodem i instrukcjami, możesz łatwo wyeliminować spis treści i poprawić układ swojego dokumentu. Pamiętaj, aby dostosować ścieżkę katalogu i nazwy plików do własnych potrzeb.

### Często zadawane pytania

#### P: Dlaczego powinienem używać Aspose.Words do usuwania spisu treści z dokumentu programu Word?

O: Aspose.Words to potężna i wszechstronna biblioteka klas do manipulowania dokumentami programu Word w aplikacjach .NET. Używając Aspose.Words, możesz skutecznie usunąć spis treści ze swoich dokumentów, co może być przydatne, jeśli spis treści jest zbędny lub niepotrzebny. Pozwala to dostosować zawartość dokumentu i poprawić jego ogólną prezentację.

#### P: Jak przesłać dokument do Aspose.Words dla .NET?

O: Aby usunąć spis treści z dokumentu programu Word, należy najpierw załadować dokument do pamięci przy użyciu metody Load() programu Aspose.Words. Oto przykładowy kod umożliwiający załadowanie dokumentu z określonego katalogu:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "your-document.docx");
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do dokumentu.

#### P: Jak usunąć spis treści z dokumentu za pomocą Aspose.Words?

 Odp.: Aby usunąć spis treści, musisz iterować po`FieldStart` wpisz węzły spisu treści w dokumencie. Możesz zapisać te węzły, aby mieć do nich szybki dostęp, i utworzyć listę węzłów do usunięcia. Oto przykładowy kod:

```csharp
// Przechowuj węzły FieldStart pól spisu treści w dokumencie, aby uzyskać szybki dostęp.
List<FieldStart> fieldStarts = new List<FieldStart>();
//To jest lista przechowująca węzły znalezione w określonym spisie treści. Zostaną one usunięte po zakończeniu tej metody.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Sprawdź, czy istnieje określony indeks spisu treści.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Bezpieczniej jest przechowywać te węzły i na koniec je wszystkie usunąć.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Kiedy napotkamy węzeł FieldEnd typu FieldTOC,
//wiemy, że dotarliśmy do końca bieżącego spisu treści i na tym się zatrzymujemy.
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

#### P: Jak zapisać edytowany dokument w Aspose.Words dla .NET?

Odp.: Po usunięciu spisu treści należy zapisać zmodyfikowany dokument za pomocą metody Save(). Określ żądaną ścieżkę i format pliku wyjściowego (np. DOCX) dla edytowanego dokumentu. Oto przykładowy kod:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```