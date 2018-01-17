---
title: "Manter tipos de códigos de barra"
description: "Este procedimento mostra como configurar a definição de um novo código de barras que pode ser usado como parte do relatório da lista de separação."
author: perlynne
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 45323206550d1b0ed66d89f4be7b995c60af63fc
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="maintain-bar-code-types"></a>Manter tipos de códigos de barra

[!include[task guide banner](../../includes/task-guide-banner.md)]

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

