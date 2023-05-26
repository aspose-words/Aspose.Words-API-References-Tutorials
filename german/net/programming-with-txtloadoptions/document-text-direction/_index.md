---
title: Dokumenttextrichtung
linktitle: Dokumenttextrichtung
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Textrichtung in Ihren Dokumenten festlegen. Verbessern Sie die Anzeige für Sprachen mit Schreibrichtung von rechts nach links.
type: docs
weight: 10
url: /de/net/programming-with-txtloadoptions/document-text-direction/
---

In diesem Tutorial untersuchen wir den C#-Quellcode, der für die Funktion „Dokumenttextrichtung“ mit Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie die Textrichtung in einem Dokument festlegen. Dies ist besonders nützlich für Sprachen, die von rechts nach links geschrieben werden, wie z. B. Hebräisch oder Arabisch.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Verweise hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Upload-Optionen konfigurieren

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 In diesem Schritt konfigurieren wir die Optionen zum Laden von Dokumenten. Wir schaffen ein Neues`TxtLoadOptions` Objekt und legen Sie das fest`DocumentDirection` Eigentum zu`DocumentDirection.Auto`. Dieser Wert weist Aspose.Words an, die Textrichtung basierend auf dem Inhalt des Dokuments automatisch zu bestimmen.

## Schritt 3: Laden des Dokuments

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 In diesem Schritt laden wir das Dokument mit`Document` -Methode und Übergabe des Pfads zur zu ladenden Textdatei. Darüber hinaus nutzen wir die angegebenen Lademöglichkeiten.

## Schritt 4: Bearbeiten Sie den Absatz und zeigen Sie die Textrichtung an

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 In diesem Schritt greifen wir mit auf den ersten Absatz des Dokuments zu`FirstSection` Und`Body` Eigenschaften. Als nächstes greifen wir auf die zu`ParagraphFormat.Bidi` -Eigenschaft, um die Textrichtung des Absatzes zu ermitteln. Diesen Wert zeigen wir dann in der Konsole an.

## Schritt 5: Speichern Sie das Dokument

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 In diesem letzten Schritt speichern wir das resultierende Dokument im .docx-Format mit`Save` -Methode und Übergabe des Pfads zur Ausgabedatei.

Jetzt können Sie den Quellcode ausführen, um das Textdokument zu laden und die Textrichtung zu bestimmen. Das resultierende Dokument wird im angegebenen Verzeichnis mit dem Namen „WorkingWithTxtLoadOptions.DocumentTextDirection.docx“ gespeichert.

### Beispielquellcode für die Funktionalität zur Dokumenttextrichtung mit Aspose.Words für .NET.


```csharp

            
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Abschluss

In diesem Tutorial haben wir die Dokumenttextrichtungsfunktion in Aspose.Words für .NET untersucht. Wir haben gelernt, wie man die Textrichtung in einem Dokument angibt, insbesondere für Sprachen, die von rechts nach links geschrieben werden, wie etwa Hebräisch oder Arabisch.

Diese Funktion ist wichtig, um sicherzustellen, dass Text in mehrsprachigen Dokumenten korrekt angezeigt wird. Durch die Verwendung der entsprechenden Ladeoptionen kann Aspose.Words die Textrichtung automatisch erkennen und auf das Dokument anwenden.

Mit Aspose.Words können Sie die Textrichtung in Ihren Dokumenten einfach ändern und so den Benutzern ein reibungsloses und intuitives Leseerlebnis bieten.

Es ist wichtig zu beachten, dass diese Funktion besonders nützlich ist, wenn Sie mit Sprachen arbeiten, die eine bestimmte Textrichtung erfordern. Aspose.Words erleichtert diese Aufgabe, indem es leistungsstarke Tools zur Verwaltung der Textrichtung in Ihren Dokumenten bereitstellt.

Denken Sie daran, die entsprechenden Ladeoptionen zu verwenden, z. B. das Festlegen der automatischen Textrichtung, um die gewünschten Ergebnisse in Ihren Dokumenten zu erzielen.

Aspose.Words für .NET bietet viele erweiterte Funktionen für die Dokumentbearbeitung und -generierung. Wenn Sie die von Aspose.Words bereitgestellte Dokumentation und Beispiele weiter erkunden, können Sie die Funktionen dieser leistungsstarken Bibliothek voll ausschöpfen.

Zögern Sie also nicht, die Dokumenttextrichtung in Ihre Aspose.Words für .NET-Projekte zu integrieren und nutzen Sie deren Vorteile, um attraktive und qualitativ hochwertige mehrsprachige Dokumente zu erstellen.