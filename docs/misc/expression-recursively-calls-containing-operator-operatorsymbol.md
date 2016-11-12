---
title: "Expression recursively calls containing Operator &#39;&lt;operatorsymbol&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BC42004"
  - "vbc42004"
helpviewer_keywords: 
  - "BC42004"
ms.assetid: a874c44a-3aec-447d-90f7-5659f1b2f5f6
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Expression recursively calls containing Operator &#39;&lt;operatorsymbol&gt;&#39;
An expression within an operator procedure uses the operator being defined. This results in the operator procedure calling itself because of the data types being used.  
  
 The operator procedure you are defining calls itself if it uses the same operator with any of the following:  
  
-   The same operands for which you are defining the operator;  
  
-   Operands of the same data types for which you are defining the operator; or  
  
-   Operands of data types that widen to the data types for which you are defining the operator.  
  
 A *recursive call* is when a procedure calls itself. Recursive calls can result in an *infinite loop*, in which control passes through the same set of statements repeatedly until your application is terminated externally. If your code does not include one or more tests that can be used to terminate recursion, you risk an infinite loop.  
  
 By default, this message is a warning. For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Error ID:** BC42004  
  
### To correct this error  
  
-   If your logic requires the operator procedure to call itself, then be sure you test for at least one condition that is certain to occur at some point, and use this test to terminate the recursive calls.  
  
-   If your logic does not require the operator procedure to call itself, then remove any recursive calls or replace them with statements that do not call their own procedure.  
  
## See Also  
 [Operator Procedures](/dotnet/visual-basic/language-reference/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)