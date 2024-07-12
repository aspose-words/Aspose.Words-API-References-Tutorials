---
title: Definir pastas de fontes com prioridade
linktitle: Definir pastas de fontes com prioridade
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para definir pastas de fontes com prioridade ao renderizar um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-fonts-folders-with-priority/
---

Neste tutorial, orientaremos você no processo passo a passo para definir pastas de fontes com prioridade ao renderizar um documento usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. No final deste tutorial, você saberá como especificar várias pastas de fontes com prioridade de pesquisa personalizada ao renderizar seus documentos usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde você deseja salvar o documento renderizado editado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: definir pastas de fontes com prioridade
 Então você pode definir as pastas de fontes com prioridade usando o`FontSettings` classe e o`SetFontsSources()`método. Você pode especificar várias fontes de fonte usando instâncias de`SystemFontSource`e`FolderFontSource`. Neste exemplo, definimos duas fontes de fontes: a fonte de fontes padrão do sistema e uma pasta de fontes personalizadas com prioridade 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Etapa 3: carregue o documento para renderizar
 Agora você pode carregar o documento para renderizar usando o`Document` aula. Certifique-se de especificar o caminho correto do documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 4: salve o documento renderizado
 Finalmente, você pode salvar o documento renderizado em um arquivo usando o`Save()` método do`Document` aula. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Exemplo de código-fonte para definir pastas de fontes com prioridade usando Aspose.Words for .NET 
```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Conclusão
Neste tutorial, aprendemos como definir pastas de fontes com prioridade ao renderizar um documento usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode especificar facilmente várias pastas de fontes com prioridade de pesquisa personalizada ao renderizar seus documentos. Aspose.Words oferece uma API poderosa e flexível para processamento de palavras com fontes em seus documentos. Com esse conhecimento, você pode controlar e personalizar as fontes de fontes usadas ao renderizar seus documentos de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso definir pastas de fontes com prioridade no Aspose.Words?

 R: Para definir pastas de fontes com prioridade no Aspose.Words, você pode usar o`SetFontsFoldersWithPriority` método do`Fonts` class especificando os locais das pastas de fontes e sua ordem de prioridade.

#### P: O que acontece se uma fonte estiver presente em várias pastas com prioridades diferentes?

R: Se uma fonte estiver presente em várias pastas com prioridade diferente, o Aspose.Words usará a versão da pasta com maior prioridade ao processar documentos.

#### P: Posso especificar várias pastas de fontes com a mesma prioridade em Aspose.Words?

R: Sim, você pode especificar várias pastas de fontes com a mesma prioridade em Aspose.Words. Aspose.Words considerará todos eles com igual prioridade ao pesquisar fontes em seus documentos.

#### P: Como posso verificar as pastas de fontes definidas com prioridade no Aspose.Words?

 R: Para verificar as pastas de fontes definidas com prioridade no Aspose.Words, você pode usar o`GetFolders` método do`Fonts` class para obter a lista de pastas de fontes configuradas, incluindo sua ordem de prioridade.

#### P: Qual é a utilidade de definir pastas de fontes com prioridade no Aspose.Words?

R: Definir pastas de fontes com prioridade no Aspose.Words permite que você controle a ordem de pesquisa das fontes em seus documentos do Word. Isso ajuda a garantir que as fontes desejadas sejam usadas e evita problemas indesejados de substituição de fontes.