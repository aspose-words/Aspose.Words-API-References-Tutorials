---
title: Verwenden von Web-Erweiterungsaufgabenbereichen
linktitle: Verwenden von Web-Erweiterungsaufgabenbereichen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in diesem ausführlichen Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.Words für .NET Web Extension Task Panes in Word-Dokumenten hinzufügen und konfigurieren.
type: docs
weight: 10
url: /de/net/programming-with-webextension/using-web-extension-task-panes/
---
## Einführung

Willkommen zu diesem ausführlichen Tutorial zur Verwendung von Web Extension Task Panes in einem Word-Dokument mit Aspose.Words für .NET. Wenn Sie Ihre Word-Dokumente schon immer mit interaktiven Aufgabenbereichen erweitern wollten, sind Sie hier richtig. Diese Anleitung führt Sie durch jeden Schritt, um dies nahtlos zu erreichen.

## Voraussetzungen

Bevor wir loslegen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:

-  Aspose.Words für .NET: Sie können es herunterladen[Hier](https://releases.aspose.com/words/net/).
- .NET-Entwicklungsumgebung: Visual Studio oder eine andere IDE Ihrer Wahl.
- Grundkenntnisse in C#: Dies hilft Ihnen, den Codebeispielen zu folgen.
-  Lizenz für Aspose.Words: Sie können eine kaufen[Hier](https://purchase.aspose.com/buy) oder holen Sie sich eine temporäre Lizenz[Hier](https://purchase.aspose.com/temporary-license/).

## Namespaces importieren

Bevor wir mit der Codierung beginnen, stellen Sie sicher, dass Sie die folgenden Namespaces in Ihr Projekt importiert haben:

```csharp
using Aspose.Words;
using Aspose.Words.WebExtensions;
```

## Schritt für Schritt Anleitung

Lassen Sie uns den Vorgang nun in leicht verständliche Schritte unterteilen.

### Schritt 1: Einrichten Ihres Dokumentverzeichnisses

Als Erstes müssen wir den Pfad zu Ihrem Dokumentverzeichnis einrichten. Hier wird Ihr Word-Dokument gespeichert.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentordner.

### Schritt 2: Neues Dokument erstellen

Als Nächstes erstellen wir mit Aspose.Words ein neues Word-Dokument.

```csharp
Document doc = new Document();
```

 Diese Zeile initialisiert eine neue Instanz des`Document` Klasse, die ein Word-Dokument darstellt.

### Schritt 3: Hinzufügen eines Aufgabenbereichs

Jetzt fügen wir unserem Dokument einen Aufgabenbereich hinzu. Aufgabenbereiche sind nützlich, um zusätzliche Funktionen und Tools in einem Word-Dokument bereitzustellen.

```csharp
TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);
```

 Hier erstellen wir ein neues`TaskPane` Objekt und fügen Sie es dem Dokument hinzu`WebExtensionTaskPanes` Sammlung.

### Schritt 4: Konfigurieren des Aufgabenbereichs

Um unseren Aufgabenbereich sichtbar zu machen und seine Eigenschaften festzulegen, verwenden wir den folgenden Code:

```csharp
taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

- `DockState` legt fest, wo der Aufgabenbereich angezeigt wird. In diesem Fall ist er rechts.
- `IsVisible` stellt sicher, dass der Aufgabenbereich sichtbar ist.
- `Width` Legt die Breite des Aufgabenbereichs fest.

### Schritt 5: Einrichten der Web-Erweiterungsreferenz

Als Nächstes richten wir die Web Extension Reference ein, die die ID, Version, den Store-Typ und den Store umfasst.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

- `Id`ist eine eindeutige Kennung für die Web-Erweiterung.
- `Version` gibt die Version der Erweiterung an.
- `StoreType` gibt den Typ des Geschäfts an (in diesem Fall OMEX).
- `Store` gibt den Sprach-/Kulturcode des Geschäfts an.

### Schritt 6: Hinzufügen von Eigenschaften zur Web-Erweiterung

Sie können Ihrer Web-Erweiterung Eigenschaften hinzufügen, um ihr Verhalten oder ihren Inhalt zu definieren.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
```

 Hier fügen wir eine Eigenschaft namens`mailchimpCampaign`.

### Schritt 7: Binden der Web-Erweiterung

Zum Schluss fügen wir unserer Web-Erweiterung Bindungen hinzu. Mit Bindungen können Sie die Erweiterung mit bestimmten Teilen des Dokuments verknüpfen.

```csharp
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545", WebExtensionBindingType.Text, "194740422"));
```

- `UnnamedBinding_0_1506535429545` ist der Name der Bindung.
- `WebExtensionBindingType.Text` gibt an, dass die Bindung vom Typ Text ist.
- `194740422` ist die ID des Dokumentteils, an den die Erweiterung gebunden ist.

### Schritt 8: Speichern des Dokuments

Nachdem Sie alles eingerichtet haben, speichern Sie Ihr Dokument.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

Diese Zeile speichert das Dokument unter dem angegebenen Dateinamen im angegebenen Verzeichnis.

### Schritt 9: Laden und Anzeigen von Aufgabenbereichsinformationen

Um die Aufgabenbereichsinformationen zu überprüfen und anzuzeigen, laden wir das Dokument und durchlaufen die Aufgabenbereiche.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");

Console.WriteLine("Task panes sources:\n");

foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
    WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
    Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
}
```

Dieser Code lädt das Dokument und druckt den Anbieter, die Version und die Katalogkennung jedes Aufgabenbereichs in der Konsole.

## Abschluss

Und das ist es! Sie haben erfolgreich einen Web Extension Task Pane in einem Word-Dokument mit Aspose.Words für .NET hinzugefügt und konfiguriert. Diese leistungsstarke Funktion kann Ihre Word-Dokumente erheblich verbessern, indem sie zusätzliche Funktionen direkt im Dokument bereitstellt. 

## Häufig gestellte Fragen

### Was ist ein Aufgabenbereich in Word?
Ein Aufgabenbereich ist ein Schnittstellenelement, das zusätzliche Tools und Funktionen innerhalb eines Word-Dokuments bereitstellt und so die Benutzerinteraktion und Produktivität verbessert.

### Kann ich das Erscheinungsbild des Aufgabenbereichs anpassen?
 Ja, Sie können das Erscheinungsbild des Aufgabenbereichs anpassen, indem Sie Eigenschaften festlegen wie`DockState`, `IsVisible` , Und`Width`.

### Was sind Web-Erweiterungseigenschaften?
Web-Erweiterungseigenschaften sind benutzerdefinierte Eigenschaften, die Sie einer Web-Erweiterung hinzufügen können, um deren Verhalten oder Inhalt zu definieren.

### Wie binde ich eine Web-Erweiterung an einen Teil des Dokuments?
 Sie können eine Web-Erweiterung an einen Teil des Dokuments binden, indem Sie`WebExtensionBinding` Klasse, unter Angabe des Bindungstyps und der Ziel-ID.

### Wo finde ich weitere Informationen zu Aspose.Words für .NET?
 Eine ausführliche Dokumentation finden Sie[Hier](https://reference.aspose.com/words/net/).