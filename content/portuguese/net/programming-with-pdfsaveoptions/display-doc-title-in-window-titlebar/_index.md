---
title: Exibir o título do documento na barra de título da janela
linktitle: Exibir o título do documento na barra de título da janela
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como exibir o título do documento na barra de título da janela ao converter para PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

Neste tutorial, iremos guiá-lo através das etapas para exibir o título do documento na barra de título da janela com Aspose.Words for .NET. Este recurso permite exibir o título do documento na barra de título da janela ao abrir o documento PDF gerado. Siga os passos abaixo:

## Passo 1: Carregando o documento

Comece enviando o documento que deseja converter para PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Certifique-se de especificar o caminho correto para o seu documento.

## Passo 2: Configurar opções para salvar PDF

Crie uma instância da classe PdfSaveOptions e habilite a exibição do título do documento na barra de título da janela:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Esta opção permite a exibição do título do documento na barra de título da janela ao converter para PDF.

## Passo 3: Converter Documento em PDF

 Use o`Save` método para converter o documento em PDF especificando opções de conversão:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Certifique-se de especificar o caminho correto para salvar o PDF convertido.

### Exemplo de código-fonte para exibir o título do documento na barra de título da janela usando Aspose.Words for .NET

Aqui está o código-fonte completo para exibir o título do documento na barra de título da janela em um documento PDF com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Seguindo essas etapas, você pode exibir facilmente o título do documento na barra de título da janela ao converter para PDF com Aspose.Words for .NET.

### perguntas frequentes

#### P: O que é o recurso "Mostrar título do documento na barra de título da janela" com Aspose.Words for .NET?
recurso "Mostrar título do documento na barra de título da janela" do Aspose.Words for .NET permite exibir o título do documento na barra de título da janela ao abrir o documento PDF gerado. Isto torna mais fácil identificar e distinguir documentos PDF no seu ambiente de leitura.

#### P: Como posso usar esse recurso com Aspose.Words for .NET?
Para usar este recurso com Aspose.Words for .NET, siga estas etapas:

 Carregue o documento usando o`Document` método e especificando o caminho do arquivo a ser convertido para PDF.

 Configure as opções de salvamento de PDF criando uma instância do arquivo`PdfSaveOptions` classe e definir o`DisplayDocTitle`propriedade para`true`. Isto permite a exibição do título do documento na barra de título da janela ao converter para PDF.

 Use o`Save` método para converter o documento em PDF especificando as opções de conversão.

#### P: Esse recurso altera o conteúdo do próprio documento?
Não, este recurso não modifica o conteúdo do documento em si. Afeta apenas a exibição do título do documento na barra de título da janela quando ele é aberto como um documento PDF. O conteúdo do documento permanece inalterado.

#### P: É possível personalizar o título do documento exibido na barra de título da janela?
 Sim, você pode personalizar o título do documento exibido na barra de título da janela alterando o`Document.Title` propriedade do documento antes de convertê-lo para PDF. Você pode definir o título desejado usando uma string. Certifique-se de definir o título antes de ligar para o`Save` método para converter para PDF.

#### P: Quais outros formatos de saída o Aspose.Words suporta para conversão de documentos?
Aspose.Words for .NET suporta muitos formatos de saída para conversão de documentos, como PDF, XPS, HTML, EPUB, MOBI, imagem (JPEG, PNG, BMP, TIFF, GIF) e muitos mais. ainda outros. Você pode escolher o formato de saída apropriado de acordo com suas necessidades específicas.