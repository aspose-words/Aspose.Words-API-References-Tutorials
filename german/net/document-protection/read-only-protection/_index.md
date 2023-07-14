---
title: Nur-Lese-Schutz in Word-Dokumenten
linktitle: Nur-Lese-Schutz in Word-Dokumenten
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Ihre schreibgeschützten Word-Dokumente mit Aspose.Words für .NET schützen.
type: docs
weight: 10
url: /de/net/document-protection/read-only-protection/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der Leseschutzfunktion von Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument schreibgeschützt machen, um unbefugte Änderungen zu verhindern. Folgen Sie den unteren Schritten:

## Schritt 1: Dokument erstellen und Schutz anwenden

Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Schreiben Sie Inhalte in das Dokument
Verwenden Sie das DocumentBuilder-Objekt, um Inhalte in das Dokument zu schreiben:

```csharp
builder.Write("Open document as read-only");
```

## Schritt 3: Passwort festlegen und Dokument schreibgeschützt machen

Legen Sie mithilfe der SetPassword()-Eigenschaft des WriteProtection-Objekts ein Kennwort für das Dokument fest:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Ersetzen Sie „MyPassword“ unbedingt durch das tatsächliche Passwort, das Sie verwenden möchten.

## Schritt 4: Schreibgeschütztes Dokument anwenden

Machen Sie das Dokument schreibgeschützt, indem Sie die ReadOnlyRecommended-Eigenschaft auf true setzen:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Schritt 5: Wenden Sie den Leseschutz an und speichern Sie das Dokument

Wenden Sie abschließend den schreibgeschützten Schutz mit der Protect()-Methode des Document-Objekts an:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen zum Speichern des geschützten Dokuments angeben.

### Beispielquellcode für den Leseschutz mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für den schreibgeschützten Schutz mit Aspose.Words für .NET:

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Geben Sie ein bis zu 15 Zeichen langes Passwort ein.
doc.WriteProtection.SetPassword("MyPassword");

// Machen Sie das Dokument schreibgeschützt.
doc.WriteProtection.ReadOnlyRecommended = true;

// Wenden Sie den Schreibschutz als schreibgeschützt an.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Wenn Sie diese Schritte befolgen, können Sie Ihre Dokumente ganz einfach schützen

## Abschluss

In diesem Tutorial haben wir die Leseschutzfunktion von Aspose.Words für .NET untersucht, mit der Sie Word-Dokumente schreibgeschützt machen können, um unbefugte Änderungen zu verhindern. Indem Sie die bereitgestellten Schritte befolgen, können Sie ganz einfach einen Leseschutz auf Ihre Dokumente anwenden und deren Sicherheit erhöhen. Der Leseschutz trägt dazu bei, die Integrität und Genauigkeit des Inhalts Ihres Dokuments sicherzustellen, indem er die Bearbeitungsmöglichkeiten einschränkt. Aspose.Words für .NET bietet eine leistungsstarke und flexible API für den Dokumentenschutz und unterstützt verschiedene andere Funktionen zum Anpassen und Sichern Ihrer Word-Dokumente.

### FAQs zum schreibgeschützten Schutz in Word-Dokumenten

#### F: Was ist der schreibgeschützte Schutz in Aspose.Words für .NET?

A: Der schreibgeschützte Schutz in Aspose.Words für .NET ist eine Funktion, die es Ihnen ermöglicht, ein Word-Dokument schreibgeschützt zu machen und so unbefugte Änderungen zu verhindern. Wenn ein Dokument schreibgeschützt ist, können Benutzer das Dokument öffnen und anzeigen, aber keine Änderungen an seinem Inhalt vornehmen.

#### F: Wie kann ich mit Aspose.Words für .NET einen schreibgeschützten Schutz auf ein Word-Dokument anwenden?

A: Um mithilfe von Aspose.Words für .NET den Leseschutz auf ein Word-Dokument anzuwenden, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine Instanz von`Document` Klasse und a`DocumentBuilder` Objekt.
2.  Benutzen Sie die`DocumentBuilder` um Inhalte in das Dokument zu schreiben.
3.  Legen Sie mithilfe von ein Passwort für das Dokument fest`SetPassword` Methode der`WriteProtection` Objekt.
4.  Stellen Sie die ein`ReadOnlyRecommended`Eigentum der`WriteProtection` widersprechen`true` Ich empfehle, das Dokument schreibgeschützt zu öffnen.
5.  Wenden Sie einen schreibgeschützten Schutz mit an`Protect` Methode der`Document` Objekt, Angabe der`ProtectionType` als`ReadOnly`.
6.  Speichern Sie das geschützte Dokument mit`Save` Methode der`Document` Objekt.

#### F: Kann ich mit Aspose.Words für .NET den Leseschutz aus einem Word-Dokument entfernen?

A: Ja, Sie können den Leseschutz von einem Word-Dokument mit Aspose.Words für .NET entfernen. Dazu können Sie die verwenden`Unprotect` Methode der`Document` Klasse, die jeglichen vorhandenen Schutz aus dem Dokument entfernt.

#### F: Kann ich für den Leseschutz in einem Word-Dokument ein anderes Passwort festlegen?

 A: Nein, der Leseschutz in Aspose.Words für .NET erlaubt es Ihnen nicht, ein separates Passwort speziell für den Leseschutz festzulegen. Das mit dem festgelegte Passwort`SetPassword` Methode der`WriteProtection` Das Objekt gilt für den gesamten Dokumentschutz, einschließlich Lese- und Lese-/Schreibschutz.

#### F: Können Benutzer den Leseschutz in einem Word-Dokument umgehen?

A: Der Schreibschutz in einem Word-Dokument soll versehentliche oder unbefugte Änderungen verhindern und verhindern. Obwohl es ein gewisses Maß an Schutz bietet, kann es von Benutzern mit ausreichenden technischen Kenntnissen oder Bearbeitungsberechtigungen umgangen werden. Allerdings dient der Leseschutz als Abschreckung und trägt dazu bei, die Integrität des Dokuments zu wahren.