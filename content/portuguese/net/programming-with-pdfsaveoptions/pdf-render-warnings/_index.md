---
title: Avisos de renderização de PDF
linktitle: Avisos de renderização de PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para lidar com avisos de renderização de PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

Este artigo fornece um guia passo a passo sobre como usar o recurso de avisos de renderização de PDF com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial, você poderá entender como lidar com avisos de renderização ao converter para PDF.

Antes de começar, certifique-se de ter instalado e configurado a biblioteca Aspose.Words for .NET em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Passo 1: Defina o diretório do documento

 Para começar, você precisa definir o caminho para o diretório onde seus documentos estão localizados. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o documento

seguir, precisamos carregar o documento que queremos processar. Neste exemplo, presumimos que o documento se chama "WMF com image.docx" e está localizado no diretório de documentos especificado.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Etapa 3: configurar opções de salvar como PDF com avisos de renderização

 Para lidar com avisos de renderização ao converter para PDF, precisamos configurar o`MetafileRenderingOptions` objeto para especificar como os metarquivos são renderizados. Também usamos o`HandleDocumentWarnings` opção para lidar com os avisos gerados ao salvar o documento.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Passo 4: Salve o documento como PDF com avisos de renderização

Por fim, podemos salvar o documento em formato PDF utilizando as opções de salvamento configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Etapa 5: lidar com avisos de renderização

Os avisos de renderização gerados ao salvar o documento podem ser recuperados usando o manipulador de avisos personalizado. Neste exemplo, simplesmente imprimimos a descrição de cada aviso.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

Isso é tudo ! Você tratou com sucesso os avisos de renderização ao converter um documento

  para PDF usando Aspose.Words para .NET.

### Exemplo de código-fonte para avisos de renderização de PDF com Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	//Se Aspose.Words não puder renderizar corretamente alguns dos registros do metarquivo
	// para gráficos vetoriais, o Aspose.Words renderiza esse metarquivo em um bitmap.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Embora o arquivo seja salvo com sucesso, os avisos de renderização que ocorreram durante o salvamento são coletados aqui.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

### perguntas frequentes

#### P: Qual é a funcionalidade dos avisos de renderização de PDF com Aspose.Words for .NET?
O recurso Avisos de renderização de PDF com Aspose.Words for .NET ajuda a gerenciar avisos gerados ao converter um documento em PDF. Ele fornece uma maneira de detectar e resolver avisos de renderização para garantir a qualidade e integridade do documento convertido.

#### P: Como posso usar esse recurso com Aspose.Words for .NET?
Para usar este recurso com Aspose.Words for .NET, siga estas etapas:

Defina o diretório do documento especificando o caminho do diretório onde seus documentos estão localizados.

 Carregue o documento a ser processado usando o`Document` método e especificando o caminho do arquivo.

 Configure as opções de salvar em PDF criando uma instância do arquivo`PdfSaveOptions` aula. Use o`MetafileRenderingOptions` classe para especificar como os metarquivos são renderizados e definir`MetafileRenderingOptions.RenderingMode` para`MetafileRenderingMode.VectorWithFallback`.

 Use o`HandleDocumentWarnings` classe para lidar com avisos de renderização. Definir`doc.WarningCallback` para uma instância desta classe.

 Use o`Save` método para salvar o documento em formato PDF especificando as opções de salvamento.

Você pode então lidar com avisos de renderização usando o`HandleDocumentWarnings` aula. Por exemplo, você pode exibir a descrição de cada aviso usando um loop.

#### P: Como posso saber se houve algum aviso de renderização ao converter o documento para PDF?
 Você pode usar o`HandleDocumentWarnings` classe para recuperar avisos de renderização gerados ao salvar o documento. Esta classe contém um`mWarnings` list que armazena informações sobre avisos. Você pode navegar nesta lista e acessar as propriedades de cada aviso, como a descrição, para tomar as medidas apropriadas.

#### P: Que tipo de avisos de renderização podem ser gerados ao converter para PDF?
Os avisos de renderização ao converter para PDF podem incluir avisos relacionados ao layout, fontes ausentes, imagens não suportadas, problemas de compatibilidade, etc. Os avisos específicos dependerão do conteúdo do documento de origem e das opções de conversão utilizadas.

#### P: É possível lidar com avisos de renderização de maneira personalizada?
 Sim, você pode personalizar o tratamento de avisos de renderização personalizando o`HandleDocumentWarnings`aula. Você pode adicionar funcionalidades adicionais para gerenciar avisos específicos do seu aplicativo, como registrar avisos, gerar relatórios, enviar alertas e muito mais.