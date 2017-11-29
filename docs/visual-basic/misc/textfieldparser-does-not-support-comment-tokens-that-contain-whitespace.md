---
title: "Parametr TextFieldParser nie obsługuje tokenów komentarzy, które zawierają odstępu"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cd7992eb2957a6471168a95ce4c139a6af7614a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-whitespace"></a><span data-ttu-id="cce69-102">Parametr TextFieldParser nie obsługuje tokenów komentarzy, które zawierają odstępu</span><span class="sxs-lookup"><span data-stu-id="cce69-102">TextFieldParser does not support comment tokens that contain whitespace</span></span>
<span data-ttu-id="cce69-103">Podano tokenu komentarz, który zawiera biały znak.</span><span class="sxs-lookup"><span data-stu-id="cce69-103">A comment token that contains white space has been supplied.</span></span> <span data-ttu-id="cce69-104">`TextFieldParser` Nie obsługuje tokenów komentarzy, które zawierają biały znak, chyba że biały znak występuje na początku tokenu.</span><span class="sxs-lookup"><span data-stu-id="cce69-104">The `TextFieldParser` does not support comment tokens that contain white space unless the white space occurs at the beginning of the token.</span></span> <span data-ttu-id="cce69-105">Biały znak występujących na początku token jest ignorowana.</span><span class="sxs-lookup"><span data-stu-id="cce69-105">White space occurring at the beginning of a token is ignored.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cce69-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="cce69-106">To correct this error</span></span>  
  
-   <span data-ttu-id="cce69-107">Podaj poprawne tokenem.</span><span class="sxs-lookup"><span data-stu-id="cce69-107">Supply a correct comment token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce69-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cce69-108">See Also</span></span>  
 [<span data-ttu-id="cce69-109">Właściwość TextFieldParser.CommentTokens</span><span class="sxs-lookup"><span data-stu-id="cce69-109">TextFieldParser.CommentTokens Property</span></span>](http://msdn.microsoft.com/en-us/2e6b6435-4bee-4c14-a353-e8f2c82e2d61)  
 [<span data-ttu-id="cce69-110">Analizowanie plików tekstowych za pomocą obiektu TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="cce69-110">Parsing Text Files with the TextFieldParser Object</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 [<span data-ttu-id="cce69-111">TextFieldParser — obiekt</span><span class="sxs-lookup"><span data-stu-id="cce69-111">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)