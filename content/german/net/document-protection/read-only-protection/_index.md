---
title: Schreibschutz im Word-Dokument
linktitle: Schreibschutz im Word-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Ihre schreibgeschützten Word-Dokumente mit Aspose.Words für .NET schützen.
type: docs
weight: 10
url: /de/net/document-protection/read-only-protection/
---
In diesem Tutorial führen wir Sie durch die Schritte zur Verwendung der schreibgeschützten Schutzfunktion von Aspose.Words für .NET. Mit dieser Funktion können Sie ein Word-Dokument schreibgeschützt machen, um unbefugte Änderungen zu verhindern. Befolgen Sie die folgenden Schritte:

## Schritt 1: Erstellen des Dokuments und Anwenden des Schutzes

Beginnen Sie mit der Erstellung einer Instanz der Document-Klasse und eines DocumentBuilder-Objekts:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Schreiben Sie Inhalt in das Dokument
Verwenden Sie das DocumentBuilder-Objekt, um Inhalt in das Dokument zu schreiben:

```csharp
builder.Write("Open document as read-only");
```

## Schritt 3: Passwort festlegen und Dokument schreibgeschützt machen

Legen Sie mit der SetPassword()-Eigenschaft des WriteProtection-Objekts ein Kennwort für das Dokument fest:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Ersetzen Sie „MyPassword“ unbedingt durch das tatsächliche Passwort, das Sie verwenden möchten.

## Schritt 4: Schreibgeschütztes Dokument anwenden

Machen Sie das Dokument schreibgeschützt, indem Sie die Eigenschaft ReadOnlyRecommended auf „true“ setzen:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Schritt 5: Schreibschutz anwenden und Dokument speichern

Wenden Sie abschließend mit der Protect()-Methode des Document-Objekts einen Nur-Lese-Schutz an:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Geben Sie zum Speichern des geschützten Dokuments unbedingt den richtigen Pfad und Dateinamen an.

### Beispielquellcode für Nur-Lese-Schutz mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für den schreibgeschützten Schutz mit Aspose.Words für .NET:

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Geben Sie ein maximal 15 Zeichen langes Passwort ein.
doc.WriteProtection.SetPassword("MyPassword");

// Machen Sie das Dokument schreibgeschützt.
doc.WriteProtection.ReadOnlyRecommended = true;

// Schreibschutz auf schreibgeschützt anwenden.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Mit diesen Schritten können Sie Ihre Dokumente ganz einfach schützen

## Abschluss

In diesem Tutorial haben wir die Funktion zum schreibgeschützten Schutz von Aspose.Words für .NET untersucht, mit der Sie Word-Dokumente schreibgeschützt machen können, um unbefugte Änderungen zu verhindern. Indem Sie die angegebenen Schritte befolgen, können Sie Ihre Dokumente ganz einfach schreibgeschützt schützen und deren Sicherheit erhöhen. Der schreibgeschützte Schutz trägt dazu bei, die Integrität und Genauigkeit des Inhalts Ihres Dokuments sicherzustellen, indem er die Bearbeitungsmöglichkeiten einschränkt. Aspose.Words für .NET bietet eine leistungsstarke und flexible API zum Verwalten des Dokumentschutzes und unterstützt verschiedene andere Funktionen zum Anpassen und Sichern Ihrer Word-Dokumente.

### FAQs zum Nur-Lese-Schutz in Word-Dokumenten

#### F: Was ist der schreibgeschützte Schutz in Aspose.Words für .NET?

A: Der Nur-Lese-Schutz in Aspose.Words für .NET ist eine Funktion, mit der Sie ein Word-Dokument schreibgeschützt machen können, um unbefugte Änderungen zu verhindern. Wenn ein Dokument schreibgeschützt ist, können Benutzer das Dokument öffnen und anzeigen, aber keine Änderungen an seinem Inhalt vornehmen.

#### F: Wie kann ich mit Aspose.Words für .NET einen schreibgeschützten Schutz auf ein Word-Dokument anwenden?

A: Um mit Aspose.Words für .NET einen schreibgeschützten Schutz auf ein Word-Dokument anzuwenden, können Sie die folgenden Schritte ausführen:
1.  Erstellen Sie eine Instanz des`Document` Klasse und eine`DocumentBuilder` Objekt.
2.  Verwenden Sie die`DocumentBuilder` um Inhalt in das Dokument zu schreiben.
3.  Legen Sie ein Passwort für das Dokument fest, indem Sie`SetPassword` Methode der`WriteProtection` Objekt.
4.  Legen Sie die`ReadOnlyRecommended` Eigentum der`WriteProtection` Einwände erheben gegen`true` um zu empfehlen, das Dokument schreibgeschützt zu öffnen.
5.  Wenden Sie den Nur-Lese-Schutz an mit dem`Protect` Methode der`Document` Objekt, unter Angabe der`ProtectionType` als`ReadOnly`.
6.  Speichern Sie das geschützte Dokument mit dem`Save` Methode der`Document` Objekt.

#### F: Kann ich mit Aspose.Words für .NET den schreibgeschützten Schutz aus einem Word-Dokument entfernen?

A: Ja, Sie können den Nur-Lese-Schutz eines Word-Dokuments mit Aspose.Words für .NET entfernen. Dazu können Sie den`Unprotect` Methode der`Document` Klasse, die jeglichen vorhandenen Schutz vom Dokument entfernt.

#### F: Kann ich für den Leseschutz eines Word-Dokuments ein anderes Kennwort festlegen?

 A: Nein, der Nur-Lese-Schutz in Aspose.Words für .NET erlaubt es Ihnen nicht, ein separates Passwort speziell für den Nur-Lese-Schutz festzulegen. Das mit dem`SetPassword` Methode der`WriteProtection` Objekt gilt für den gesamten Dokumentschutz, einschließlich Nur-Lese- und Lese-Schreibschutz.

#### F: Können Benutzer den Leseschutz in einem Word-Dokument umgehen?

A: Der Nur-Lese-Schutz in einem Word-Dokument soll versehentliche oder unbefugte Änderungen verhindern. Obwohl er ein gewisses Maß an Schutz bietet, kann er von Benutzern mit ausreichendem technischen Wissen oder Bearbeitungsberechtigungen umgangen werden. Der Nur-Lese-Schutz dient jedoch als Abschreckung und trägt dazu bei, die Integrität des Dokuments zu wahren.