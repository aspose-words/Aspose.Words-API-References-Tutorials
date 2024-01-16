---
title: Renderizar efeitos 3D DML 3DEffects em um documento PDF
linktitle: Renderizar efeitos 3D DML 3DEffects em um documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como habilitar a renderização de efeitos DML 3D ao converter para PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

Neste tutorial, orientaremos você nas etapas para ativar a renderização do efeito DML 3D ao converter para PDF com Aspose.Words for .NET. Isso mantém os efeitos 3D no documento PDF gerado. Siga os passos abaixo:

## Passo 1: Carregando o documento

Comece enviando o documento que deseja converter para PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Certifique-se de especificar o caminho correto para o seu documento.

## Passo 2: Configurar opções de salvamento de PDF

Crie uma instância da classe PdfSaveOptions e habilite a renderização avançada de efeitos DML 3D:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Esta opção mantém os efeitos 3D no documento PDF gerado.

## Passo 3: Converter Documento em PDF

 Use o`Save` método para converter o documento em PDF especificando opções de salvamento:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Certifique-se de especificar o caminho correto para salvar o PDF convertido.

### Exemplo de código-fonte para renderização Dml 3DEffects usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Seguindo essas etapas, você pode ativar facilmente a renderização de efeitos DML 3D ao converter para PDF com Aspose.Words for .NET.

## Conclusão

Neste tutorial, explicamos como habilitar a renderização de efeitos DML 3D ao converter para PDF com Aspose.Words for .NET. Seguindo as etapas descritas, você pode facilmente manter os efeitos 3D no documento PDF gerado. Use este recurso para preservar os efeitos visuais importantes do documento original.


### perguntas frequentes

#### P: O que é a renderização de efeitos DML 3D em um documento PDF?
R: A renderização de efeitos 3D DML em um documento PDF refere-se à capacidade de reter efeitos 3D ao converter um documento para o formato PDF. Isso preserva os efeitos visuais e garante que o documento PDF gerado se pareça com o documento original.

#### P: Como posso ativar a renderização de efeitos DML 3D ao converter para PDF com Aspose.Words for .NET?
R: Para ativar a renderização de efeitos DML 3D ao converter para PDF com Aspose.Words for .NET, siga estas etapas:

 Crie uma instância do`Document` classe especificando o caminho para o documento do Word.

 Crie uma instância do`PdfSaveOptions` classe e definir o`Dml3DEffectsRenderingMode`propriedade para`Dml3DEffectsRenderingMode.Advanced` para permitir a renderização avançada de efeitos DML 3D.

 Use o`Save` método do`Document`class para salvar o documento em formato PDF especificando opções de salvamento.

#### P: Como posso verificar se os efeitos DML 3D foram renderizados no documento PDF gerado?
R: Para verificar se os efeitos 3D DML foram renderizados no documento PDF gerado, abra o arquivo PDF com um visualizador de PDF compatível, como o Adobe Acrobat Reader, e examine o documento. Você deverá ver os efeitos 3D conforme aparecem no documento original.



