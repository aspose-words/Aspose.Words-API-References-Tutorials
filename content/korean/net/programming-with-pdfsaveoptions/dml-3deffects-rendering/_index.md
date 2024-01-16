---
title: PDF 문서에서 3D DML 3DEffect 렌더링
linktitle: PDF 문서에서 3D DML 3DEffect 렌더링
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF로 변환할 때 3D DML 효과 렌더링을 활성화하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 PDF로 변환할 때 3D DML 효과 렌더링을 활성화하는 단계를 안내합니다. 이렇게 하면 생성된 PDF 문서에 3D 효과가 유지됩니다. 아래 단계를 따르십시오.

## 1단계: 문서 로드

PDF로 변환하려는 문서를 업로드하여 시작하십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

문서의 올바른 경로를 지정해야 합니다.

## 2단계: PDF 저장 옵션 구성

PdfSaveOptions 클래스의 인스턴스를 만들고 3D DML 효과의 고급 렌더링을 활성화합니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

이 옵션은 생성된 PDF 문서의 3D 효과를 유지합니다.

## 3단계: 문서를 PDF로 변환

 사용`Save` 저장 옵션을 지정하여 문서를 PDF로 변환하는 방법:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

변환된 PDF를 저장할 올바른 경로를 지정했는지 확인하세요.

### .NET용 Aspose.Words를 사용한 Dml 3DEffects 렌더링의 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 PDF로 변환할 때 3D DML 효과 렌더링을 쉽게 활성화할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 PDF로 변환할 때 3D DML 효과 렌더링을 활성화하는 방법을 설명했습니다. 설명된 단계를 따르면 생성된 PDF 문서에 3D 효과를 쉽게 유지할 수 있습니다. 원본 문서의 중요한 시각 효과를 보존하려면 이 기능을 사용하십시오.


### 자주 묻는 질문

#### Q: PDF 문서에서 3D DML 효과를 렌더링한다는 것은 무엇입니까?
A: PDF 문서에서 3D DML 효과를 렌더링한다는 것은 문서를 PDF 형식으로 변환할 때 3D 효과를 유지하는 기능을 의미합니다. 이렇게 하면 시각적 효과가 유지되고 생성된 PDF 문서가 원본 문서와 비슷하게 보입니다.

#### Q: .NET용 Aspose.Words를 사용하여 PDF로 변환할 때 3D DML 효과 렌더링을 활성화하려면 어떻게 해야 합니까?
A: .NET용 Aspose.Words를 사용하여 PDF로 변환할 때 3D DML 효과 렌더링을 활성화하려면 다음 단계를 따르십시오.

 인스턴스를 생성합니다.`Document` Word 문서의 경로를 지정하는 클래스입니다.

 인스턴스를 생성합니다.`PdfSaveOptions` 클래스를 설정하고`Dml3DEffectsRenderingMode`재산`Dml3DEffectsRenderingMode.Advanced` 3D DML 효과의 고급 렌더링을 활성화합니다.

 사용`Save` 의 방법`Document`저장 옵션을 지정하여 문서를 PDF 형식으로 저장하는 클래스입니다.

#### Q: 생성된 PDF 문서에 3D DML 효과가 렌더링되었는지 어떻게 확인할 수 있나요?
A: 생성된 PDF 문서에 3D DML 효과가 렌더링되었는지 확인하려면 Adobe Acrobat Reader와 같은 호환 가능한 PDF 뷰어로 PDF 파일을 열고 문서를 검사하십시오. 원본 문서에 나타나는 대로 3D 효과를 볼 수 있습니다.



