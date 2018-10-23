--- 
title: "Manter tipos de código de barras"
description: "Este procedimento mostra como configurar a definição de um novo código de barras que pode ser usado como parte do relatório da lista de separação."
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a0d7092228f078f528ec1cb9ac56d7034c44bccf
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="maintain-barcode-types"></a>Manter tipos de código de barras

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar a definição de um novo código de barras que pode ser usado como parte do relatório da lista de separação. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Se você estiver usando USMF você pode usar os valores de exemplo mostrados. Essas tarefas normalmente seriam realizadas por um gerente do depósito.

1. Vá para Códigos de barras.
2. Clique em Novo.
3. No campo Configuração de código de barras, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tipo de código de barras, selecione uma opção.
    * Se você estiver usando USMF, você pode selecionar 'Código 39'.  
6. No campo Tamanho, insira um número.
7. No campo Comprimento máximo, insira um número.
8. Clique em Salvar.
9. Feche a página.
10. Vá para Parâmetros de gerenciamento de estoque e depósito.
11. No campo Configuração de código de barras, insira ou selecione um valor.
    * Selecione a configuração de código de barras que você criou antes, mas esteja ciente de que o formato do código de barras deve corresponder ao formato do identificador exclusivo para o tipo de registro usado no processo. Por exemplo, para roteiros de separação, o formato do código de barras deve corresponder ao formato da referência do roteiro de separação, que normalmente é uma sequência numérica.  
12. Clique em Salvar.
13. Feche a página.


