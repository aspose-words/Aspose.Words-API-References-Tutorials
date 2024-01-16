---
title: 스마트 아트 드로잉 업데이트
linktitle: 스마트 아트 드로잉 업데이트
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 스마트 아트 그림을 업데이트하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/update-smart-art-drawing/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 스마트 아트 그림을 업데이트하는 방법을 설명합니다. 문서의 도형을 반복하고 스마트 아트가 있는지 확인하면 데이터 변경 사항을 반영하도록 스마트 아트 드로잉을 업데이트할 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드
다음을 사용하여 스마트 아트 드로잉이 포함된 Word 문서를 로드합니다.`Document` 클래스 생성자.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## 3단계: 스마트 아트 드로잉 업데이트
 다음을 사용하여 문서의 모양을 반복합니다.`GetChildNodes` 방법`NodeType.Shape` 매개변수. 다음을 사용하여 각 도형에 스마트 아트가 있는지 확인하세요.`HasSmartArt` 속성을 확인하고, true인 경우`UpdateSmartArtDrawing` 스마트 아트 도면을 업데이트하는 방법입니다.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### .NET용 Aspose.Words를 사용하여 스마트 아트 드로잉 업데이트에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서의 스마트 아트 그림을 성공적으로 업데이트했습니다.