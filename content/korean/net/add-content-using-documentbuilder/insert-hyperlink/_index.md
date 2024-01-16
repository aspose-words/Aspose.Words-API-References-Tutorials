---
title: Word 문서에 하이퍼링크 삽입
linktitle: Word 문서에 하이퍼링크 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 사용하여 Word 문서에 하이퍼링크를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/insert-hyperlink/
---
이 포괄적인 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 하이퍼링크를 삽입하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 클릭 가능한 하이퍼링크를 문서에 추가할 수 있게 됩니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 새 문서 및 DocumentBuilder 만들기
시작하려면 Document 클래스를 사용하여 새 문서를 만들고 DocumentBuilder 객체를 초기화합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 하이퍼링크 삽입
다음으로 DocumentBuilder 클래스의 Write 메서드를 사용하여 텍스트를 추가하고 색상 및 밑줄 속성을 설정하여 하이퍼링크 서식을 지정합니다.

```csharp
builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", 거짓);

builder.Font.ClearFormatting();
builder.Write(" for more information.");
```

## 3단계: 문서 저장
하이퍼링크를 삽입한 후 Document 클래스의 Save 메서드를 사용하여 문서를 파일에 저장합니다.

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

## .NET용 Aspose.Words를 사용하여 하이퍼링크 삽입을 위한 소스 코드 예
다음은 .NET용 Aspose.Words를 사용하여 하이퍼링크를 삽입하기 위한 전체 소스 코드입니다.

하이퍼링크는 Word 문서의 상호 작용성과 유용성을 향상시키는 강력한 방법입니다. 외부 리소스를 참조하거나, 추가 정보를 제공하거나, 문서 내 탐색 요소를 만드는 데 사용할 수 있습니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", 거짓);

builder.Font.ClearFormatting();
builder.Write(" for more information.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

하이퍼링크 텍스트 및 URL을 포함하여 특정 요구 사항에 따라 코드를 조정해야 합니다. 필요에 따라 추가 형식이나 기능을 사용하여 향상시키세요.

## 결론
축하해요! Aspose.Words for .NET을 사용하여 Word 문서에 하이퍼링크를 삽입하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 문서에 클릭 가능한 하이퍼링크를 추가하여 독자를 외부 웹사이트나 특정 URL로 연결할 수 있습니다.

### Word 문서에 하이퍼링크 삽입에 대한 FAQ

#### Q: 동일한 문서 내의 특정 위치에 대한 하이퍼링크를 삽입할 수 있습니까?

A: 예, .NET용 Aspose.Words를 사용하면 동일한 문서 내의 특정 위치를 참조하는 하이퍼링크를 삽입할 수 있습니다. 북마크 기술을 사용하여 문서 내의 대상을 정의하고 해당 대상으로 이동하는 하이퍼링크를 만들 수 있습니다.

#### Q: 색상이나 스타일 변경 등 하이퍼링크 모양의 서식을 지정할 수 있나요?

답: 물론이죠! Aspose.Words for .NET은 하이퍼링크에 대한 광범위한 서식 옵션을 제공합니다. 색상, 밑줄 스타일, 글꼴 및 기타 속성을 변경하여 문서 스타일에 맞게 하이퍼링크 모양을 사용자 정의할 수 있습니다.

#### Q: 이메일 주소에 대한 하이퍼링크를 만드는 것이 가능합니까?

A: 예, 미리 입력된 이메일 주소로 기본 이메일 클라이언트를 여는 하이퍼링크를 생성할 수 있습니다. 하이퍼링크를 삽입할 때 "mailto:" 접두사 뒤에 이메일 주소를 URL 매개변수로 사용하면 됩니다.

#### Q: 하이퍼링크에 도구 설명이나 설명을 추가할 수 있나요?

A: Aspose.Words for .NET은 "제목" 속성을 사용하여 하이퍼링크에 도구 설명이나 설명을 추가하는 것을 지원합니다. 삽입된 하이퍼링크에 title 속성을 지정하면 하이퍼링크 위로 마우스를 가져갈 때 표시될 추가 정보를 제공할 수 있습니다.

#### Q: .NET용 Aspose.Words는 로컬 시스템의 파일 연결을 지원합니까?

A: 예, 상대 또는 절대 파일 경로를 사용하여 로컬 시스템의 파일에 연결되는 하이퍼링크를 만들 수 있습니다. 이 기능을 사용하면 지원 파일이나 관련 문서에 대한 링크가 포함된 문서 템플릿을 만들 수 있습니다.