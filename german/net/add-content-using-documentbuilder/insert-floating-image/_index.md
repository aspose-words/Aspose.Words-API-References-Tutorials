---
title: Fügen Sie ein schwebendes Bild in ein Word-Dokument ein
linktitle: Fügen Sie ein schwebendes Bild in ein Word-Dokument ein
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET schwebende Bilder in Word-Dokumente einfügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-floating-image/
---
In diesem umfassenden Beispiel erfahren Sie, wie Sie mit Aspose.Words für .NET ein schwebendes Bild in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieser Anleitung werden Sie in der Lage sein, Bilder mit anpassbaren Positionierungs- und Umbruchoptionen zu Ihren Dokumenten hinzuzufügen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie ein schwebendes Bild ein
Als nächstes verwenden Sie die InsertImage-Methode der DocumentBuilder-Klasse, um ein schwebendes Bild einzufügen. Geben Sie den Pfad der Bilddatei, die relative horizontale und vertikale Position, Breite, Höhe und Umbruchoptionen als Parameter an:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Schritt 3: Speichern Sie das Dokument
Nachdem Sie das schwebende Bild eingefügt haben, speichern Sie das Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Beispielquellcode zum Einfügen eines schwebenden Bildes mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen eines schwebenden Bildes mit Aspose.Words für .NET:
Schwebende Bilder sind für verschiedene Szenarien nützlich, beispielsweise zum Hinzufügen von Logos, Illustrationen oder dekorativen Elementen, die unabhängig vom Text des Dokuments positioniert werden können.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

Denken Sie daran, den Code entsprechend Ihren spezifischen Anforderungen anzupassen, einschließlich des Bilddateipfads und der gewünschten Positionierungs- und Umbruchoptionen.

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET ein schwebendes Bild in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie Ihre Dokumente jetzt mit optisch ansprechenden und anpassbaren schwebenden Bildern verbessern.

### FAQs zum Einfügen eines schwebenden Bildes in ein Word-Dokument

#### F: Kann ich mehrere schwebende Bilder in ein einzelnes Dokument einfügen?

A: Auf jeden Fall! Mit Aspose.Words für .NET können Sie beliebig viele schwebende Bilder in ein Word-Dokument einfügen. Wiederholen Sie einfach den Einfügevorgang, um mehrere optisch ansprechende Bilder hinzuzufügen.

#### F: Welche Umbruchoptionen stehen für das schwebende Bild zur Verfügung?

A: Aspose.Words für .NET bietet verschiedene Umbruchoptionen für schwebende Bilder, darunter „Quadrat“, „Enge“, „Durch“, „Oben Unten“ und „Keine“. Diese Optionen bestimmen, wie der Text mit dem schwebenden Bild interagiert.

#### F: Kann ich die Größe des schwebenden Bildes anpassen?

A: Auf jeden Fall! Sie können die Breite und Höhe des schwebenden Bildes mithilfe der entsprechenden Parameter in der Methode InsertImage angeben. Dadurch können Sie die Abmessungen des Bildes entsprechend Ihren Designvorlieben steuern.

#### F: Kann ich das schwebende Bild relativ zu einem bestimmten Element im Dokument positionieren?

A: Ja, mit Aspose.Words für .NET können Sie das schwebende Bild relativ zu bestimmten Elementen wie dem Rand, der Seite, dem Absatz oder der Tabelle positionieren. Sie können die entsprechenden relativen horizontalen und vertikalen Positionsparameter auswählen, um die gewünschte Platzierung zu erreichen.

#### F: Ist Aspose.Words für .NET sowohl für Desktop- als auch für Webanwendungen geeignet?

A: Ja, Aspose.Words für .NET ist eine vielseitige Bibliothek, die sowohl für Desktop- als auch für Webanwendungen geeignet ist. Unabhängig davon, ob Sie eine Windows-Anwendung oder ein webbasiertes System erstellen, können Sie die Bibliothek mühelos integrieren.
