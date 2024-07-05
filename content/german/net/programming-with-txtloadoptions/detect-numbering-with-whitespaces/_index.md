---
title: Nummerierung mit Leerzeichen erkennen
linktitle: Nummerierung mit Leerzeichen erkennen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Listennummern mit Leerzeichen in Aspose.Words für .NET erkennen. Verbessern Sie mühelos die Struktur Ihrer Dokumente.
type: docs
weight: 10
url: /de/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
In diesem Tutorial untersuchen wir den C#-Quellcode, der für die Funktion „Erkennung von Nummerierungen mit Leerzeichen“ mit Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie Listen aus einem Textdokument erkennen und erstellen, das Listennummern gefolgt von Leerzeichen enthält.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Erstellen des Textdokuments

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
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

 In diesem Schritt konfigurieren wir die Dokumentladeoptionen. Wir erstellen ein neues`TxtLoadOptions` Objekt und setzen Sie den`DetectNumberingWithWhitespaces`Eigentum an`true`. Dadurch kann Aspose.Words Listennummern erkennen, auch wenn auf diese Leerzeichen folgen.

## Schritt 4: Dokument laden und speichern

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 In diesem Schritt laden wir das Dokument mit der angegebenen Textzeichenfolge und den Ladeoptionen. Wir verwenden eine`MemoryStream` um die Textzeichenfolge in einen Speicherstrom umzuwandeln. Anschließend speichern wir das resultierende Dokument im DOCX-Format.

### Beispiel-Quellcode für die Funktion zur Erkennung von Leerzeichen bei der Nummerierung mit Aspose.Words für .NET.

```csharp

            
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Erstellen Sie ein Klartextdokument in Form einer Zeichenfolge mit Teilen, die als Listen interpretiert werden können.
// Beim Laden werden die ersten drei Listen immer von Aspose.Words erkannt,
// und nach dem Laden werden Listenobjekte für sie erstellt.
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

// Die vierte Liste, mit Leerzeichen zwischen der Listennummer und dem Inhalt des Listenelements,
// wird nur dann als Liste erkannt, wenn "DetectNumberingWithWhitespaces" in einem LoadOptions-Objekt auf true gesetzt ist,
// um zu vermeiden, dass Absätze, die mit Zahlen beginnen, fälschlicherweise als Listen erkannt werden.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Laden Sie das Dokument, während Sie LoadOptions als Parameter anwenden, und überprüfen Sie das Ergebnis.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Jetzt können Sie den Quellcode ausführen, um das Textdokument mit Listennummern und Leerzeichen zu laden und dann ein .docx-Dokument mit den erkannten Listen zu erstellen. Die Ausgabedatei wird im angegebenen Verzeichnis unter dem Namen „WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx“ gespeichert.

## Abschluss
In diesem Tutorial haben wir die Funktion zur Erkennung von Leerzeichen in Aspose.Words für .NET untersucht. Wir haben gelernt, wie man aus einem Textdokument Listen erstellt, die Listennummern gefolgt von Leerzeichen enthalten.

Diese Funktion ist äußerst nützlich für die Verarbeitung von Dokumenten, die auf unterschiedliche Weise formatierte Listennummern enthalten. Mithilfe der entsprechenden Ladeoptionen kann Aspose.Words diese Listennummern erkennen, auch wenn ihnen Leerzeichen folgen, und sie im endgültigen Dokument in strukturierte Listen umwandeln.

Mit dieser Funktion können Sie Zeit sparen und die Effizienz Ihres Arbeitsablaufs verbessern. Sie können problemlos Informationen aus Textdokumenten extrahieren und diese mit entsprechenden Listen in gut strukturierte Dokumente umwandeln.

Denken Sie daran, Ladeoptionen zu berücksichtigen, z. B. die Konfiguration der Erkennung von Leerzeichen beim Wählen, um die gewünschten Ergebnisse zu erzielen.

Aspose.Words für .NET bietet viele erweiterte Funktionen zur Dokumentbearbeitung und -erstellung. Durch die eingehendere Untersuchung der von Aspose.Words bereitgestellten Dokumentation und Beispiele können Sie die Funktionen dieser leistungsstarken Bibliothek voll ausschöpfen.

Zögern Sie also nicht, die Erkennung von Leerzeichennummerierungen in Ihre Aspose.Words-Projekte für .NET zu integrieren und nutzen Sie die Vorteile, um gut strukturierte und lesbare Dokumente zu erstellen.


