---
title: Fügen Sie ein schwebendes Bild in ein Word-Dokument ein
linktitle: Fügen Sie ein schwebendes Bild in ein Word-Dokument ein
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie in dieser detaillierten Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET ein schwebendes Bild in ein Word-Dokument einfügen. Perfekt zur Aufwertung Ihrer Dokumente.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-floating-image/
---
## Einführung

Stellen Sie sich vor, Sie erstellen einen beeindruckenden Bericht oder Vorschlag, bei dem die Bilder perfekt positioniert sind, um Ihren Text zu ergänzen. Mit Aspose.Words für .NET können Sie dies mühelos erreichen. Diese Bibliothek bietet leistungsstarke Funktionen für die Dokumentbearbeitung und ist damit eine Lösung der Wahl für Entwickler. In diesem Tutorial konzentrieren wir uns auf das Einfügen eines schwebenden Bildes mithilfe der DocumentBuilder-Klasse. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, dieser Leitfaden führt Sie durch jeden Schritt.

## Voraussetzungen

Bevor wir loslegen, stellen wir sicher, dass Sie über alles verfügen, was Sie für den Einstieg benötigen:

1.  Aspose.Words für .NET: Sie können die Bibliothek von herunterladen[Aspose-Veröffentlichungsseite](https://releases.aspose.com/words/net/).
2. Visual Studio: Jede Version, die die .NET-Entwicklung unterstützt.
3. Grundkenntnisse in C#: Das Verständnis der Grundlagen der C#-Programmierung ist hilfreich.
4. Bilddatei: Eine Bilddatei, die Sie einfügen möchten, beispielsweise ein Logo oder ein Bild.

## Namespaces importieren

Um Aspose.Words in Ihrem Projekt verwenden zu können, müssen Sie die erforderlichen Namespaces importieren. Fügen Sie dazu am Anfang Ihrer C#-Datei die folgenden Zeilen hinzu:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Nachdem diese Voraussetzungen und Namespaces erfüllt sind, können wir mit unserem Tutorial beginnen.

Lassen Sie uns den Prozess des Einfügens eines schwebenden Bildes in ein Word-Dokument in überschaubare Schritte unterteilen. Jeder Schritt wird im Detail erklärt, um sicherzustellen, dass Sie ihn ohne Probleme befolgen können.

## Schritt 1: Richten Sie Ihr Projekt ein

Erstellen Sie zunächst ein neues C#-Projekt in Visual Studio. Der Einfachheit halber können Sie eine Konsolen-App wählen.

1. Öffnen Sie Visual Studio und erstellen Sie ein neues Projekt.
2. Wählen Sie „Konsolen-App (.NET Core)“ und klicken Sie auf „Weiter“.
3. Benennen Sie Ihr Projekt und wählen Sie einen Speicherort aus. Klicken Sie auf „Erstellen“.
4. Installieren Sie Aspose.Words für .NET über den NuGet Package Manager. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt, wählen Sie „NuGet-Pakete verwalten“ und suchen Sie nach „Apose.Words“. Installieren Sie die neueste Version.

## Schritt 2: Initialisieren Sie Document und DocumentBuilder

Nachdem Ihr Projekt nun eingerichtet ist, initialisieren wir die Objekte Document und DocumentBuilder.

1.  Erstellen Sie eine neue Instanz von`Document` Klasse:

```csharp
Document doc = new Document();
```

2. Initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Der`Document` Das Objekt stellt das Word-Dokument dar und das`DocumentBuilder` hilft beim Hinzufügen von Inhalten.

## Schritt 3: Definieren Sie den Bildpfad

Geben Sie als Nächstes den Pfad zu Ihrer Bilddatei an. Stellen Sie sicher, dass Ihr Bild über das Verzeichnis Ihres Projekts zugänglich ist.

Definieren Sie das Bildverzeichnis und den Namen der Bilddatei:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imagePath = dataDir + "Transparent background logo.png";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad, in dem Ihr Bild gespeichert ist.

## Schritt 4: Fügen Sie das schwebende Bild ein

Wenn alles eingerichtet ist, fügen wir das schwebende Bild in das Dokument ein.

 Benutzen Sie die`InsertImage` Methode der`DocumentBuilder` Klasse zum Einfügen des Bildes:

```csharp
builder.InsertImage(imagePath,
   RelativeHorizontalPosition.Margin,
   100,
   RelativeVerticalPosition.Margin,
   100,
   200,
   100,
   WrapType.Square);
```

Hier ist, was jeder Parameter bedeutet:
- `imagePath`Der Pfad zu Ihrer Bilddatei.
- `RelativeHorizontalPosition.Margin`: Die horizontale Position relativ zum Rand.
- `100`: Der horizontale Versatz vom Rand (in Punkten).
- `RelativeVerticalPosition.Margin`: Die vertikale Position relativ zum Rand.
- `100`: Der vertikale Versatz vom Rand (in Punkten).
- `200`: Die Breite des Bildes (in Punkten).
- `100`: Die Höhe des Bildes (in Punkten).
- `WrapType.Square`: Der Textumbruchstil um das Bild.

## Schritt 5: Speichern Sie das Dokument

Speichern Sie das Dokument abschließend am gewünschten Ort.

1. Geben Sie den Pfad der Ausgabedatei an:

```csharp
string outputPath = dataDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx";
```

2. Speichern Sie das Dokument:

```csharp
doc.Save(outputPath);
```

Ihr Word-Dokument mit dem schwebenden Bild ist jetzt fertig!

## Abschluss

Das Einfügen eines schwebenden Bildes in ein Word-Dokument mit Aspose.Words für .NET ist ein unkomplizierter Vorgang, wenn er in überschaubare Schritte unterteilt wird. Wenn Sie dieser Anleitung folgen, können Sie Ihren Dokumenten professionell aussehende Bilder hinzufügen und so deren visuelle Attraktivität steigern. Aspose.Words bietet eine robuste API, die die Bearbeitung von Dokumenten zum Kinderspiel macht, unabhängig davon, ob Sie an Berichten, Vorschlägen oder anderen Dokumenttypen arbeiten.

## FAQs

### Kann ich mit Aspose.Words für .NET mehrere Bilder einfügen?

 Ja, Sie können mehrere Bilder einfügen, indem Sie den Vorgang wiederholen`InsertImage` Methode für jedes Bild mit den gewünschten Parametern.

### Wie ändere ich die Position des Bildes?

 Sie können die anpassen`RelativeHorizontalPosition`, `RelativeVerticalPosition`und Offset-Parameter, um das Bild nach Bedarf zu positionieren.

### Welche anderen Wrap-Typen sind für Bilder verfügbar?

 Aspose.Words unterstützt verschiedene Wrap-Typen wie z`Inline`, `TopBottom`, `Tight`, `Through`, und mehr. Sie können diejenige auswählen, die am besten zu Ihrem Dokumentlayout passt.

### Kann ich verschiedene Bildformate verwenden?

Ja, Aspose.Words unterstützt eine Vielzahl von Bildformaten, darunter JPEG, PNG, BMP und GIF.

### Wie erhalte ich eine kostenlose Testversion von Aspose.Words für .NET?

 Sie können eine kostenlose Testversion von erhalten[Aspose kostenlose Testseite](https://releases.aspose.com/).