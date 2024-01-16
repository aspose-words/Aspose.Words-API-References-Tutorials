---
title: Exportar marcadores de rodapé de cabeçalho de documento do Word para documento PDF
linktitle: Exportar marcadores de rodapé de cabeçalho de documento do Word para documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para exportar marcadores de rodapé de cabeçalho de documento do Word para marcadores de documentos PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Este artigo fornece um guia passo a passo sobre como exportar marcadores de rodapé de cabeçalho de documento do Word para o recurso de documento PDF com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial, você poderá entender como exportar marcadores de cabeçalhos e rodapés de um documento e gerar um PDF com os marcadores apropriados.

Antes de começar, certifique-se de ter instalado e configurado a biblioteca Aspose.Words for .NET em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Passo 1: Defina o diretório do documento

 Para começar, você precisa definir o caminho para o diretório onde seus documentos estão localizados. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o documento

seguir, precisamos carregar o documento que queremos processar. Neste exemplo, presumimos que o documento se chama "Favoritos em cabeçalhos e rodapés.docx" e está localizado no diretório de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Etapa 3: configurar as opções de salvar como PDF

 Para exportar marcadores de cabeçalho e rodapé, precisamos configurar o`PdfSaveOptions` objeto. Neste exemplo, definimos o nível de contorno do marcador padrão como 1 e o modo de exportação do marcador de cabeçalho e rodapé como "Primeiro".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Etapa 4: salve o documento como PDF com marcadores de cabeçalhos e rodapés

Por fim, podemos salvar o documento em formato PDF utilizando as opções de salvamento configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Isso é tudo ! Você exportou com êxito marcadores de cabeçalho e rodapé de um documento e gerou um PDF com os marcadores apropriados usando Aspose.Words for .NET.

### Exemplo de código-fonte para exportar marcadores de cabeçalho e rodapé com Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Conclusão

Neste tutorial, explicamos como exportar marcadores de cabeçalho e rodapé de um documento Word para um documento PDF usando Aspose.Words for .NET. Os marcadores exportados permitem uma navegação fácil e uma referência rápida aos cabeçalhos e rodapés correspondentes no documento PDF gerado. Siga as etapas descritas para exportar marcadores de cabeçalho e rodapé de um documento e gerar um PDF com os marcadores apropriados usando Aspose.Words for .NET. Certifique-se de especificar o caminho correto para seus documentos e configurar as opções de salvamento conforme necessário.

### perguntas frequentes

### P: O que é exportar marcadores de cabeçalho e rodapé de um documento Word para um documento PDF?
R: Exportar marcadores de cabeçalho e rodapé de um documento Word para um documento PDF é um recurso para manter e gerar marcadores no documento PDF a partir dos cabeçalhos e rodapés. rodapés do documento original do Word. Isso permite que os usuários naveguem de forma rápida e fácil pelo documento PDF usando marcadores correspondentes aos cabeçalhos e rodapés.

### P: Como posso usar o Aspose.Words for .NET para exportar marcadores de cabeçalho e rodapé de um documento do Word para um documento PDF?
R: Para exportar marcadores de cabeçalho e rodapé de um documento Word para um documento PDF usando Aspose.Words for .NET, siga estas etapas:

 Defina o caminho do diretório onde seus documentos estão localizados, substituindo`"YOUR DOCUMENT DIRECTORY"` com o caminho real do seu diretório de documentos.

 Carregue o documento que deseja processar usando o`Document` class e especifique o caminho para o documento do Word no diretório de documentos especificado.

 Configure as opções de salvar como PDF criando uma instância do arquivo`PdfSaveOptions` class e definindo as opções apropriadas de marcador de cabeçalho e rodapé.

 Salve o documento em formato PDF usando o`Save` método do`Document` classe especificando o caminho e as opções de salvamento.

### P: Quais são os benefícios de exportar marcadores de cabeçalho e rodapé para um documento PDF?
R: As vantagens de exportar marcadores de cabeçalho e rodapé para um documento PDF são:

Navegação fácil: os marcadores permitem que os usuários naveguem facilmente em um documento PDF consultando cabeçalhos e rodapés específicos.

Referência rápida: os marcadores permitem que os usuários encontrem rapidamente seções relevantes do documento PDF com base em cabeçalhos e rodapés.