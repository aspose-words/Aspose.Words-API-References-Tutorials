---
title: Word 문서의 기존 서명란에 서명하기
linktitle: Word 문서의 기존 서명란에 서명하기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 기존 서명란에 서명하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/signing-existing-signature-line/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 기존 서명란의 서명 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 Word 문서에 이미 있는 서명란에 디지털 서명을 할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 로드 및 서명란에 액세스

기존 서명란이 포함된 문서를 업로드하여 시작하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 2단계: 서명 옵션 설정

SignOptions 클래스의 인스턴스를 만들고 서명란 ID 및 서명란 이미지를 포함한 서명 옵션을 설정합니다.

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

서명란 이미지에 올바른 경로를 지정해야 합니다.

## 3단계: 인증서 로드

CertificateHolder 클래스를 사용하여 서명 인증서를 로드하는 것부터 시작하세요.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

인증서 및 관련 비밀번호의 올바른 경로를 지정하십시오.

## 4단계: 기존 서명란에 서명하기

DigitalSignatureUtil 클래스를 사용하여 기존 서명란에 서명합니다.

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

원본 문서, 서명된 문서 및 인증서에 대한 올바른 경로를 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 기존 서명란에 서명하기 위한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 기존 서명란에 서명하는 전체 소스 코드입니다.


```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

다음 단계를 따르면 Aspose.Words for .NET을 사용하여 Word 문서의 기존 서명란에 쉽게 서명할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 기존 서명란에 서명하는 방법을 배웠습니다. 제공된 단계를 따르면 쉽게 문서를 로드하고, 기존 서명란에 액세스하고, 서명 옵션을 설정하고, 문서에 서명할 수 있습니다. 기존 서명란에 서명하는 기능은 Word 문서의 미리 정의된 영역에 디지털 서명을 추가하는 편리한 방법을 제공하여 문서 무결성과 인증을 보장합니다. Aspose.Words for .NET은 디지털 서명이 포함된 단어 처리를 위한 강력한 API를 제공하여 서명 프로세스를 사용자 정의하고 Word 문서의 보안을 강화할 수 있습니다.

### FAQ

#### Q: Word 문서의 기존 서명란은 무엇입니까?

A: Word 문서의 기존 서명란은 서명을 넣을 수 있는 미리 정의된 영역입니다. 일반적으로 문서의 모양이나 개체로 표시되며 서명자가 디지털 서명을 추가할 수 있는 지정된 공간 역할을 합니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서의 기존 서명란에 어떻게 서명할 수 있나요?

A: .NET용 Aspose.Words를 사용하여 Word 문서의 기존 서명란에 서명하려면 다음 단계를 따르세요.
1.  다음을 사용하여 문서를 로드합니다.`Document` 클래스를 선택하고 문서 파일의 경로를 지정합니다.
2.  적절한 방법이나 속성을 사용하여 기존 서명란에 액세스합니다. 예를 들어 다음을 사용할 수 있습니다.`GetChild` 서명란 모양을 검색하는 방법입니다.
3.  인스턴스를 생성합니다.`SignOptions` 클래스를 설정하고`SignatureLineId` 속성을 기존 서명란의 ID로 설정합니다.
4.  설정`SignatureLineImage` 의 재산`SignOptions` 디지털 서명을 나타내는 이미지 클래스입니다.
5.  다음을 사용하여 서명 인증서를 로드합니다.`CertificateHolder` 수업을 듣고 필요한 인증서와 비밀번호를 제공하세요.
6.  사용`DigitalSignatureUtil.Sign` 문서에 서명하는 방법을 포함하여 필요한 매개변수를 제공합니다.`SignOptions` 물체.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서의 기존 서명란에 어떻게 액세스합니까?

 A: .NET용 Aspose.Words를 사용하여 Word 문서의 기존 서명란에 액세스하려면 적절한 메서드나 속성을 사용하여 문서 구조에서 서명란 모양을 검색할 수 있습니다. 예를 들어 다음을 사용할 수 있습니다.`GetChild` 원하는 서명란 모양을 얻으려면 적절한 매개변수를 사용하는 방법을 사용하세요.

#### Q: 기존 서명란의 디지털 서명 모양을 사용자 정의할 수 있습니까?

A: 예, 서명을 나타내는 이미지 파일을 제공하여 기존 서명란의 디지털 서명 모양을 사용자 정의할 수 있습니다. 이미지는 로고, 자필 서명 또는 기타 서명의 그래픽 표현일 수 있습니다. 당신은 설정할 수 있습니다`SignatureLineImage` 의 재산`SignOptions` 클래스를 이미지 파일의 바이트로 변환합니다.

#### 질문: Word 문서에 있는 여러 기존 서명란에 서명할 수 있나요?
 A: 예, Word 문서에 있는 여러 기존 서명란에 서명할 수 있습니다. 각 서명란에 대한 단계를 개별적으로 수행하여 적절하게 설정해야 합니다.`SignatureLineId` 그리고`SignatureLineImage` 의 값`SignOptions` 각 서명란에 대한 개체입니다.

#### Q: 기존 서명란의 디지털 서명을 위한 이미지 파일은 어떤 형식이어야 합니까?

 A: 기존 서명란의 디지털 서명에 대한 이미지 파일은 PNG, JPEG, BMP 또는 GIF와 같은 다양한 형식일 수 있습니다. 파일 경로를 지정하거나 이미지 파일의 바이트를 읽고 이를`SignatureLineImage` 의 재산`SignOptions` 수업.
