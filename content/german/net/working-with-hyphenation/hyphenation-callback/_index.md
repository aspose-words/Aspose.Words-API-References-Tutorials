---
title: Rückruf zur Silbentrennung
linktitle: Rückruf zur Silbentrennung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie in dieser umfassenden Schritt-für-Schritt-Anleitung, wie Sie den Silbentrennungsrückruf in Aspose.Words für .NET implementieren, um die Dokumentformatierung zu verbessern.
type: docs
weight: 10
url: /de/net/working-with-hyphenation/hyphenation-callback/
---

## Einführung

Hallo! Haben Sie sich schon einmal mit der Komplexität der Textformatierung beschäftigt, insbesondere wenn es um Sprachen geht, die eine Silbentrennung erfordern? Du bist nicht allein. Die Silbentrennung ist zwar für das richtige Textlayout von entscheidender Bedeutung, kann jedoch ein wenig Kopfzerbrechen bereiten. Aber rate mal was? Aspose.Words für .NET steht Ihnen zur Seite. Mit dieser leistungsstarken Bibliothek können Sie die Textformatierung nahtlos verwalten, einschließlich der Silbentrennung über einen Rückrufmechanismus. Fasziniert? Lassen Sie uns ins Detail gehen, wie Sie mit Aspose.Words für .NET einen Silbentrennungsrückruf implementieren können.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:

1.  Aspose.Words für .NET: Stellen Sie sicher, dass Sie über die Bibliothek verfügen. Du kannst[hier herunterladen](https://releases.aspose.com/words/net/).
2. IDE: Eine Entwicklungsumgebung wie Visual Studio.
3. Grundkenntnisse in C#: Verständnis von C# und .NET Framework.
4. Silbentrennungswörterbücher: Silbentrennungswörterbücher für die Sprachen, die Sie verwenden möchten.
5.  Aspose-Lizenz: Eine gültige Aspose-Lizenz. Sie können eine bekommen[temporäre Lizenz](https://purchase.aspose.com/temporary-license/) falls du keins hast.

## Namespaces importieren

Als Erstes importieren wir die erforderlichen Namespaces. Dadurch wird sichergestellt, dass unser Code Zugriff auf alle Klassen und Methoden hat, die wir von Aspose.Words benötigen.

```csharp
using Aspose.Words;
using System;
using System.IO;
```

## Schritt 1: Registrieren Sie den Silbentrennungsrückruf

Zunächst müssen wir unseren Silbentrennungsrückruf registrieren. Hier weisen wir Aspose.Words an, unsere benutzerdefinierte Silbentrennungslogik zu verwenden.

```csharp
try
{
    // Rückruf für Silbentrennung registrieren.
    Hyphenation.Callback = new CustomHyphenationCallback();
}
catch (Exception e)
{
    Console.WriteLine($"Error registering hyphenation callback: {e.Message}");
}
```

 Hier erstellen wir eine Instanz unseres benutzerdefinierten Rückrufs und weisen ihn zu`Hyphenation.Callback`.

## Schritt 2: Definieren Sie den Dokumentpfad

Als nächstes müssen wir das Verzeichnis definieren, in dem unsere Dokumente gespeichert werden. Dies ist von entscheidender Bedeutung, da wir Dokumente über diesen Pfad laden und speichern.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihren Dokumenten.

## Schritt 3: Laden Sie das Dokument

Laden wir nun das Dokument, das eine Silbentrennung erfordert.

```csharp
Document document = new Document(dataDir + "German text.docx");
```

 Hier laden wir ein deutsches Textdokument. Sie können ersetzen`"German text.docx"` mit dem Dateinamen Ihres Dokuments.

## Schritt 4: Speichern Sie das Dokument

Nachdem wir das Dokument geladen haben, speichern wir es in einer neuen Datei und wenden dabei den Silbentrennungs-Callback an.

```csharp
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

Diese Zeile speichert das Dokument als PDF mit angewendeter Silbentrennung.

## Schritt 5: Behandeln Sie die Ausnahme „Fehlendes Silbentrennungswörterbuch“.

Manchmal kann es vorkommen, dass das Silbentrennungswörterbuch fehlt. Lassen Sie uns das in den Griff bekommen.

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
    Console.WriteLine(e.Message);
}
finally
{
    Hyphenation.Callback = null;
}
```

In diesem Block fangen wir die spezifische Ausnahme im Zusammenhang mit fehlenden Wörterbüchern ab und geben die Nachricht aus.

## Schritt 6: Implementieren Sie die benutzerdefinierte Silbentrennungs-Rückrufklasse

 Lassen Sie uns nun das implementieren`CustomHyphenationCallback` Klasse, die die Anforderung für Silbentrennungswörterbücher verarbeitet.

```csharp
public class CustomHyphenationCallback : IHyphenationCallback
{
    public void RequestDictionary(string language)
    {
        string dictionaryFolder = MyDir;
        string dictionaryFullFileName;
        switch (language)
        {
            case "en-US":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_en_US.dic");
                break;
            case "de-CH":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_de_CH.dic");
                break;
            default:
                throw new Exception($"Missing hyphenation dictionary for {language}.");
        }
        // Registrieren Sie das Wörterbuch für die gewünschte Sprache.
        Hyphenation.RegisterDictionary(language, dictionaryFullFileName);
    }
}
```

 In dieser Klasse ist die`RequestDictionary` Die Methode wird immer dann aufgerufen, wenn ein Silbentrennungswörterbuch benötigt wird. Es überprüft die Sprache und registriert das entsprechende Wörterbuch.

## Abschluss

Und da haben Sie es! Sie haben gerade gelernt, wie Sie einen Silbentrennungsrückruf in Aspose.Words für .NET implementieren. Wenn Sie diese Schritte befolgen, können Sie sicherstellen, dass Ihre Dokumente unabhängig von der Sprache schön formatiert sind. Unabhängig davon, ob Sie mit Englisch, Deutsch oder einer anderen Sprache arbeiten, können Sie mit dieser Methode die Silbentrennung mühelos bewältigen.

## FAQs

### Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zur Dokumentbearbeitung, mit der Entwickler Dokumente programmgesteuert erstellen, ändern und konvertieren können.

### Warum ist die Silbentrennung bei der Dokumentformatierung wichtig?
Die Silbentrennung verbessert das Textlayout, indem sie Wörter an geeigneten Stellen umbricht und so ein lesbareres und optisch ansprechenderes Dokument gewährleistet.

### Kann ich Aspose.Words kostenlos nutzen?
 Aspose.Words bietet eine kostenlose Testversion. Du kannst es bekommen[Hier](https://releases.aspose.com/).

### Wie erhalte ich ein Silbentrennungswörterbuch?
Sie können Silbentrennungswörterbücher von verschiedenen Online-Ressourcen herunterladen oder bei Bedarf eigene Wörterbücher erstellen.

### Was passiert, wenn ein Silbentrennungswörterbuch fehlt?
 Wenn ein Wörterbuch fehlt, wird das`RequestDictionary` Die Methode löst eine Ausnahme aus, die Sie verarbeiten können, um den Benutzer zu informieren oder einen Fallback bereitzustellen.