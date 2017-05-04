---
title: Ordens de quarentena
description: "Este artigo descreve como as ordens de quarentena são usadas para bloquear o estoque."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 394276e6908f2c1f6bc72eea061facc3afe701e9
ms.lasthandoff: 03/31/2017


---

# <a name="quarantine-orders"></a>Ordens de quarentena

[!include[banner](../includes/banner.md)]


Este artigo descreve como as ordens de quarentena são usadas para bloquear o estoque. 

As ordens de quarentena podem ser usadas para bloquear o estoque. Por exemplo, talvez você deseje quarentena itens por motivos de controle de qualidade. Estoque que ficou em quarentena transferido para um depósito de quarentena. **Observação:** se você estiver usando processos avançados de gerenciamento de depósito (em Gerenciamento de depósito), o processamento da ordem de quarentena será usado somente para devolver ordens de venda.

## <a name="quarantine-onhand-inventory-items"></a>Itens de estoque disponíveis em quarentena
Ao colocar itens em quarentena, você pode criar ordens de quarentena manualmente ou configurar o sistema para criar automaticamente ordens de quarentena durante o processamento de entrada. Para criar automaticamente ordens de quarentena, selecione a opção **Gerenciamento de quarentena** na guia **Políticas de estoque** na página **Grupos de modelos de item**. Você também deve especificar um depósito de quarentena padrão no campo **Depósito de quarentena** para os depósitos de recebimento. Quando o estoque fisicamente disponível for registrado em uma ordem de compra ou em uma ordem de produção, os itens em quarentena serão automaticamente movidos para um depósito de quarentena no Microsoft Dynamics 365 for Operations. Esse movimento ocorre porque o status da ordem de quarentena é alterado para **Iniciado**. Quando você cria ordens de quarentena manualmente, o item não precisa ser configurado para gerenciamento de quarentena no grupo de modelos do item associado. Para esse processo, você deve especificar o estoque disponível que deve estar em quarentena e o depósito de quarentena que deve ser usado. Você pode usar os status da ordem de quarentena para ajudar a planejar o processo.

## <a name="quarantine-order-statuses"></a>Status da ordem de quarentena
As ordens de quarentena podem ter os seguintes status:

-   Criado em
-   Iniciado
-   Relatado como concluído
-   Concluído

### <a name="created"></a>Criado em

Quando uma ordem de quarentena tiver sido criada manualmente, mas o item ainda não estiver colocado no depósito de quarentena, a ordem de quarentena fica com o status **Criado**. Duas transações de estoque são geradas. Uma transação é uma transação de saída que pode ter um status **Na ordem**, **Qtd. reservada** ou **Separado**. A outra transação é uma transação de de recebimento que pode ter o status **Encomendado** ou **Registrado** no depósito de quarentena. Você pode reservar, separar e registrar atualizações no estoque usando os processos normais.

### <a name="started"></a>Iniciado

Quando uma ordem de quarentena tem o status **Iniciado**, o estoque é transferido do depósito normal para o depósito de quarentena, e duas transações de estoque são geradas. Uma transação tem o status **Deduzido** e a outra transação, o status **Recebido**. Ao mesmo tempo, duas transações de estoque são criadas para tratar da transferência de retorno. Essas transações não são datadas. Uma transação tem o status **Qtd. reservada** e a outra transação, o status **Encomendado**.

### <a name="reported-as-finished"></a>Relatado como concluído

Ao clicar em **Relatar como concluído**, você poderá relatar uma ordem de quarentena iniciada como concluída. O item é liberado da quarentena, mas ainda não é retornado para o depósito normal. O movimento de volta ao depósito normal pode ser processado por meio de um Diário de entrada de item que pode ser inicializado durante o o processo Relatar como concluído.

### <a name="ended"></a>Concluído

Quando uma ordem de quarentena é finalizada, o item é movido do depósito de quarentena para o depósito normal novamente. O status da transação de item é definido como **Vendido** no depósito de quarentena e como **Comprado** no depósito normal.

## <a name="quarantine-order-scrap"></a>Sucata da ordem de quarentena
Como parte do processo da ordem de quarentena, você pode sucatear o estoque. Ao processar a sucata, o status do estoque será definido como **Vendido** por uma transação de saída no depósito de quarentena.

<a name="see-also"></a>Consulte também
--------

[Bloqueio de estoque](inventory-blocking.md)




