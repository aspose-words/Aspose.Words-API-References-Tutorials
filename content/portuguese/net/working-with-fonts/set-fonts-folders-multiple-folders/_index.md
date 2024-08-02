---
title: Definir pastas de fontes em várias pastas
linktitle: Definir pastas de fontes em várias pastas
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para definir várias pastas de fontes ao renderizar um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

Neste tutorial, orientaremos você no processo passo a passo para definir várias pastas de fontes ao renderizar um documento usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como especificar várias pastas de fontes para usar ao renderizar seus documentos usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde você deseja salvar o documento renderizado editado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento para renderizar
 Então você pode carregar o documento para renderizar usando o`Document` aula. Certifique-se de especificar o caminho correto do documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: definir pastas de fontes
 Agora você pode definir várias pastas de fontes usando o`FontSettings` classe e o`SetFontsFolders()` método. Você pode especificar os caminhos para as pastas de fontes que deseja usar em uma matriz. Neste exemplo, especificamos duas pastas de fontes: "C:\MyFonts\" e "D:\Diversos\Fontes\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Etapa 4: aplicar configurações de fonte
 Em seguida, você precisa aplicar as configurações de fonte ao seu documento usando o`FontSettings` propriedade do`Document` aula.

```csharp
doc.FontSettings = fontSettings;
```

## Etapa 5: salve o documento renderizado
 Finalmente, você pode salvar o documento renderizado em um arquivo usando o`Save()` método do`Document` aula. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Exemplo de código-fonte para definir pastas de fontes múltiplas pastas usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Observe que esta configuração substituirá qualquer fonte de fonte padrão que esteja sendo pesquisada por padrão. Agora apenas essas pastas serão pesquisadas
// fontes ao renderizar ou incorporar fontes. Para adicionar uma fonte de fonte extra enquanto mantém as fontes de fonte do sistema, use FontSettings.GetFontSources e
// FontSettings.SetFontSources em vez disso.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Conclusão
Neste tutorial, aprendemos como definir várias pastas de fontes ao renderizar um documento usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode especificar facilmente várias pastas de fontes para usar ao renderizar seus documentos. Aspose.Words oferece uma API poderosa e flexível para processamento de palavras com fontes em seus documentos. Com esse conhecimento, você pode controlar e personalizar as fontes de fontes usadas ao renderizar seus documentos de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso definir várias pastas de fontes no Aspose.Words?

 R: Para definir várias pastas de fontes no Aspose.Words, você pode usar o`SetFontsFolders` método do`Fonts` classe que fornece uma lista de locais de pastas de fontes personalizadas.

#### P: A configuração de várias pastas de fontes afeta todos os documentos processados com Aspose.Words?

R: Sim, a configuração de várias pastas de fontes afeta todos os documentos processados com Aspose.Words. Depois de definir as pastas de fontes, o Aspose.Words usará esses locais para procurar fontes em todos os documentos.

#### P: Quantas pastas de fontes posso definir no Aspose.Words?

R: Você pode definir quantas pastas de fontes forem necessárias em Aspose.Words. Não há limite específico para o número de pastas de fontes que você pode definir.

#### P: Como posso verificar as pastas de fontes definidas em Aspose.Words?

 R: Para verificar as pastas de fontes definidas em Aspose.Words, você pode usar o`GetFolders` método do`Fonts` class para obter os locais das pastas de fontes configuradas.

#### P: As pastas de fontes precisam conter fontes específicas?

R: Sim, as pastas de fontes devem conter as fontes que você deseja usar em seus documentos do Word. Aspose.Words procurará fontes nas pastas especificadas ao processar documentos.