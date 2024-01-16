---
title: Állítsa be az oroszt alapértelmezett szerkesztési nyelvként
linktitle: Állítsa be az oroszt alapértelmezett szerkesztési nyelvként
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre az orosz beállításához a dokumentumok alapértelmezett szerkesztési nyelveként az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, hogy az oroszt állítsa be alapértelmezett szerkesztési nyelvként az Aspose.Words for .NET segítségével. Ezzel a funkcióval beállíthatja az alapértelmezett nyelvet a dokumentum betöltésekor.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük azt a Word dokumentumot, amelyhez az oroszt szeretnénk alapértelmezett szerkesztési nyelvként beállítani. A dokumentum betöltéséhez használja a következő kódot:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentum található.

## 3. lépés: Az alapértelmezett nyelv ellenőrzése

dokumentum feltöltése után ellenőrizzük, hogy az alapértelmezett nyelv megfelelően lett-e beállítva oroszra. Az alapértelmezett nyelvazonosító lekéréséhez használja a következő kódot:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

A kód ellenőrzi, hogy a nyelvazonosító megegyezik-e az orosz nyelvvel. Az eredménynek megfelelően egy megfelelő üzenetet jelenít meg.

### Példa forráskód az orosz beállítása alapértelmezett szerkesztési nyelvnek az Aspose.Words for .NET használatával

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg a`dataDir` változó.

Megtanulta, hogyan állíthat be orosz nyelvet a dokumentumok alapértelmezett szerkesztési nyelveként az Aspose.Words for .NET használatával. A lépéses útmutató követésével