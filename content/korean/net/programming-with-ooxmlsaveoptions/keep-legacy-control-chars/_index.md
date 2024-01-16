---
title: 레거시 제어 문자 유지
linktitle: 레거시 제어 문자 유지
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 문서를 저장할 때 레거시 제어 문자를 보존하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 저장할 때 레거시 제어 문자를 보존하기 위해 제공된 C# 소스 코드를 살펴보겠습니다. 이 기능을 사용하면 문서를 변환하거나 저장할 때 특수 제어 문자를 유지할 수 있습니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하여 개발 환경을 설정했는지 확인하세요. 필요한 참조를 추가하고 적절한 네임스페이스를 가져왔는지 확인하세요.

## 2단계: 문서 로드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 이 단계에서는 다음을 사용하여 문서를 로드합니다.`Document` 메서드를 사용하고 상속된 제어 문자가 포함된 파일의 경로를 전달합니다.

## 3단계: OOXML 백업 옵션 구성

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 이 단계에서는 새로운 생성을 통해 OOXML 저장 옵션을 구성합니다.`OoxmlSaveOptions` 물체. 원하는 저장 형식을 지정합니다(여기서는`FlatOpc` )를 활성화하고`KeepLegacyControlChars` 레거시 제어 문자를 유지하는 옵션입니다.

## 4단계: 레거시 제어 문자를 사용하여 문서 저장

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 이 마지막 단계에서는 다음을 사용하여 문서를 저장합니다.`Save` 메서드를 사용하여 출력 파일의 경로를 전달합니다.`.docx` 확장명과 지정된 저장 옵션이 함께 제공됩니다.

이제 문서를 저장할 때 소스 코드를 실행하여 레거시 제어 문자를 보존할 수 있습니다. 결과 파일은 "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx"라는 이름으로 지정된 디렉터리에 저장됩니다.

### .NET용 Aspose.Words를 사용하여 기존 제어 문자 유지에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서를 저장할 때 레거시 제어 문자를 보존하는 기능을 살펴보았습니다. 우리는 적절한 문서 형식이나 표시에 중요할 수 있는 특수 문자를 보존하는 방법을 배웠습니다.

 레거시 제어 문자를 보존하는 것은 특수 제어 문자와 같이 오래되었거나 특정 기능을 사용하는 문서를 단어 처리할 때 특히 유용합니다. 활성화함으로써`KeepLegacyControlChars` 문서를 저장할 때 옵션을 사용하면 이러한 문자가 유지되는지 확인할 수 있습니다.

Aspose.Words for .NET은 문서 조작 요구 사항을 충족할 수 있는 유연하고 강력한 백업 옵션을 제공합니다. 적절한 옵션을 사용하면 문서의 특정 특성을 유지하도록 백업 프로세스를 사용자 정의할 수 있습니다.

문서에서 레거시 제어 문자의 무결성과 보존을 보장하려면 이 기능을 .NET용 Aspose.Words 프로젝트에 자유롭게 통합하세요.