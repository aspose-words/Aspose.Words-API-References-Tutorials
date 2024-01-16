---
title: 압축 수준 설정
linktitle: 압축 수준 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 저장할 때 압축 수준을 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 저장할 때 압축 수준을 설정하기 위해 제공된 C# 소스 코드를 살펴보겠습니다. 이 기능을 사용하면 생성된 문서의 압축 수준을 제어할 수 있습니다.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 이 단계에서는 다음을 사용하여 OOXML 저장 옵션을 구성합니다.`OoxmlSaveOptions` 수업. 압축 수준을 다음으로 설정했습니다.`SuperFast` 더 빠른 압축을 얻으려면.

## 4단계: 지정된 압축 수준으로 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 이 마지막 단계에서는 다음을 사용하여 문서를 저장합니다.`Save` 메서드를 사용하여 출력 파일의 경로를 전달합니다.`.docx` 확장명과 지정된 저장 옵션이 함께 제공됩니다.

이제 소스 코드를 실행하여 문서를 저장할 때 압축 수준을 설정할 수 있습니다. 결과 파일은 "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx"라는 이름으로 지정된 디렉터리에 저장됩니다.

### .NET용 Aspose.Words를 사용하여 압축 수준 설정에 대한 샘플 소스 코드 

```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 저장할 때 압축 수준을 설정하는 기능을 살펴보았습니다. 적절한 압축 수준을 지정하면 문서 크기와 생성 속도를 최적화할 수 있습니다.

 그만큼`OoxmlSaveOptions` 클래스는 다음을 설정하여 압축 수준을 제어할 수 있는 유연성을 제공합니다.`CompressionLevel` 속성을 적절한 값으로 설정합니다(예:`SuperFast`. 이를 통해 특정 요구 사항에 따라 파일 크기와 백업 속도 간의 적절한 균형을 유지할 수 있습니다.

압축을 사용하면 생성된 파일의 크기를 줄여야 할 때, 특히 대용량 문서의 경우 유용할 수 있습니다. 이를 통해 문서를 보다 쉽게 저장, 공유 및 전송할 수 있습니다.

Aspose.Words for .NET은 문서 조작을 위한 다양하고 강력한 옵션과 기능을 제공합니다. 적절한 백업 옵션을 사용하면 문서 생성 프로세스를 사용자 정의하고 애플리케이션 성능을 최적화할 수 있습니다.

문서 생성 작업 흐름을 향상시키기 위해 .NET용 Aspose.Words의 더 많은 기능을 자유롭게 탐색해 보십시오.
