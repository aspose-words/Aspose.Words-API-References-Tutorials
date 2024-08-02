---
title: 댓글 추가
linktitle: 댓글 추가
second_title: Aspose.Words 문서 처리 API
description: 가이드와 함께 Aspose.Words for .NET을 사용하여 Word 문서에 주석을 추가하는 방법을 알아보세요. 문서 공동 작업 프로세스를 손쉽게 향상하세요.
type: docs
weight: 10
url: /ko/net/working-with-comments/add-comments/
---
## 소개

.NET용 Aspose.Words를 사용하여 Word 문서에 주석을 추가하는 방법에 대한 자세한 가이드에 오신 것을 환영합니다! 프로그래밍 방식으로 주석을 통합하여 문서 검토 프로세스를 간소화하려는 경우 올바른 위치에 오셨습니다. 이 튜토리얼은 환경 설정부터 Word 문서에 주석 작성 및 저장까지 알아야 할 모든 것을 안내합니다. 본격적으로 문서 공동작업을 쉽게 만들어 보세요!

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. .NET용 Aspose.Words: .NET용 Aspose.Words가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
2. .NET Framework: 컴퓨터에 .NET Framework가 설치되어 있는지 확인하세요.
3. 개발 환경: 코드를 작성하고 실행하기 위한 Visual Studio와 같은 IDE입니다.
4. C#에 대한 기본 지식: C# 프로그래밍 언어에 익숙하면 예제를 따라가는 데 도움이 됩니다.

## 네임스페이스 가져오기

먼저, 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이를 통해 Aspose.Words 작업에 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System;
using Aspose.Words;
```

이제 프로세스를 따라하기 쉬운 단계로 나누어 보겠습니다. 각 단계에는 논리와 기능을 이해하는 데 도움이 되는 자세한 설명이 포함되어 있습니다.

## 1단계: 문서 디렉토리 설정

 먼저 문서가 저장될 디렉터리를 정의해야 합니다. 자리 표시자를 사용하겠습니다.`YOUR DOCUMENT DIRECTORY` 실제 디렉터리 경로로 바꿔야 합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 초기화

다음으로 새 문서와 DocumentBuilder 개체를 초기화하겠습니다. DocumentBuilder는 문서를 작성하고 수정하는 데 도움이 됩니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 문서에 텍스트 추가

DocumentBuilder를 사용하여 문서에 일부 텍스트를 추가하겠습니다. 이 텍스트에 의견을 첨부할 것입니다.

```csharp
builder.Write("Some text is added.");
```

## 4단계: 댓글 작성 및 추가

이제 댓글을 작성할 차례입니다. 문서, 작성자 이름, 이니셜 및 날짜를 지정하여 새 Comment 개체를 초기화합니다.

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

## 5단계: 단락에 주석 첨부

텍스트를 추가한 현재 단락에 주석을 첨부해야 합니다. 이는 단락에 주석을 추가하여 수행됩니다.

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

## 6단계: 댓글에 콘텐츠 추가

마지막으로 댓글에 내용을 추가하겠습니다. 주석 텍스트를 보관할 새 단락 및 실행을 만든 다음 이를 주석에 추가합니다.

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## 7단계: 문서 저장

마지막 단계는 주석이 포함된 문서를 저장하는 것입니다. 디렉토리와 파일 이름을 지정하겠습니다.

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## 결론

거기 있어요! .NET용 Aspose.Words를 사용하여 Word 문서에 주석을 성공적으로 추가했습니다. 이 강력한 기능은 문서 검토 프로세스를 크게 향상시켜 보다 쉽게 협업하고 피드백을 전달할 수 있도록 해줍니다. 문서 관리 작업을 더욱 간소화하려면 Aspose.Words의 다른 기능을 탐색하는 것을 잊지 마십시오.

## FAQ

### .NET용 Aspose.Words란 무엇입니까?

Aspose.Words for .NET은 개발자가 .NET 언어를 사용하여 프로그래밍 방식으로 Word 문서를 생성, 조작 및 변환할 수 있도록 하는 강력한 API입니다.

### 단일 문서에 여러 댓글을 추가할 수 있나요?

예, 다양한 단락이나 텍스트 실행에 댓글을 만들고 추가하는 과정을 반복하여 단일 문서에 여러 댓글을 추가할 수 있습니다.

### 댓글 모양을 어떻게 맞춤설정할 수 있나요?

Aspose.Words는 주석의 내용과 구조에 중점을 두고 있지만 Word에 내장된 서식 기능을 사용하여 모양을 사용자 정의할 수 있습니다.

### 프로그래밍 방식으로 주석을 제거할 수 있습니까?

예, 문서의 주석을 반복하고 필요에 따라 제거하여 프로그래밍 방식으로 주석을 제거할 수 있습니다.

### 댓글에 답글을 추가할 수 있나요?

Aspose.Words를 사용하면 스레드된 댓글로 작업할 수 있으므로 기존 댓글에 답변을 추가하여 더 자세한 토론을 할 수 있습니다.