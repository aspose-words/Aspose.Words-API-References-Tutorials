---
title: Link in Word erstellen
linktitle: Link in Word erstellen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Word-Verknüpfung zwischen Textfeldern in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/working-with-textboxes/create-a-link/
---
In dieser Schritt-für-Schritt-Anleitung wird erläutert, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET eine Word-Verknüpfung zwischen zwei Textfeldern in einem Word-Dokument erstellen. Sie erfahren, wie Sie das Dokument konfigurieren, die Textfeldformen erstellen, auf die Textfelder zugreifen, die Gültigkeit des Linkziels überprüfen und schließlich den Link selbst erstellen.

## Schritt 1: Einrichten des Dokuments und Erstellen von TextBox-Formen

 Zunächst müssen wir das Dokument einrichten und zwei TextBox-Formen erstellen. Der folgende Code initialisiert eine neue Instanz von`Document` Klasse und erstellt zwei Textfeldformen:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Schritt 2: Erstellen einer Verknüpfung zwischen TextBoxen

Wir erstellen nun mithilfe von eine Verknüpfung zwischen den beiden TextBoxen`IsValidLinkTarget()` Methode und die`Next` Eigenschaft der ersten TextBox.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 Der`IsValidLinkTarget()` Die Methode prüft, ob die zweite TextBox ein gültiges Ziel für den Link der ersten TextBox sein kann. Wenn die Validierung erfolgreich ist, wird die`Next` Die Eigenschaft der ersten TextBox wird auf die zweite TextBox gesetzt, wodurch eine Verknüpfung zwischen beiden erstellt wird.

### Beispielquellcode zur Verknüpfung mit Aspose.Words für .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```
## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET eine Verknüpfung zwischen zwei Textfeldern in einem Word-Dokument erstellen. Mithilfe dieser Schritt-für-Schritt-Anleitung konnten Sie das Dokument einrichten, die Textfeldformen erstellen, auf die Textfelder zugreifen, die Gültigkeit des Linkziels überprüfen und schließlich den Link selbst erstellen.

### FAQs zum Erstellen von Links in Word

#### F: Welche Bibliothek wird zum Verknüpfen von Textfeldern in Word mit Aspose.Words für .NET verwendet?

A: Um Textfelder in Word mit Aspose.Words für .NET zu verknüpfen, wird die Bibliothek Aspose.Words für .NET verwendet.

#### F: Wie kann ich prüfen, ob das Linkziel gültig ist, bevor ich den Link erstelle?

 A: Bevor Sie die Verknüpfung zwischen Textfeldern erstellen, können Sie die verwenden`IsValidLinkTarget()` Methode, um zu überprüfen, ob das Linkziel gültig ist. Diese Methode überprüft, ob das zweite Textfeld ein gültiges Ziel für den Link aus dem ersten Textfeld sein kann.

#### F: Wie erstelle ich eine Verknüpfung zwischen zwei Textfeldern?

 A: Um eine Verknüpfung zwischen zwei Textfeldern zu erstellen, müssen Sie die festlegen`Next` Eigenschaft des ersten Textfelds auf das zweite Textfeld übertragen. Stellen Sie sicher, dass Sie die Gültigkeit des Linkziels zuvor mithilfe des überprüft haben`IsValidLinkTarget()` Methode.

#### F: Ist es möglich, Verknüpfungen zwischen anderen Elementen als Textfeldern zu erstellen?

A: Ja, mit der Aspose.Words-Bibliothek für .NET ist es möglich, Verknüpfungen zwischen verschiedenen Elementen wie Absätzen, Tabellen, Bildern usw. zu erstellen. Der Vorgang variiert je nach dem spezifischen Element, das Sie verknüpfen möchten.

#### F: Welche weiteren Funktionen können mit Aspose.Words für .NET zu Textfeldern in Word hinzugefügt werden?

A: Mit Aspose.Words für .NET können Sie Textfeldern viele weitere Funktionen hinzufügen, z. B. Textformatierung, Bilder hinzufügen, Stile ändern usw. Sie können die Dokumentation zu Aspose.Words für .NET durchsuchen, um alle Funktionen herauszufinden verfügbar.