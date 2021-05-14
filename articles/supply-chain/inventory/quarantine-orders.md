---
title: Ordens de quarentena
description: Este tópico descreve como usar ordens de quarentena para bloquear o estoque.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956173"
---
# <a name="quarantine-orders"></a>Ordens de quarentena

[!include [banner](../includes/banner.md)]

Este tópico descreve como usar ordens de quarentena para bloquear o estoque.

As ordens de quarentena permitem bloquear o estoque. Por exemplo, talvez você deseje quarentena itens por motivos de controle de qualidade. Estoque que ficou em quarentena transferido para um depósito de quarentena.

> [!NOTE]
> Se você estiver usando processos avançados de gerenciamento de depósito (em Gerenciamento de depósito), o processamento da ordem de quarentena será usado somente para ordens de venda de devolução.

## <a name="quarantine-on-hand-inventory-items"></a>Itens de estoque disponíveis em quarentena

Ao colocar itens em quarentena, você pode criar as ordens de quarentena manualmente ou configurar o sistema para criá-las de forma automática durante o processamento de entrada.

Para configurar o sistema para gerar ordens de quarentena automaticamente, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Configuração \> Estoque \> Grupos de modelos de item**.
1. Selecione um grupo de modelos relevante no painel de lista ou crie um novo grupo de modelos.
1. Na FastTab **Políticas de estoque**, marque a caixa de seleção **Gerenciamento de quarentena**.
1. Feche a página.
1. No campo **Depósito de quarentena** dos depósitos de recebimento, especifique um depósito de quarentena padrão.

Quando um item registrado como recebido no depósito pertence a um grupo de modelos no qual a caixa de seleção **Gerenciamento de quarentena** está marcada, o sistema gera uma ordem de quarentena para ele. A ordem de quarentena instrui os trabalhadores a mover o item para o depósito de quarentena.

Quando você cria ordens de quarentena manualmente na página **Ordens de quarentena**, o item não precisa ser configurado para gerenciamento de quarentena no grupo de modelos de item associado. Para esse processo, você deve especificar o estoque disponível que deve estar em quarentena e o depósito de quarentena que deve ser usado. Você pode usar os status da ordem de quarentena para ajudar a planejar o processo.

## <a name="quarantine-order-statuses"></a>Status da ordem de quarentena

As ordens de quarentena podem ter os seguintes status:

- Criado em
- Iniciado
- Relatado como concluído
- Concluído

### <a name="created"></a>Criado em

Quando uma ordem de quarentena tiver sido criada manualmente, mas o item ainda não estiver colocado no depósito de quarentena, a ordem de quarentena fica com o status **Criado**. Duas transações de estoque são geradas. Uma transação é uma transação de saída que pode ter um status **Na ordem**, **Qtd. reservada** ou **Separado**. A outra transação é uma transação de de recebimento que pode ter o status **Encomendado** ou **Registrado** no depósito de quarentena. Você pode reservar, separar e registrar atualizações no estoque usando os processos normais.

### <a name="started"></a>Iniciado

Quando uma ordem de quarentena tem o status **Iniciado**, o estoque é transferido do depósito normal para o depósito de quarentena, e duas transações de estoque são geradas. Uma transação tem o status **Deduzido** e a outra transação, o status **Recebido**. Ao mesmo tempo, duas transações de estoque são criadas para tratar da transferência de retorno. Essas transações não são datadas. Uma transação tem o status **Qtd. reservada** e a outra transação, o status **Encomendado**.

### <a name="reported-as-finished"></a>Informado como concluído

Para relatar uma ordem de quarentena iniciada como concluída, abra a ordem e selecione **Relatar como concluído** no Painel de Ações. O item é liberado da quarentena, mas ainda não é retornado ao depósito normal. O retorno ao depósito normal pode ser processado por meio de um diário de entrada de itens que pode ser inicializado durante o processo Relatar como concluído.

### <a name="ended"></a>Terminado

Quando uma ordem de quarentena é finalizada, o item é movido do depósito de quarentena para o depósito normal novamente. O status da transação de item é definido como *Vendido* no depósito de quarentena e como *Comprado* no depósito normal.

## <a name="quarantine-order-scrap"></a>Sucata da ordem de quarentena

Como parte do processo da ordem de quarentena, você pode sucatear o estoque. Ao processar a sucata, o status do estoque é definido como *Vendido* por uma transação de saída no depósito de quarentena.

## <a name="additional-resources"></a>Recursos adicionais

- [Bloqueio de estoque](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
