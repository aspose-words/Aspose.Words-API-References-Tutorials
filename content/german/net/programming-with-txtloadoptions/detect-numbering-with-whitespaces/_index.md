---
title: Nummerierung mit Leerzeichen erkennen
linktitle: Nummerierung mit Leerzeichen erkennen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Listennummern mit Leerzeichen in Aspose.Words für .NET erkennen. Verbessern Sie mühelos die Struktur Ihrer Dokumente.
type: docs
weight: 10
url: /de/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
In diesem Tutorial untersuchen wir den C#-Quellcode, der für die Funktion „Erkennung von Nummerierungen mit Leerzeichen“ mit Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie Listen aus einem Textdokument erkennen und erstellen, das Listennummern gefolgt von Leerzeichen enthält.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Verweise hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Erstellen des Textdokuments

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

In diesem Schritt erstellen wir eine Textzeichenfolge, die ein Textdokument simuliert, das Listennummern gefolgt von Leerzeichen enthält. Wir verwenden verschiedene Listentrennzeichen wie Punkt, rechte Klammer, Aufzählungszeichen und Leerzeichen.

## Schritt 3: Upload-Optionen konfigurieren

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 In diesem Schritt konfigurieren wir die Optionen zum Laden von Dokumenten. Wir schaffen ein Neues`TxtLoadOptions` Objekt und legen Sie das fest`DetectNumberingWithWhitespaces` Eigentum zu`true`. Dadurch kann Aspose.Words Listennummern erkennen, auch wenn ihnen Leerzeichen folgen.

## Schritt 4: Dokument laden und speichern

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 In diesem Schritt laden wir das Dokument mit der angegebenen Textzeichenfolge und den angegebenen Ladeoptionen. Wir benutzen ein`MemoryStream` um die Textzeichenfolge in einen Speicherstream umzuwandeln. Anschließend speichern wir das resultierende Dokument im .docx-Format.

### Beispielquellcode für die Funktion zur Erkennung von Leerraumnummern mit Aspose.Words für .NET.

```csharp

            
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Erstellen Sie ein Klartextdokument in Form einer Zeichenfolge mit Teilen, die als Listen interpretiert werden können.
// Beim Laden werden die ersten drei Listen immer von Aspose.Words erkannt.
// Für sie werden nach dem Laden Listenobjekte erstellt.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// Die vierte Liste mit Leerzeichen zwischen der Listennummer und dem Inhalt des Listenelements,
// wird nur dann als Liste erkannt, wenn „DetectNumberingWithWhitespaces“ in einem LoadOptions-Objekt auf true gesetzt ist,
// um zu vermeiden, dass Absätze, die mit Zahlen beginnen, fälschlicherweise als Listen erkannt werden.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Laden Sie das Dokument, während Sie LoadOptions als Parameter anwenden, und überprüfen Sie das Ergebnis.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Jetzt können Sie den Quellcode ausführen, um das Textdokument zu laden, das Listennummern mit Leerzeichen enthält, und dann ein DOCX-Dokument mit den erkannten Listen erstellen. Die Ausgabedatei wird im angegebenen Verzeichnis mit dem Namen „WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx“ gespeichert.

## Abschluss
In diesem Tutorial haben wir die Funktion zur Erkennung von Leerzeichennummern in Aspose.Words für .NET untersucht. Wir haben gelernt, wie man Listen aus einem Textdokument erstellt, das Listennummern gefolgt von Leerzeichen enthält.

Diese Funktion ist äußerst nützlich für die Verarbeitung von Dokumenten, die Listennummern enthalten, die auf unterschiedliche Weise formatiert sind. Durch die Verwendung der entsprechenden Ladeoptionen ist Aspose.Words in der Lage, diese Listennummern zu erkennen, auch wenn ihnen Leerzeichen folgen, und sie im endgültigen Dokument in strukturierte Listen umzuwandeln.

Mit dieser Funktion können Sie Zeit sparen und die Effizienz Ihres Arbeitsablaufs verbessern. Sie können problemlos Informationen aus Textdokumenten extrahieren und diese in gut strukturierte Dokumente mit geeigneten Listen umwandeln.

Denken Sie daran, Ladeoptionen in Betracht zu ziehen, z. B. die Konfiguration der Leerraumwahlerkennung, um die gewünschten Ergebnisse zu erzielen.

Aspose.Words für .NET bietet viele erweiterte Funktionen für die Dokumentbearbeitung und -generierung. Wenn Sie die von Aspose.Words bereitgestellte Dokumentation und Beispiele weiter erkunden, können Sie die Funktionen dieser leistungsstarken Bibliothek voll ausschöpfen.

Zögern Sie also nicht, die Erkennung von Leerzeichennummern in Ihre Aspose.Words für .NET-Projekte zu integrieren und nutzen Sie deren Vorteile, um gut strukturierte und lesbare Dokumente zu erstellen.


