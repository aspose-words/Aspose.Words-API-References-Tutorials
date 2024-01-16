---
title: Word 문서에 단락 삽입
linktitle: Word 문서에 단락 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 서식 있는 단락을 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/insert-paragraph/
---
이 포괄적인 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 단락을 삽입하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 문서에 서식 있는 단락을 추가할 수 있게 됩니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 새 문서 및 DocumentBuilder 만들기
시작하려면 Document 클래스를 사용하여 새 문서를 만들고 DocumentBuilder 객체를 초기화합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 글꼴 및 서식 설정
다음으로 각각 Font 및 ParagraphFormat 개체를 사용하여 글꼴 속성과 단락 서식을 설정합니다.

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## 3단계: 단락 삽입
글꼴과 서식을 설정한 후 DocumentBuilder 클래스의 Writeln 메서드를 사용하여 전체 단락을 삽입합니다.

```csharp
builder.Writeln("A whole paragraph.");
```

## 4단계: 문서 저장
단락을 삽입한 후 Document 클래스의 Save 메서드를 사용하여 문서를 파일에 저장합니다.

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## .NET용 Aspose.Words를 사용하여 단락 삽입을 위한 소스 코드 예
다음은 .NET용 Aspose.Words를 사용하여 단락을 삽입하는 전체 소스 코드입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## 결론
축하해요! Aspose.Words for .NET을 사용하여 서식이 지정된 단락을 Word 문서에 삽입하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 특정 글꼴, 서식 및 정렬이 포함된 사용자 정의 단락을 문서에 추가할 수 있습니다.

### Word 문서에 단락 삽입에 대한 FAQ

#### Q: 동일한 문서에 서식이 다른 여러 단락을 삽입할 수 있나요?

 A: 예, Aspose.Words for .NET을 사용하여 동일한 문서에 서로 다른 서식을 가진 여러 단락을 삽입할 수 있습니다. 호출하기 전에 글꼴 및 단락 서식 속성을 조정하기만 하면 됩니다.`Writeln` 각 단락에 대한 방법.

#### Q: 단락의 줄 간격과 들여쓰기를 어떻게 설정합니까?

 A: .NET용 Aspose.Words는 단락의 줄 간격과 들여쓰기를 설정하는 옵션을 제공합니다. 당신은 조정할 수 있습니다`LineSpacing` 그리고`LeftIndent` 의 속성`ParagraphFormat` 이러한 측면을 제어하는 객체입니다.

#### Q: DocumentBuilder를 사용하여 글머리 기호 또는 번호 매기기 목록을 삽입할 수 있습니까?

 A: 예.`ListFormat` 의 속성`DocumentBuilder` 물체. 다음을 사용하여 목록 항목을 추가할 수 있습니다.`Writeln` 방법을 사용하면 번호 매기기 또는 글머리 기호 스타일이 자동으로 적용됩니다.

#### Q: 단락 내에 하이퍼링크나 기타 요소를 삽입할 수 있나요?

 답: 물론이죠! 다음을 사용하여 단락 내에 하이퍼링크, 이미지 및 기타 요소를 삽입할 수 있습니다.`DocumentBuilder` 수업. 이를 통해 단락 내에 풍부하고 대화형 콘텐츠를 만들 수 있습니다.

#### Q: 단락에 특수 문자나 기호를 삽입하려면 어떻게 해야 합니까?

 A: 특수 문자나 기호를 삽입하려면`Writeln` 원하는 유니코드 표현을 사용하여 메소드를 사용하거나`InsertSpecialChar` 의 방법`DocumentBuilder` 수업.