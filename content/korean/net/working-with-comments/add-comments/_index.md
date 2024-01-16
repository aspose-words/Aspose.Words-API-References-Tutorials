---
title: 댓글 추가
linktitle: 댓글 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 설명을 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-comments/add-comments/
---

이 포괄적인 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 주석을 추가하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 문서에 주석을 삽입하고 해당 내용을 사용자 정의할 수 있게 됩니다.

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

## 2단계: 문서에 콘텐츠 추가
그런 다음 DocumentBuilder 개체를 사용하여 문서에 원하는 내용을 추가합니다. 이 예에서는 일부 텍스트를 추가합니다.

```csharp
builder.Write("Some text is added.");
```

## 3단계: 댓글 작성 및 내용 추가
댓글을 추가하려면 Document 객체, 작성자 이름, 작성자 이니셜 및 현재 날짜를 전달하여 Comment 클래스의 인스턴스를 만듭니다.

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

그런 다음 현재 단락에 주석을 추가합니다.

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

단락, 텍스트 등 댓글에 내용을 추가합니다.

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## 4단계: 문서 저장
주석과 해당 내용을 추가한 후 Document 클래스의 Save 메서드를 사용하여 문서를 파일에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## .NET용 Aspose.Words를 사용하여 주석 추가를 위한 예제 소스 코드
다음은 .NET용 Aspose.Words를 사용하여 주석을 추가하는 전체 소스 코드입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## 결론
축하해요! Aspose.Words for .NET을 사용하여 Word 문서에 주석을 추가하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 문서에 주석을 삽입하고 해당 내용을 사용자 정의할 수 있습니다.

댓글은 공동작업, 추가 정보 제공, 문서 내 메모 작성에 유용합니다. 특정 요구 사항을 충족하기 위해 다양한 작성자 이름, 이니셜 및 설명 내용을 실험해 보세요.

### FAQ

#### Q: Aspose.Words for .NET 문서에 주석을 어떻게 추가할 수 있나요?

A: Aspose.Words for .NET 문서에 주석을 추가하려면 튜토리얼에 언급된 단계를 따라야 합니다.

#### Q: .NET용 Aspose.Words에서 주석 텍스트의 서식을 지정할 수 있나요?

A: 예, 사용 가능한 서식 지정 속성을 사용하여 .NET용 Aspose.Words에서 주석 텍스트의 서식을 지정할 수 있습니다.

#### Q: 문서에 있는 모든 댓글을 어떻게 검색할 수 있나요?

A: 다음을 사용하여 문서에 있는 모든 주석을 검색할 수 있습니다.`Document.Comments` 재산.

#### Q: Aspose.Words for .NET에서 특정 댓글을 삭제할 수 있나요?

 A: 예, 다음을 사용하여 .NET용 Aspose.Words에서 특정 주석을 제거할 수 있습니다.`Comment.Remove` 방법.

#### Q: Aspose.Words for .NET에서 기존 주석 텍스트를 어떻게 수정합니까?

 A: Aspose.Words for .NET의 기존 주석 텍스트를 수정하려면`Comment.Text` 해당 속성`Comment` 개체를 선택하고 필요에 따라 텍스트를 수정합니다.