---
title: 공백으로 번호 매기기 감지
linktitle: 공백으로 번호 매기기 감지
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words에서 공백이 포함된 목록 번호를 감지하는 방법을 알아보세요. 문서 구조를 쉽게 개선하세요.
type: docs
weight: 10
url: /ko/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 "공백으로 번호 매기기 감지" 기능에 제공된 C# 소스 코드를 살펴보겠습니다. 이 기능을 사용하면 목록 번호와 공백이 포함된 텍스트 문서에서 목록을 감지하고 생성할 수 있습니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하여 개발 환경을 설정했는지 확인하세요. 필요한 참조를 추가하고 적절한 네임스페이스를 가져왔는지 확인하세요.

## 2단계: 텍스트 문서 만들기

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
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

이 단계에서는 목록 번호와 공백이 포함된 텍스트 문서를 시뮬레이트하는 텍스트 문자열을 만듭니다. 마침표, 오른쪽 대괄호, 글머리 기호 및 공백과 같은 다양한 목록 구분 기호를 사용합니다.

## 3단계: 업로드 옵션 구성

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 이 단계에서는 문서 로드 옵션을 구성합니다. 우리는 새로운 것을 만듭니다`TxtLoadOptions` 객체를 설정하고`DetectNumberingWithWhitespaces`재산`true`. 이렇게 하면 Aspose.Words가 뒤에 공백이 있어도 목록 번호를 감지할 수 있습니다.

## 4단계: 문서 로드 및 저장

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 이 단계에서는 지정된 텍스트 문자열과 로드 옵션을 사용하여 문서를 로드합니다. 우리는`MemoryStream` 텍스트 문자열을 메모리 스트림으로 변환합니다. 그런 다음 결과 문서를 .docx 형식으로 저장합니다.

### .NET용 Aspose.Words를 사용한 공백 번호 매기기 감지 기능의 샘플 소스 코드입니다.

```csharp

            
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// 목록으로 해석될 수 있는 부분이 포함된 문자열 형식의 일반 텍스트 문서를 만듭니다.
// 로드 시 처음 세 개의 목록은 항상 Aspose.Words에 의해 감지됩니다.
// 로드 후 목록 개체가 생성됩니다.
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

// 네 번째 목록은 목록 번호와 목록 항목 내용 사이에 공백이 있습니다.
// LoadOptions 개체의 "DetectNumberingWithWhitespaces"가 true로 설정된 경우에만 목록으로 감지됩니다.
// 숫자로 시작하는 단락이 목록으로 잘못 감지되는 것을 방지합니다.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// LoadOptions를 파라미터로 적용하면서 문서를 로딩하고 결과를 확인합니다.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

이제 소스 코드를 실행하여 공백이 있는 목록 번호가 포함된 텍스트 문서를 로드한 다음 감지된 목록이 있는 .docx 문서를 만들 수 있습니다. 출력 파일은 "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx"라는 이름으로 지정된 디렉터리에 저장됩니다.

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words의 공백 번호 매기기 감지 기능을 살펴보았습니다. 우리는 목록 번호와 공백이 포함된 텍스트 문서에서 목록을 만드는 방법을 배웠습니다.

이 기능은 다양한 형식의 목록 번호가 포함된 문서를 처리하는 데 매우 유용합니다. Aspose.Words는 적절한 로딩 옵션을 사용하여 이러한 목록 번호 뒤에 공백이 있어도 이를 감지하고 최종 문서에서 구조화된 목록으로 변환할 수 있습니다.

이 기능을 사용하면 시간을 절약하고 작업흐름 효율성을 향상시킬 수 있습니다. 텍스트 문서에서 정보를 쉽게 추출하고 적절한 목록이 포함된 잘 구성된 문서로 변환할 수 있습니다.

원하는 결과를 얻으려면 공백 전화 걸기 감지 구성과 같은 로딩 옵션을 고려해야 합니다.

Aspose.Words for .NET은 문서 조작 및 생성을 위한 다양한 고급 기능을 제공합니다. Aspose.Words에서 제공하는 문서와 예제를 더 자세히 살펴보면 이 강력한 라이브러리의 기능을 완전히 활용할 수 있습니다.

따라서 주저하지 말고 공백 번호 매기기 감지를 Aspose.Words for .NET 프로젝트에 통합하고 그 이점을 활용하여 잘 구조화되고 읽기 쉬운 문서를 만드십시오.


