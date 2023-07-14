---
title: Rückruf zur Silbentrennung
linktitle: Rückruf zur Silbentrennung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie den Silbentrennungsrückruf in Aspose.Words für .NET verwenden, um die Silbentrennung von Wörtern zu verarbeiten.
type: docs
weight: 10
url: /de/net/working-with-hyphenation/hyphenation-callback/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie die Silbentrennungs-Rückruffunktion in Aspose.Words für .NET verwenden. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie es noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Silbentrennungserinnerung speichern

 Zuerst registrieren wir den Silbentrennungsrückruf mithilfe einer benutzerdefinierten Funktion`CustomHyphenationCallback` Klasse. Dadurch können wir die Silbentrennung von Wörtern nach unseren eigenen Regeln handhaben:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Stellen Sie sicher, dass Sie das implementiert haben`CustomHyphenationCallback`Unterricht nach Ihren spezifischen Bedürfnissen.

## Schritt 2: Laden des Dokuments und Anwenden der Silbentrennung

Laden Sie als Nächstes Ihr Dokument aus dem angegebenen Verzeichnis und trennen Sie die Wörter mit Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Schritt 3: Behandeln von fehlenden Wörterbuchfehlern

Falls ein Silbentrennungswörterbuch fehlt, fangen wir die entsprechende Ausnahme ab und zeigen eine Fehlermeldung an:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Schritt 4: Silbentrennungserinnerung bereinigen und deaktivieren

Führen Sie abschließend aus Gründen der Sauberkeit und zum Deaktivieren der Silbentrennungserinnerung die folgenden Schritte aus:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Dadurch wird die Silbentrennungserinnerung nach Abschluss der Verarbeitung bereinigt und deaktiviert.

So ! Sie haben den Silbentrennungs-Callback in Aspose.Words für .NET erfolgreich verwendet.

### Beispielquellcode für Silbentrennungsrückruf mit Aspose.Words für .NET

```csharp
try
{
	 // Rückruf für Silbentrennung registrieren.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und an Ihre spezifischen Bedürfnisse anpassen.

### FAQs

#### F: Was ist eine Silbentrennungserinnerung in Aspose.Words?

A: Eine Silbenerinnerung in Aspose.Words ist eine Funktion, mit der Sie anpassen können, wie Wörter in Ihren Dokumenten mit Silben versehen werden. Durch die Verwendung einer Silbentrennungserinnerung können Sie benutzerdefinierte Regeln für die Silbentrennung von Wörtern festlegen, was für bestimmte Sprachen oder bestimmte Szenarien nützlich sein kann, in denen die Standardsilbentrennung nicht die gewünschten Ergebnisse liefert.

#### F: Wie stelle ich in Aspose.Words eine Silbentrennungserinnerung ein?

 A: Um einen Silbentrennungsrückruf in Aspose.Words zu definieren, müssen Sie eine Klasse erstellen, die den implementiert`HyphenationCallback` Schnittstelle und implementieren die`HandleWord()` Methode. Diese Methode wird für jedes Wort aufgerufen, das während der Silbenbildung auftritt. Sie können benutzerdefinierte Silbenregeln darauf anwenden und das syllabierte Wort zurückgeben. Dann können Sie Ihren Silbentrennungsrückruf mit dem binden`Document.HyphenationCallback` Eigentum Ihres Dokuments.

#### F: Welchen Vorteil bietet die Verwendung einer Silbentrennungserinnerung in Aspose.Words?

A: Der Vorteil der Verwendung einer Silbenerinnerung in Aspose.Words besteht in der Möglichkeit, die Silbenbildung von Wörtern in Ihren Dokumenten anzupassen. Dies gibt Ihnen mehr Kontrolle über die Silbenbildung, insbesondere für bestimmte Sprachen oder Szenarien, in denen die Standardsilbenbildung nicht die gewünschten Ergebnisse liefert. Sie können auf jedes Wort spezifische Regeln anwenden, um eine präzise Silbenbildung entsprechend Ihren Anforderungen zu erhalten.

#### F: In welchen häufigen Situationen kann die Verwendung einer Silbentrennungserinnerung hilfreich sein?

A: Die Verwendung eines Silbenbildungs-Boosters kann in mehreren Szenarien nützlich sein, wie zum Beispiel:
- Silbenbildung von Wörtern in bestimmten Sprachen, für die bestimmte Regeln für die Silbenbildung gelten.
- Die Anwendung personalisierter Silbenregeln für Akronyme oder Fachwörter.
- Anpassung der Silbentrennung an stilistische Vorlieben oder typografische Standards.

#### F: Wie kann ich die benutzerdefinierte Silbentrennung mit einer Silbentrennungserinnerung in Aspose.Words testen?

A: Um die benutzerdefinierte Silbenbildung mit einer Silbenerinnerung in Aspose.Words zu testen, können Sie ein Testdokument erstellen, das Wörter enthält, für die Sie benutzerdefinierte Silbenbildungsregeln anwenden möchten. Dann können Sie Ihren benutzerdefinierten Rückruf für die Silbentrennung festlegen`Document.Range.Replace()` Methode, um die Wörter im Dokument zu ersetzen, und verwenden Sie die`Hyphenate()` Methode der`Hyphenation` Klasse, um die Silbenbildung der Wörter zu erhalten. Anschließend können Sie die Silbenwörter nach Bedarf formatieren, indem Sie beispielsweise Bindestriche zwischen den Silben einfügen.