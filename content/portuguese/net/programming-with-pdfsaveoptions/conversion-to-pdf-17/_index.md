---
title: Converter documento do Word em PDF 1.7
linktitle: Converter documento do Word em PDF 1.7
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como converter documento do Word para PDF 1.7 com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

Neste tutorial, orientaremos você nas etapas de como converter um documento do Word em PDF 1.7 com Aspose.Words for .NET. A conversão para PDF 1.7 permite gerar arquivos PDF em conformidade com o padrão PDF 1.7. Siga os passos abaixo:

## Passo 1: Carregando o documento

Comece enviando o documento que deseja converter para PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Certifique-se de especificar o caminho correto para o seu documento.

## Passo 2: Definir opções de conversão de PDF

Crie uma instância da classe PdfSaveOptions e especifique a versão do padrão PDF que deseja usar:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Esta opção garante que o arquivo PDF gerado esteja em conformidade com o padrão PDF 1.7.

## Passo 3: Converter Documento em PDF

 Use o`Save` método para converter o documento em PDF especificando opções de conversão:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Certifique-se de especificar o caminho correto para salvar o PDF convertido.

### Exemplo de código-fonte para conversão em PDF 17 usando Aspose.Words for .NET

Aqui está o código-fonte completo para converter para PDF 1.7 com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Seguindo estas etapas, você pode converter facilmente para PDF 1.7 com Aspose.Words for .NET.


## Conclusão

Neste tutorial, explicamos como converter um documento do Word para PDF 1.7 usando Aspose.Words for .NET. Seguindo as etapas descritas, você pode gerar facilmente arquivos PDF que atendem ao padrão PDF 1.7. Certifique-se de especificar o caminho correto para o seu documento do Word e configurar as opções de conversão para PDF conforme necessário. A conversão para PDF 1.7 garante compatibilidade e legibilidade ideais em diferentes plataformas.

### perguntas frequentes

#### P: O que é a conversão de Word para PDF 1.7?
R: Converter documentos do Word para PDF 1.7 é gerar arquivos PDF que estejam em conformidade com o padrão PDF 1.7. Este padrão especifica recursos e requisitos para arquivos PDF, permitindo compatibilidade e legibilidade ideais em diferentes plataformas.

#### P: Como posso converter um documento do Word em PDF 1.7 usando Aspose.Words for .NET?
R: Para converter um documento do Word em PDF 1.7 usando Aspose.Words for .NET, siga estas etapas:

 Defina o caminho do diretório onde seus documentos estão localizados, substituindo`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do seu diretório de documentos.

 Carregue o documento Word que deseja converter para PDF usando o`Document` class e especifique o caminho para o documento do Word no diretório de documentos especificado.

 Configure a conversão como opções de PDF criando uma instância do`PdfSaveOptions`classe e especificando a versão do padrão PDF que você deseja usar usando o`Compliance` imóvel com o valor`PdfCompliance. Pdf17` para gerar um arquivo PDF que esteja em conformidade com o padrão PDF 1.7.

 Salve o documento em formato PDF usando o`Save` método do`Document` classe especificando o caminho e as opções de salvamento.

#### P: Quais são os benefícios da conversão para PDF 1.7 com Aspose.Words for .NET?
R: As vantagens de converter para PDF 1.7 com Aspose.Words for .NET são:

Compatível com PDF 1.7: A conversão para PDF 1.7 garante que o arquivo PDF gerado seja compatível com PDF 1.7, garantindo compatibilidade e legibilidade em diferentes plataformas.

Preservação da formatação de documentos: Aspose.Words for .NET garante a conversão precisa de documentos Word, preservando formatação, imagens e estilos, resultando em um arquivo PDF fiel ao original.