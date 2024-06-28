---
title: Zusammenführungsfeld mithilfe von DOM einfügen
linktitle: Zusammenführungsfeld mithilfe von DOM einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie in diesem umfassenden Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.Words für .NET Zusammenführungsfelder in Word-Dokumente einfügen und konfigurieren.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-merge-field-using-dom/
---

Wenn Sie mit der Dokumentverarbeitung in .NET arbeiten, sind Sie wahrscheinlich auf Aspose.Words gestoßen. Diese leistungsstarke Bibliothek bietet eine breite Palette von Funktionen zur programmgesteuerten Bearbeitung von Word-Dokumenten. In diesem Tutorial konzentrieren wir uns auf eine bestimmte Funktion: das Einfügen eines Briefvorlagenfelds mithilfe des Document Object Model (DOM) in Aspose.Words für .NET. Dieser Leitfaden führt Sie durch jeden Schritt, von der Einrichtung Ihrer Umgebung bis zum Einfügen und Aktualisieren eines Seriendruckfelds in einem Word-Dokument.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen wir sicher, dass Sie über alles verfügen, was Sie für dieses Tutorial benötigen.

1. **Basic Knowledge of C#:** Sie sollten mit der C#-Programmierung vertraut sein.
2. **Visual Studio Installed:** Stellen Sie sicher, dass Visual Studio oder eine andere C#-IDE auf Ihrem Computer installiert ist.
3. **Aspose.Words for .NET:** Laden Sie die neueste Version von Aspose.Words für .NET herunter und installieren Sie sie[Veröffentlichungen](https://releases.aspose.com/words/net/).
4. **Valid License:** Wenn Sie keine Lizenz haben, können Sie eine bekommen[temporäre Lizenz](https://purchase.aspose.com/temporary-license/) zur Auswertung.

## Schritt 1: Richten Sie Ihr Projekt ein

Als Erstes richten wir ein neues Projekt in Visual Studio ein.

1. **Open Visual Studio.**
2. **Create a New Project:** Gehen Sie zu Datei > Neu > Projekt. Wählen Sie eine C#-Konsolen-App aus.
3. **Name Your Project:** Geben Sie Ihrem Projekt einen aussagekräftigen Namen und klicken Sie auf Erstellen.

## Schritt 2: Installieren Sie Aspose.Words

Um Aspose.Words verwenden zu können, müssen Sie es Ihrem Projekt hinzufügen. Dies kann über den NuGet Package Manager erfolgen.

1. **Open NuGet Package Manager:** Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie dann NuGet-Pakete verwalten aus.
2. **Search for Aspose.Words:** Suchen Sie im NuGet-Paketmanager nach „Apose.Words“.
3. **Install the Package:** Klicken Sie auf „Installieren“, um Aspose.Words zu Ihrem Projekt hinzuzufügen.

## Schritt 3: Namespaces importieren

Um Aspose.Words verwenden zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. So können Sie es machen:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## Schritt 4: Initialisieren Sie Ihr Dokument

Nachdem nun alles eingerichtet ist, erstellen wir ein neues Word-Dokument und initialisieren den DocumentBuilder.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 5: Bewegen Sie den Cursor auf einen bestimmten Absatz

Als nächstes müssen wir den Cursor zu einem bestimmten Absatz im Dokument bewegen, in dem wir das Zusammenführungsfeld einfügen möchten.

```csharp
// Bewegen Sie den Cursor zum Absatz.
builder.MoveToParagraph(2, 0);
```

## Schritt 6: Fügen Sie das Zusammenführungsfeld ein

 Das Einfügen eines Zusammenführungsfelds ist unkompliziert. Wir werden das verwenden`InsertField` Methode der`DocumentBuilder` Klasse.

```csharp
// Feldzusammenführungsfeld einfügen.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

## Schritt 7: Konfigurieren Sie das Zusammenführungsfeld

Nachdem Sie das Zusammenführungsfeld eingefügt haben, können Sie verschiedene Eigenschaften festlegen, um es entsprechend Ihren Anforderungen zu konfigurieren.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field.TextAfter = "Test3";
field.IsMapped = true;
field.IsVerticalFormatting = true;
```

## Schritt 8: Aktualisieren und speichern Sie das Dokument

Aktualisieren Sie abschließend das Feld, um sicherzustellen, dass alle Einstellungen übernommen werden, und speichern Sie das Dokument.

```csharp
// Aktualisieren Sie das Feld.
field.Update();

// Speichern Sie das Dokument.
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## Abschluss

Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Words für .NET problemlos Zusammenführungsfelder in ein Word-Dokument einfügen und konfigurieren. In diesem Tutorial wurden die wesentlichen Schritte vom Einrichten Ihrer Umgebung bis zum Speichern des endgültigen Dokuments behandelt. Mit Aspose.Words können Sie komplexe Dokumentenverarbeitungsaufgaben automatisieren und so Ihre .NET-Anwendungen leistungsfähiger und effizienter machen.

## FAQs

### 1. Was ist ein Zusammenführungsfeld?
Ein Zusammenführungsfeld ist ein Platzhalter in einem Dokument, der dynamisch durch Daten aus einer Datenquelle, beispielsweise einer Datenbank oder einer CSV-Datei, ersetzt werden kann.

### 2. Kann ich Aspose.Words kostenlos nutzen?
 Aspose.Words bietet eine kostenlose Testversion, die Sie herunterladen können[Hier](https://releases.aspose.com/). Für die langfristige Nutzung müssen Sie eine Lizenz erwerben.

### 3. Wie erhalte ich eine temporäre Lizenz für Aspose.Words?
 Sie können eine temporäre Lizenz auf der Aspose-Website erwerben[Hier](https://purchase.aspose.com/temporary-license/).

### 4. Welche Versionen von .NET werden von Aspose.Words unterstützt?
Aspose.Words unterstützt mehrere Versionen von .NET, einschließlich .NET Framework, .NET Core und .NET Standard.

### 5. Wo finde ich die API-Dokumentation für Aspose.Words?
 Die API-Dokumentation ist verfügbar.[Hier](https://reference.aspose.com/words/net/).