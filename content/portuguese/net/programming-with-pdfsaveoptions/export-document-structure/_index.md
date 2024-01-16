---
title: Exportar estrutura de documento Word para documento PDF
linktitle: Exportar estrutura de documento Word para documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para exportar estrutura de documento do Word para documento PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/export-document-structure/
---

Este artigo fornece um guia passo a passo sobre como usar o recurso Exportar estrutura de documento do Word para documento PDF com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial você poderá entender como exportar a estrutura de um documento e gerar um PDF com a estrutura do documento visível.

Antes de começar, certifique-se de ter instalado e configurado a biblioteca Aspose.Words for .NET em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Passo 1: Defina o diretório do documento

 Para começar, você precisa definir o caminho para o diretório onde seus documentos estão localizados. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o documento

A seguir, precisamos carregar o documento que queremos processar. Neste exemplo, presumimos que o documento se chama "Paragraphs.docx" e está localizado no diretório de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Etapa 3: configurar as opções de salvar como PDF

 Para exportar a estrutura do documento e torná-la visível no painel de navegação "Conteúdo" do Adobe Acrobat Pro durante a edição do arquivo PDF, precisamos configurar o`PdfSaveOptions` objeto com o`ExportDocumentStructure` propriedade definida como`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Passo 4: Salve o documento como PDF com a estrutura do documento

Por fim, podemos salvar o documento em formato PDF utilizando as opções de salvamento configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Isso é tudo ! Você exportou com sucesso uma estrutura de documento e gerou um PDF com a estrutura do documento visível usando Aspose.Words for .NET.

### Exemplo de código-fonte para exportar estrutura de documento com Aspose.Words for .NET


```csharp

            // O caminho para o diretório de documentos.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // O tamanho do arquivo será aumentado e a estrutura ficará visível no painel de navegação "Conteúdo"
            // do Adobe Acrobat Pro, enquanto edita o .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## Conclusão

Neste tutorial, explicamos como exportar a estrutura de um documento Word para um documento PDF usando Aspose.Words for .NET. Seguindo as etapas descritas, você pode gerar facilmente um PDF com a estrutura do documento visível, facilitando a navegação e a pesquisa no documento. Use os recursos do Aspose.Words for .NET para exportar a estrutura de seus documentos Word e criar PDFs bem estruturados.

### perguntas frequentes

#### P: O que é exportar a estrutura de um documento Word para um documento PDF?
R: Exportar a estrutura de um documento Word para um documento PDF cria um PDF com uma estrutura de documento visível. A estrutura do documento geralmente inclui títulos, seções, parágrafos e outros elementos estruturados do documento. Esta estrutura pode ser útil para navegação e pesquisa no documento PDF.

#### P: Como posso exportar a estrutura de um documento Word para um documento PDF usando Aspose.Words for .NET?
R: Para exportar a estrutura de um documento Word para um documento PDF usando Aspose.Words for .NET, siga estas etapas:

 Crie uma instância do`Document` classe especificando o caminho para o documento do Word.

 Crie uma instância do`PdfSaveOptions` classe e definir o`ExportDocumentStructure`propriedade para`true`. Isso exportará a estrutura do documento e a tornará visível no painel de navegação “Conteúdo” do Adobe Acrobat Pro ao editar o arquivo PDF.

 Use o`Save` método do`Document`class para salvar o documento em formato PDF especificando opções de salvamento.

#### P: Como posso visualizar a estrutura de um documento PDF com o Adobe Acrobat Pro?
R: Para visualizar a estrutura de um documento PDF com Adobe Acrobat Pro, siga estas etapas:

Abra o documento PDF no Adobe Acrobat Pro.

Na barra de navegação esquerda, clique no ícone “Conteúdo” para exibir o painel de navegação “Conteúdo”.

No painel de navegação “Conteúdo”, você verá a estrutura do documento com títulos, seções e outros elementos estruturados.