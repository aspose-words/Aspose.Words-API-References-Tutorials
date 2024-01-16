---
title: Word 문서에 부동 이미지 삽입
linktitle: Word 문서에 부동 이미지 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 부동 이미지를 삽입하는 방법을 알아보세요. 단계별 가이드.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/insert-floating-image/
---
이 포괄적인 예에서는 Aspose.Words for .NET을 사용하여 Word 문서에 부동 이미지를 삽입하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 사용자 정의 가능한 위치 지정 및 래핑 옵션이 포함된 이미지를 문서에 추가할 수 있게 됩니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 새 문서 및 DocumentBuilder 만들기
시작하려면 Document 클래스를 사용하여 새 문서를 만들고 DocumentBuilder 객체를 초기화합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 플로팅 이미지 삽입
다음으로 DocumentBuilder 클래스의 InsertImage 메서드를 사용하여 부동 이미지를 삽입합니다. 이미지 파일 경로, 상대 수평 및 수직 위치, 너비, 높이 및 줄바꿈 옵션을 매개변수로 제공합니다.

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## 3단계: 문서 저장
부동 이미지를 삽입한 후 Document 클래스의 Save 메서드를 사용하여 문서를 파일에 저장합니다.

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## .NET용 Aspose.Words를 사용하여 부동 이미지 삽입을 위한 예제 소스 코드
다음은 .NET용 Aspose.Words를 사용하여 부동 이미지를 삽입하기 위한 전체 소스 코드입니다.
플로팅 이미지는 문서의 텍스트와 독립적으로 배치할 수 있는 로고, 일러스트레이션 또는 장식 요소를 추가하는 등 다양한 시나리오에 유용합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

이미지 파일 경로, 원하는 위치 지정 및 래핑 옵션을 포함하여 특정 요구 사항에 따라 코드를 조정해야 합니다.

## 결론
축하해요! Aspose.Words for .NET을 사용하여 Word 문서에 부동 이미지를 삽입하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 시각적으로 매력적이고 사용자 정의가 가능한 플로팅 이미지로 문서를 향상시킬 수 있습니다.

### Word 문서에 부동 이미지 삽입에 대한 FAQ

#### Q: 단일 문서에 여러 개의 부동 이미지를 삽입할 수 있나요?

답: 물론이죠! .NET용 Aspose.Words를 사용하여 Word 문서에 필요한 만큼 부동 이미지를 삽입할 수 있습니다. 시각적으로 매력적인 여러 이미지를 추가하려면 삽입 과정을 반복하기만 하면 됩니다.

#### Q: 플로팅 이미지에는 어떤 래핑 옵션을 사용할 수 있나요?

A: Aspose.Words for .NET은 Square, Tight, Through, TopBottom 및 None을 포함하여 부동 이미지에 대한 다양한 래핑 옵션을 제공합니다. 이러한 옵션은 텍스트가 부동 이미지와 상호 작용하는 방식을 결정합니다.

#### Q: 플로팅 이미지의 크기를 조정할 수 있나요?

답: 물론이죠! InsertImage 메서드의 해당 매개 변수를 사용하여 부동 이미지의 너비와 높이를 지정할 수 있습니다. 이를 통해 디자인 기본 설정에 따라 이미지의 크기를 제어할 수 있습니다.

#### Q: 문서의 특정 요소를 기준으로 부동 이미지를 배치할 수 있나요?

A: 예, .NET용 Aspose.Words를 사용하면 여백, 페이지, 단락 또는 표와 같은 특정 요소를 기준으로 부동 이미지를 배치할 수 있습니다. 적절한 상대 수평 및 수직 위치 매개변수를 선택하여 원하는 배치를 얻을 수 있습니다.

#### Q: Aspose.Words for .NET은 데스크탑과 웹 애플리케이션 모두에 적합합니까?

A: 네, Aspose.Words for .NET은 데스크탑과 웹 애플리케이션 모두에 적합한 다용도 라이브러리입니다. Windows 애플리케이션을 구축하든 웹 기반 시스템을 구축하든 상관없이 라이브러리를 손쉽게 통합할 수 있습니다.
