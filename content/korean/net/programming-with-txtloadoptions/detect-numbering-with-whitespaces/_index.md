---
title: 공백으로 번호 매기기 감지
linktitle: 공백으로 번호 매기기 감지
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 일반 텍스트 문서에서 공백이 포함된 번호 매기기를 감지하고 목록이 올바르게 인식되는지 확인하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
## 소개

.NET 매니아를 위한 Aspose.Words! 오늘 우리는 일반 텍스트 문서의 목록을 쉽게 처리할 수 있는 흥미로운 기능에 대해 알아보겠습니다. 일부 줄이 목록이어야 하는데 Word 문서에 로드할 때 제대로 보이지 않는 텍스트 파일을 처리한 적이 있습니까? 글쎄, 우리는 공백으로 번호 매기기를 감지하는 깔끔한 트릭을 가지고 있습니다. 이 튜토리얼에서는 다음을 사용하는 방법을 안내합니다.`DetectNumberingWithWhitespaces` .NET용 Aspose.Words의 옵션을 사용하면 숫자와 텍스트 사이에 공백이 있는 경우에도 목록이 올바르게 인식되도록 할 수 있습니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

-  .NET용 Aspose.Words: 다음에서 다운로드할 수 있습니다.[Aspose 릴리스](https://releases.aspose.com/words/net/) 페이지.
- 개발 환경: Visual Studio 또는 기타 C# IDE.
- .NET Framework가 컴퓨터에 설치되어 있습니다.
- C#에 대한 기본 지식: 기본 사항을 이해하면 예제를 따라가는 데 도움이 됩니다.

## 네임스페이스 가져오기

코드를 시작하기 전에 프로젝트에 필요한 네임스페이스를 가져왔는지 확인하세요. 다음은 시작하는 데 도움이 되는 간단한 스니펫입니다.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Loading;
```

프로세스를 간단하고 관리 가능한 단계로 나누어 보겠습니다. 각 단계는 필요한 코드를 안내하고 무슨 일이 일어나는지 설명합니다.

## 1단계: 문서 디렉터리 정의

먼저 문서 디렉터리 경로를 설정해 보겠습니다. 여기에 입력 및 출력 파일이 저장됩니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 일반 텍스트 문서 만들기

다음으로 일반 텍스트 문서를 문자열로 생성하겠습니다. 이 문서에는 목록으로 해석될 수 있는 부분이 포함되어 있습니다.

```csharp
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";
```

## 3단계: LoadOptions 구성

 공백이 포함된 번호 매기기를 감지하려면 다음을 설정해야 합니다.`DetectNumberingWithWhitespaces` 옵션`true` 안에`TxtLoadOptions` 물체.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

## 4단계: 문서 로드

 이제 다음을 사용하여 문서를 로드해 보겠습니다.`TxtLoadOptions` 매개변수로. 이렇게 하면 네 번째 목록(공백 포함)이 올바르게 감지됩니다.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

## 5단계: 문서 저장

마지막으로 문서를 지정된 디렉터리에 저장합니다. 그러면 올바르게 검색된 목록이 포함된 Word 문서가 출력됩니다.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

## 결론

그리고 거기에 있습니다! 단 몇 줄의 코드만으로 Aspose.Words for .NET을 사용하여 일반 텍스트 문서에서 공백이 포함된 번호 매기기를 감지하는 기술을 마스터했습니다. 이 기능은 다양한 텍스트 형식을 처리하고 목록이 Word 문서에 정확하게 표시되는지 확인할 때 매우 유용합니다. 따라서 다음에 이러한 까다로운 목록을 접하게 되면 무엇을 해야 할지 정확히 알게 될 것입니다.

## FAQ

###  무엇인가요`DetectNumberingWithWhitespaces` in Aspose.Words for .NET?
`DetectNumberingWithWhitespaces` 의 옵션입니다`TxtLoadOptions` 이는 번호 매기기와 목록 항목 텍스트 사이에 공백이 있는 경우에도 Aspose.Words가 목록을 인식할 수 있게 해줍니다.

### 글머리 기호 및 대괄호와 같은 다른 구분 기호에 이 기능을 사용할 수 있습니까?
 예, Aspose.Words는 글머리 기호 및 괄호와 같은 일반적인 구분 기호가 있는 목록을 자동으로 감지합니다. 그만큼`DetectNumberingWithWhitespaces` 특히 공백이 있는 목록에 도움이 됩니다.

###  사용하지 않으면 어떻게 되나요?`DetectNumberingWithWhitespaces`?
이 옵션이 없으면 번호 매기기와 텍스트 사이에 공백이 있는 목록이 목록으로 인식되지 않고 항목이 일반 단락으로 나타날 수 있습니다.

### 이 기능을 다른 Aspose 제품에서도 사용할 수 있나요?
이 특정 기능은 Word 문서 처리를 처리하도록 설계된 Aspose.Words for .NET에 맞게 조정되었습니다.

### .NET용 Aspose.Words의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[임시 면허를 양도하다](https://purchase.aspose.com/temporary-license/) 페이지.

