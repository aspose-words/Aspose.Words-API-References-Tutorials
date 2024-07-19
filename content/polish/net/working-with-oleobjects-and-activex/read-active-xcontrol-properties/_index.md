---
title: Przeczytaj właściwości Active XControl z pliku Word
linktitle: Przeczytaj właściwości Active XControl z pliku Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przeczytaj właściwości kontrolek ActiveX w pliku Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

W tym przewodniku krok po kroku pokażemy, jak odczytać właściwości kontrolek ActiveX w pliku Word za pomocą Aspose.Words dla .NET. Dostarczymy Ci pełny kod źródłowy i pokażemy, jak sformatować wynik przeceny.

## Krok 1: Inicjalizacja dokumentu

 Pierwszym krokiem jest inicjalizacja pliku`Document` obiektu, ładując dokument programu Word zawierający kontrolki ActiveX. Pamiętaj o wymianie`MyDir` z rzeczywistą ścieżką do katalogu zawierającego dokument.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Krok 2: Odzyskaj kontrolki ActiveX

 Na tym etapie będziemy iterować po każdym z nich`Shape` dokumentu, aby pobrać kontrolki ActiveX i przeczytać ich właściwości.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Przykładowy kod źródłowy dla właściwości Read Active XControl przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do odczytywania właściwości formantów ActiveX przy użyciu Aspose.Words dla .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## Wniosek

Ten przewodnik pokazał, jak czytać właściwości kontrolek ActiveX w pliku Word przy użyciu Aspose.Words dla .NET. Wykonując opisane kroki, możesz zainicjować dokument, pobrać kontrolki ActiveX i odczytać ich właściwości. Skorzystaj z dostarczonego przykładowego kodu jako punktu wyjścia i dostosuj go do swoich konkretnych potrzeb.

Odczytywanie właściwości formantów ActiveX umożliwia wyodrębnienie ważnych informacji z plików programu Word zawierających te kontrolki. Aspose.Words dla .NET oferuje zaawansowane funkcje przetwarzania tekstu z kontrolkami ActiveX i automatyzację przetwarzania dokumentów.

### Często zadawane pytania

#### P: Jaki jest pierwszy krok w celu odczytania właściwości kontrolek ActiveX w pliku Word?

 Odp.: Pierwszym krokiem jest inicjalizacja pliku`Document` obiektu, ładując dokument programu Word zawierający kontrolki ActiveX. Pamiętaj o wymianie`MyDir` z rzeczywistą ścieżką do katalogu zawierającego dokument.

#### P: Jak umieścić kontrolki ActiveX w dokumencie?

 O: Aby odzyskać kontrolki ActiveX, musisz iterować po każdym z nich`Shape` dokumentu i sprawdź, czy jest to formant ActiveX. Użyj`OleFormat` własność`Shape` aby uzyskać dostęp do`OleControl` obiekt i pobierz niezbędne właściwości.

#### P: Jakie właściwości kontrolek ActiveX mogę odczytać?

O: Można odczytać różne właściwości formantów ActiveX, takie jak podpis, wartość, stan włączenia lub wyłączenia, typ i węzły podrzędne powiązane z kontrolką.

#### P: Jak mogę uzyskać całkowitą liczbę kontrolek ActiveX w dokumencie?

 O: Aby uzyskać całkowitą liczbę formantów ActiveX w dokumencie, możesz użyć metody`GetChildNodes` metoda`Document` obiekt określający`NodeType.Shape` typ i łącznie z węzłami podrzędnymi.