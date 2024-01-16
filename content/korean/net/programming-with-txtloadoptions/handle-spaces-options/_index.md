---
title: 핸들 공간 옵션
linktitle: 핸들 공간 옵션
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 TXT 문서의 공간을 관리하는 방법을 알아보세요. 불필요한 공백을 제거하고 가독성을 높였습니다.
type: docs
weight: 10
url: /ko/net/programming-with-txtloadoptions/handle-spaces-options/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 "TXT 로딩 옵션으로 공간 관리" 기능에 제공되는 C# 소스 코드를 살펴보겠습니다. 이 기능을 사용하면 TXT 문서를 로드할 때 공백 처리 동작을 지정할 수 있습니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하여 개발 환경을 설정했는지 확인하세요. 필요한 참조를 추가하고 적절한 네임스페이스를 가져왔는지 확인하세요.

## 2단계: 텍스트 문서 만들기

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

이 단계에서는 선행 및 후행 공백이 있는 줄이 포함된 텍스트 문서를 시뮬레이트하는 텍스트 문자열을 만듭니다.

## 3단계: 업로드 옵션 구성

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

 이 단계에서는 TXT 문서를 로드하기 위한 옵션을 구성합니다. 우리는 새로운 것을 만듭니다`TxtLoadOptions` 객체를 설정하고`LeadingSpacesOptions` 그리고`TrailingSpacesOptions` 속성`TxtLeadingSpacesOptions.Trim` 그리고`TxtTrailingSpacesOptions.Trim` 각기. 이는 Aspose.Words가 문서를 로드할 때 줄의 선행 및 후행 공백을 제거하도록 지시합니다.

## 4단계: 문서 로드

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

 이 단계에서는 다음을 사용하여 문서를 로드합니다.`Document` 메서드를 실행하고 지정된 텍스트 문자열과 로드 옵션이 포함된 메모리 스트림을 전달합니다.

## 5단계: 문서 저장

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

 이 마지막 단계에서는 다음을 사용하여 결과 문서를 .docx 형식으로 저장합니다.`Save` 메서드를 사용하고 경로를 출력 파일에 전달합니다.

이제 공백 처리 옵션을 지정하여 소스 코드를 실행하여 텍스트 문서를 로드할 수 있습니다. 결과 문서는 "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx"라는 이름으로 지정된 디렉터리에 저장됩니다.

### .NET용 Aspose.Words를 사용하여 TXT 로딩 옵션을 갖춘 공간 관리 기능의 샘플 소스 코드*

```csharp

            
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

const string textDoc = "      Line 1 \n" +
					   "    Line 2   \n" +
					   " Line 3       ";

TxtLoadOptions loadOptions = new TxtLoadOptions
{
	LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
	TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx")
            
        
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET에서 TXT 로딩 옵션을 사용하여 공간을 관리하는 기능을 살펴보았습니다. TXT 문서를 로드할 때 공백 처리 동작을 지정하는 방법을 배웠습니다.

이 기능은 문서의 줄 왼쪽과 오른쪽에 불필요한 공백을 처리하는 데 매우 유용합니다. 적절한 로드 옵션을 구성하면 원하지 않는 공백을 쉽게 제거할 수 있으므로 문서 내용을 더 깔끔하고 읽기 쉽게 만드는 데 도움이 됩니다.

Aspose.Words for .NET은 문서 조작 및 생성을 위한 다양한 고급 기능을 제공합니다. TXT 문서를 로드할 때 공간을 관리하는 것은 이 문서가 제공하는 많은 강력한 도구 중 하나입니다.

 특정 시나리오에 가장 적합한 공간 관리 옵션을 선택하는 것이 중요합니다. 이 예에서는`Trim`줄의 시작과 끝에서 불필요한 공백을 제거하는 옵션입니다. 그러나 Aspose.Words에는 공백을 유지하거나 완전히 제거하거나 그대로 유지하는 다른 옵션도 있습니다.

특정 요구 사항과 TXT 문서의 구조에 따라 이러한 옵션을 조정하는 것을 잊지 마십시오.

.NET용 Aspose.Words를 사용하면 문서의 공백을 쉽게 조작하여 레이아웃 품질과 콘텐츠 가독성을 향상시킬 수 있습니다.

따라서 .NET용 Aspose.Words 프로젝트의 TXT 로딩 옵션과 공백 관리를 주저하지 말고 통합하고 그 장점을 활용하여 형식이 좋고 읽기 쉬운 문서를 만드십시오.