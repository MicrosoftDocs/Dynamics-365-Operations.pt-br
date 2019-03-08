---
title: Configurar realocação de item de pouca seleção
description: Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente localizações alternativas se não houver estoque suficiente na localização para a qual eles foram direcionados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bf56a0811c4793ee2e3eaf78c8696c3c29e984c3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "361213"
---
# <a name="set-up-short-picking-item-reallocation"></a>Configurar realocação de item de pouca seleção

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como permitir que os trabalhadores do depósito encontrem rapidamente localizações alternativas se não houver estoque suficiente na localização para a qual eles foram direcionados. É possível usar um processo de realocação automática, que usa as diretivas de localização para recuperar as mercadorias se elas estiverem disponíveis em outras localizações. Como alternativa, quando a realocação manual for usada, uma lista das localizações com a quantidade disponível é mostrada no dispositivo móvel, permitindo que o trabalhador do depósito escolha em qual localização usar o estoque. Você pode usar este procedimento na empresa USMF de dados de demonstração. Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


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

