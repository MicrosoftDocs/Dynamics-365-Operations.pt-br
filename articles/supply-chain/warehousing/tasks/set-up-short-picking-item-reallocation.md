--- 
title: "Configurar realocação de item de pouca seleção"
description: "Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente localizações alternativas se não houver estoque suficiente na localização para a qual eles foram direcionados."
author: YuyuScheller
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b67965b6c8641b5d91ab3c5b0a7a7fd28a07cba6
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-short-picking-item-reallocation"></a>Configurar realocação de item de pouca seleção

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente localizações alternativas se não houver estoque suficiente na localização para a qual eles foram direcionados. É possível usar um processo de realocação automática, que usa as diretivas de localização para recuperar as mercadorias se elas estiverem disponíveis em outras localizações. Como alternativa, quando a realocação manual for usada, uma lista das localizações com a quantidade disponível é mostrada no dispositivo móvel, permitindo que o trabalhador do depósito escolha em qual localização usar o estoque. Você pode usar este procedimento na empresa USMF de dados de demonstração. Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.


## <a name="set-up-work-exceptions"></a>Configurar exceções de trabalho
1. Vá para Gerenciamento de depósito > Configuração > Trabalho > Exceções de trabalho.
2. Clique em Novo.
    * É possível definir várias exceções de trabalho com diferentes políticas de realocação de itens para permitir que os trabalhadores do depósito escolham uma com base nas necessidades da remessa que eles estão processando.  
3. No campo Código de exceção do trabalho, digite um valor.
    * Dê à exceção de trabalho um título para indicar para que ela é usada. Por exemplo, manual de separação insuficiente.  
4. No campo Descrição, digite um valor.
5. No campo Tipo de exceção, selecione "Separação insuficiente".
6. Marque a caixa de seleção Ajustar estoque.
    * Essa opção significa que o estoque será automaticamente ajustado para 0 na localização separada insuficiente.  
7. No campo Código de tipo de ajuste padrão, insira ou selecione um valor.
    * Por exemplo, na USMF, você pode selecionar "Remover Res Adj Out".  
8. No campo Realocação de item, selecione "Manual".
    * Se você selecionar Manual, ou Automática e Manual, o trabalhador do depósito precisará estar habilitado para usar a realocação manual.  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Configurar um trabalhador para usar a realocação de item manual
1. Feche a página.
2. Vá para Gerenciamento de depósito > Configuração > Trabalhador.
3. Clique em Editar.
4. Na lista, selecione o trabalhador 24.
5. Expanda a seção Trabalho.
6. Selecione Sim no campo Permitir realocação manual de itens.


