---
title: 마지막으로 저장된 시간 속성 업데이트
linktitle: 마지막으로 저장된 시간 속성 업데이트
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 저장할 때 마지막 저장 시간 속성을 자동으로 업데이트하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 저장할 때 마지막 저장 시간 속성을 업데이트하기 위해 제공된 C# 소스 코드를 탐색합니다. 이 기능을 사용하면 생성된 문서의 마지막 저장 시간 속성을 자동으로 업데이트할 수 있습니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하여 개발 환경을 설정했는지 확인하세요. 필요한 참조를 추가하고 적절한 네임스페이스를 가져왔는지 확인하세요.

## 2단계: 문서 로드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 이 단계에서는 다음을 사용하여 문서를 로드합니다.`Document` 메서드를 사용하고 로드할 DOCX 파일의 경로를 전달합니다.

## 3단계: OOXML 백업 옵션 구성

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 이 단계에서는 다음을 사용하여 OOXML 저장 옵션을 구성합니다.`OoxmlSaveOptions` 수업. 다음을 설정하여 마지막 저장 시간 속성의 자동 업데이트를 활성화합니다.`UpdateLastSavedTimeProperty` 에게`true`.

## 4단계: 업데이트된 속성으로 문서 저장

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 이 마지막 단계에서는 다음을 사용하여 문서를 저장합니다.`Save` 메서드를 사용하여 출력 파일의 경로를 전달합니다.`.docx` 확장명과 지정된 저장 옵션이 함께 제공됩니다.

이제 문서를 저장할 때 소스 코드를 실행하여 마지막 저장 시간 속성을 자동으로 업데이트할 수 있습니다. 결과 파일은 "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx"라는 이름으로 지정된 디렉터리에 저장됩니다.

### .NET용 Aspose.Words를 사용하여 마지막으로 저장된 시간 업데이트 속성에 대한 샘플 소스 코드 

```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 저장할 때 마지막 저장 시간 속성을 자동으로 업데이트하는 기능을 살펴보았습니다. OOXML 저장 옵션으로 이 기능을 활성화하면 생성된 문서에서 마지막 저장 시간 속성이 자동으로 업데이트되도록 할 수 있습니다.

마지막 저장 시간 속성을 업데이트하면 문서의 변경 사항 및 버전을 추적하는 데 유용할 수 있습니다. 또한 문서가 마지막으로 저장된 시기를 추적하므로 다양한 시나리오에서 유용할 수 있습니다.

Aspose.Words for .NET을 사용하면 유연하고 강력한 백업 옵션을 제공하여 마지막 백업 시간 속성을 자동으로 쉽게 업데이트할 수 있습니다. 이 기능을 프로젝트에 통합하여 생성된 문서에 정확한 백업 정보가 포함되도록 할 수 있습니다.