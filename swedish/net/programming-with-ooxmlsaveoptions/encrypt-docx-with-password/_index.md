---
title: Kryptera Docx med lösenord
linktitle: Kryptera Docx med lösenord
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du krypterar en DOCX-fil med ett lösenord med Aspose.Words för .NET. Komplett handledning för dokumentsäkerhet.
type: docs
weight: 10
url: /sv/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
I den här handledningen kommer vi att utforska den medföljande C#-källkoden för att kryptera en DOCX-fil med ett lösenord med Aspose.Words för .NET. Denna funktion låter dig skydda ditt dokument genom att göra det tillgängligt endast med ett specificerat lösenord.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har ställt in din utvecklingsmiljö med Aspose.Words för .NET. Se till att du har lagt till nödvändiga referenser och importerat lämpliga namnområden.

## Steg 2: Ladda dokumentet

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 I det här steget laddar vi dokumentet med hjälp av`Document` metod och skickar sökvägen till DOCX-filen som ska laddas.

## Steg 3: Konfigurera OOXML-säkerhetskopieringsalternativ

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

 det här steget konfigurerar vi OOXML-sparalternativ genom att skapa ett nytt`OoxmlSaveOptions` objekt. Vi anger det önskade lösenordet för att kryptera dokumentet genom att ställa in`Password` egendom till ditt anpassade lösenord.

## Steg 4: Kryptera dokumentet med lösenord

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 I detta sista steg sparar vi dokumentet med hjälp av`Save` metod och skickar sökvägen till utdatafilen med`.docx` tillägg, tillsammans med de angivna sparalternativen.

Nu kan du köra källkoden för att kryptera ditt DOCX-dokument med ett lösenord. Den resulterande filen kommer att sparas i den angivna katalogen med namnet "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx". Se till att förvara ditt lösenord säkert, eftersom det kommer att behövas för att öppna det krypterade dokumentet.

### Exempel på källkod för Kryptera Docx med lösenord med Aspose.Words för .NET 

```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Slutsats

I den här handledningen utforskade vi funktionen för att kryptera en DOCX-fil med ett lösenord med Aspose.Words för .NET. Vi lärde oss hur vi skyddar våra dokument genom att göra dem tillgängliga endast med ett specificerat lösenord.

Dokumentkryptering är en viktig säkerhetsåtgärd för att skydda känslig information. Tack vare Aspose.Words för .NET kan vi enkelt lägga till denna funktionalitet till våra applikationer.

Genom att följa de angivna stegen kan du integrera lösenordskryptering i dina Aspose.Words for .NET-projekt och säkerställa sekretessen för dina dokument.

Experimentera gärna med andra funktioner som erbjuds av Aspose.Words för .NET för att berika dina applikationer med avancerade dokumentmanipuleringsfunktioner.
