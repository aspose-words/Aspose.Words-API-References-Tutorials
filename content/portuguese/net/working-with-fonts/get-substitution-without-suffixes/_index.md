---
title: Obtenha substituição sem sufixos
linktitle: Obtenha substituição sem sufixos
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, aprenda como obter substituições sem sufixo em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/get-substitution-without-suffixes/
---

Neste tutorial, mostraremos como obter substituições sem sufixos em um documento do Word usando a biblioteca Aspose.Words para .NET. As substituições sem sufixos são usadas para resolver problemas de substituição de fontes ao exibir ou imprimir documentos. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto

## Passo 1: Defina o diretório do documento
 Primeiro, você precisa definir o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento e configure substituições sem sufixos
 A seguir, carregaremos o documento usando o`Document` classe e configurar substituições sem sufixo usando o`DocumentSubstitutionWarnings` aula. Também adicionaremos uma fonte de fonte especificando uma pasta que contém as fontes.

```csharp
// Carregue o documento e configure substituições sem sufixos
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Etapa 3: salve o documento
Por fim, salvaremos o documento com as substituições sem sufixo aplicadas.

```csharp
// Salve o documento
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Exemplo de código-fonte para obter substituição sem sufixos usando Aspose.Words for .NET 
```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Conclusão
Neste tutorial, vimos como obter substituições sem sufixos em um documento Word com Aspose.Words for .NET. Substituições sem sufixos são úteis para resolver problemas de substituição de fontes. Sinta-se à vontade para usar esse recurso para melhorar a exibição e impressão de seus documentos.

### Perguntas frequentes

#### P: Por que Aspose.Words adiciona sufixos às substituições de fontes?

R: Aspose.Words adiciona sufixos às substituições de fontes para evitar conflitos entre as fontes originais e as fontes substituídas. Isto ajuda a garantir a máxima compatibilidade ao converter e manipular documentos.

#### P: Como posso recuperar substituições de fontes sem sufixos em Aspose.Words?

 R: Para recuperar substituições de fontes sem sufixos em Aspose.Words, você pode usar o`FontSubstitutionSettings` classe e o`RemoveSuffixes` propriedade. Definir esta propriedade como`true` obterá as substituições de fontes sem os sufixos adicionados.

#### P: É possível desativar a adição de sufixos às substituições de fontes no Aspose.Words?

R: Não, não é possível desabilitar a adição de sufixos às substituições de fontes no Aspose.Words. Os sufixos são adicionados por padrão para garantir a compatibilidade e consistência do documento.

#### P: Como posso filtrar sufixos indesejados em substituições de fontes no Aspose.Words?

 R: Para filtrar sufixos indesejados em substituições de fontes no Aspose.Words, você pode usar técnicas de processamento de strings, como usar o`Replace` ou`Substring` métodos para remover sufixos específicos que você não deseja incluir.