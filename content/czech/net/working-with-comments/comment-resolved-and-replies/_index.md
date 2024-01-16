---
title: Komentář vyřešen a odpovědi
linktitle: Komentář vyřešen a odpovědi
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vyřešit komentáře a jejich odpovědi v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-comments/comment-resolved-and-replies/
---

tomto komplexním tutoriálu se naučíte, jak vyřešit komentáře a jejich odpovědi v dokumentu aplikace Word pomocí Aspose.Words for .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete moci spravovat řešení komentářů a aktualizovat stav komentářů a jejich odpovědí.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Načtěte dokument a otevřete komentáře
Chcete-li začít, načtěte dokument, který obsahuje komentáře, pomocí třídy Document a otevřete kolekci komentářů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Krok 2: Vyřešte komentáře a jejich odpovědi
Dále projděte komentáře a jejich odpovědi a označte je jako vyřešené:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Ve výše uvedeném kódu přistupujeme k nadřazenému komentáři a iterujeme jeho odpovědi. Můžeme načíst ID nadřazeného komentáře a jeho stav řešení. Poté aktualizujeme značku „Hotovo“ u každé odpovědi na komentář, aby bylo uvedeno řešení.

## Krok 3: Uložte dokument
Po vyřešení komentářů a aktualizaci jejich stavu uložte upravený dokument do souboru pomocí metody Save třídy Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Příklad zdrojového kódu pro řešení komentářů a jejich odpovědí pomocí Aspose.Words for .NET
Zde je kompletní zdrojový kód pro řešení komentářů a jejich odpovědí pomocí Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Nezapomeňte upravit kód podle vašich konkrétních požadavků, včetně cesty k souboru dokumentu a dalších úprav

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vyřešit komentáře a jejich odpovědi v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete nyní spravovat řešení komentářů a aktualizovat stav komentářů a jejich odpovědí podle vašich požadavků.

Rozlišení komentářů pomáhá při sledování a správě zpětné vazby v dokumentu. Experimentujte s různými stavy komentářů a přizpůsobte je, abyste zlepšili spolupráci a procesy kontroly ve vašich dokumentech.

### FAQ

#### Otázka: Jak vyřeším komentář v Aspose.Words pro .NET?

 A: Chcete-li vyřešit komentář v Aspose.Words pro .NET, můžete použít`Comment.Resolve` způsob upřesňující`Comment` objekt, který chcete vyřešit. Tím označíte komentář jako vyřešený a skryjete jej v konečném dokumentu.

#### Otázka: Jak přidám odpověď na vyřešený komentář v Aspose.Words pro .NET?

 Odpověď: Přestože jsou vyřešené komentáře ve výchozím nastavení v konečném dokumentu skryté, stále můžete přidat odpověď na vyřešený komentář pomocí`Comment.AddReply` metoda určující text odpovědi a místo, kam jej chcete přidat.

#### Otázka: Jak zobrazím vyřešené komentáře v Aspose.Words for .NET?

 Odpověď: Ve výchozím nastavení jsou vyřešené komentáře v konečném dokumentu skryté. Můžete je však zobrazit pomocí`CommentOptions.ShowResolvedComments` vlastnictvím`Document` objekt a jeho nastavení`true`.

#### Otázka: Jak mohu skrýt všechny komentáře, včetně odpovědí, v Aspose.Words for .NET?

 A: Chcete-li skrýt všechny komentáře, včetně odpovědí, v Aspose.Words pro .NET, můžete použít`CommentOptions.CommentDisplayMode` vlastnictvím`Document` objekt a nastavte jej na`CommentDisplayMode.None`.

#### Otázka: Mohu upravit text vyřešeného komentáře v Aspose.Words pro .NET?

 Odpověď: Ano, můžete upravit text vyřešeného komentáře v Aspose.Words pro .NET přístupem k`Comment.Text` vlastnost odpovídající`Comment` objekt a upravovat text podle potřeby.