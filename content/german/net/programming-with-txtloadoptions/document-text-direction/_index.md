---
title: Dokumenttextrichtung
linktitle: Dokumenttextrichtung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Textrichtung in Ihren Dokumenten festlegen. Verbessern Sie die Anzeige für Sprachen, die von rechts nach links verlaufen.
type: docs
weight: 10
url: /de/net/programming-with-txtloadoptions/document-text-direction/
---

In diesem Tutorial untersuchen wir den C#-Quellcode, der für die Funktion „Dokumenttextrichtung“ mit Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie die Textrichtung in einem Dokument festlegen, was besonders für Sprachen nützlich ist, die von rechts nach links geschrieben werden, wie Hebräisch oder Arabisch.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Upload-Optionen konfigurieren

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 In diesem Schritt konfigurieren wir die Dokumentladeoptionen. Wir erstellen ein neues`TxtLoadOptions` Objekt und setzen Sie den`DocumentDirection`Eigentum an`DocumentDirection.Auto`. Dieser Wert weist Aspose.Words an, die Textrichtung automatisch basierend auf dem Inhalt des Dokuments zu bestimmen.

## Schritt 3: Dokument einlegen

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 In diesem Schritt laden wir das Dokument mit dem`Document` Methode und Übergabe des Pfads zur zu ladenden Textdatei. Wir verwenden auch die angegebenen Ladeoptionen.

## Schritt 4: Absatz bearbeiten und Textrichtung anzeigen

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 In diesem Schritt greifen wir auf den ersten Absatz des Dokuments zu, indem wir`FirstSection`Und`Body` Eigenschaften. Als nächstes greifen wir auf die`ParagraphFormat.Bidi` Eigenschaft, um die Textrichtung des Absatzes zu erhalten. Wir zeigen diesen Wert dann in der Konsole an.

## Schritt 5: Speichern Sie das Dokument

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

In diesem letzten Schritt speichern wir das resultierende Dokument im .docx-Format mit dem`Save` Methode und Übergabe des Pfads an die Ausgabedatei.

Nun können Sie den Quellcode ausführen, um das Textdokument zu laden und die Textrichtung zu bestimmen. Das resultierende Dokument wird im angegebenen Verzeichnis unter dem Namen „WorkingWithTxtLoadOptions.DocumentTextDirection.docx“ gespeichert.

### Beispiel-Quellcode für die Dokumenttextrichtungsfunktion mit Aspose.Words für .NET.


```csharp

            
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktion zur Dokumenttextrichtung in Aspose.Words für .NET untersucht. Wir haben gelernt, wie man die Textrichtung in einem Dokument angibt, insbesondere für Sprachen, die von rechts nach links geschrieben werden, wie Hebräisch oder Arabisch.

Diese Funktion ist wichtig, um sicherzustellen, dass Text in mehrsprachigen Dokumenten korrekt angezeigt wird. Durch die Verwendung der entsprechenden Ladeoptionen kann Aspose.Words die Textrichtung automatisch erkennen und auf das Dokument anwenden.

Mit Aspose.Words können Sie die Textrichtung in Ihren Dokumenten einfach bearbeiten und den Benutzern so ein reibungsloses und intuitives Leseerlebnis bieten.

Es ist wichtig zu beachten, dass diese Funktion besonders nützlich ist, wenn Sie mit Textverarbeitungssprachen arbeiten, die eine bestimmte Textrichtung erfordern. Aspose.Words erleichtert diese Aufgabe, indem es leistungsstarke Tools zur Verwaltung der Textrichtung in Ihren Dokumenten bereitstellt.

Denken Sie daran, die entsprechenden Ladeoptionen zu verwenden, z. B. die automatische Textrichtung festzulegen, um in Ihren Dokumenten die gewünschten Ergebnisse zu erzielen.

Aspose.Words für .NET bietet viele erweiterte Funktionen zur Dokumentbearbeitung und -erstellung. Durch die eingehendere Untersuchung der von Aspose.Words bereitgestellten Dokumentation und Beispiele können Sie die Funktionen dieser leistungsstarken Bibliothek voll ausschöpfen.

Zögern Sie also nicht, die Dokumenttextrichtung in Ihre Aspose.Words-Projekte für .NET zu integrieren und nutzen Sie die Vorteile, um attraktive und qualitativ hochwertige mehrsprachige Dokumente zu erstellen.