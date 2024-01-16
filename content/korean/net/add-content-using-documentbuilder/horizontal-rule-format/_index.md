---
title: Word 문서의 수평 규칙 형식
linktitle: Word 문서의 수평 규칙 형식
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 가로 규칙의 형식을 지정하는 방법을 알아보세요. 단계별 가이드.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/horizontal-rule-format/
---
이 포괄적인 예에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 수평선의 형식을 지정하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 수평선의 정렬, 너비, 높이, 색상 및 기타 속성을 사용자 정의할 수 있습니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: DocumentBuilder 만들기 및 수평선 삽입
시작하려면 DocumentBuilder 개체를 만들고 InsertHorizontalRule 메서드를 사용하여 수평선을 삽입합니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## 2단계: 수평 규칙 형식에 액세스
다음으로 Shape 개체의 HorizonRuleFormat 속성에 액세스하여 서식 지정 옵션을 검색합니다.

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## 3단계: 서식 옵션 사용자 정의
이제 수평선에 대한 다양한 서식 옵션을 사용자 정의할 수 있습니다. 예를 들어 정렬, 너비, 높이, 색상 및 음영을 조정할 수 있습니다.

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## 4단계: 문서 저장
수평선의 서식을 지정한 후 Document 개체의 Save 메서드를 사용하여 문서를 파일에 저장합니다.

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### .NET용 Aspose.Words를 사용하는 수평 규칙 형식의 예제 소스 코드
다음은 .NET용 Aspose.Words를 사용하여 수평선 형식을 지정하기 위한 전체 소스 코드입니다.

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

특정 요구 사항에 따라 코드를 조정하고 필요에 따라 추가 기능을 사용하여 코드를 향상시키는 것을 잊지 마십시오.

## 결론
축하해요! .NET용 Aspose.Words를 사용하여 Word 문서에서 수평선 형식을 지정하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 가로 규칙의 모양을 사용자 정의하여 문서의 시각적 레이아웃을 향상시킬 수 있습니다.

가로 눈금자에 대해 원하는 스타일과 효과를 얻으려면 다양한 서식 옵션을 실험해 보세요.

### Word 문서의 수평선 형식에 대한 FAQ

#### Q: 수평선에 다른 색상을 적용할 수 있나요?

답: 물론이죠! Aspose.Words for .NET을 사용하면 Color 속성을 원하는 색상 값으로 설정하여 수평선의 색상을 쉽게 사용자 정의할 수 있습니다. 이를 통해 수평선을 문서의 전체 디자인과 일치시킬 수 있습니다.

#### Q: 수평선의 너비와 높이를 조정할 수 있나요?

A: 예, 수평선의 너비와 높이를 완전히 제어할 수 있습니다. WidthPercent 및 Height 속성을 수정하면 수평선에 대해 원하는 치수를 얻을 수 있습니다.

#### Q: 문서 내 수평선 정렬을 변경할 수 있나요?

답: 물론이죠! Aspose.Words for .NET을 사용하면 Alignment 속성을 사용하여 수평선 정렬을 지정할 수 있습니다. 가운데, 왼쪽, 오른쪽, 양쪽 맞춤 등 다양한 옵션 중에서 선택할 수 있습니다.

#### Q: 수평선에 음영이나 배경색을 적용할 수 있나요?

A: 네, 수평선에 음영이나 배경색을 추가할 수 있습니다. 기본적으로 NoShade 속성은 true로 설정되어 있지만 false로 설정하고 적절한 방법을 사용하여 음영을 정의할 수 있습니다.

#### Q: 단일 문서에 여러 개의 가로줄을 삽입할 수 있나요?

답: 물론이죠! Aspose.Words for .NET을 사용하여 Word 문서에 여러 개의 수평선을 삽입할 수 있습니다. 필요한 만큼 수평 규칙을 추가하려면 튜토리얼의 단계를 반복하세요.