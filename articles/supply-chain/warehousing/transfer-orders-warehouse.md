---
title: Configurar depósitos para ordens de transferência
description: Este tópico descreve como você pode configurar depósitos para ordens de transferência.
author: Mirzaab
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 9e4ea0f9720bd4e5d2724b507aa32525ac25fa52
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823206"
---
# <a name="set-up-warehouses-for-transfer-orders"></a>Configurar depósitos para ordens de transferência 

[!include [banner](../includes/banner.md)]

Você pode usar níveis de depósito para criar uma hierarquia que ofereça suporte a ordens de transferência entre depósitos. Com base nesta configuração, o planejamento mestre calculará as requisições de itens em cada nível de depósito e gerará ordens de transferência planejadas a partir de um depósito de origem atribuído para abastecê-lo.

1.  Clique em **Gerenciamento do estoque > Configuração > Divisão do estoque > Depósitos**.

2.  Selecione o depósito que desejar reabastecer.

3.  Na FastTab **Planejamento mestre**, marque a caixa de seleção **Reabastecimento**.

4.  No campo **Depósito principal**, selecione o depósito que deseja atribuir como o depósito de reabastecimento. O agendamento do planejamento mestre calculará uma solicitação de transferência para o depósito selecionado e gerará uma ordem de transferência planejada a partir do **Depósito principal** atribuído.
   
    > [!NOTE]
    > <P>Se você desmarcar a caixa de seleção <STRONG>Reabastecimento</STRONG>, o depósito selecionado será atribuído a um nível de depósito em relação ao <STRONG>Depósito principal</STRONG>, mas o <STRONG>Depósito principal</STRONG> não está configurado como um depósito de reabastecimento.</P>

5.  Feche a página para aplicar a nova configuração.


> [!TIP]
> <P>Se desejar atribuir um depósito para reabastecimento, você precisará primeiro configurar o depósito como uma dimensão de armazenamento na página <STRONG>Grupos de dimensão de armazenamento</STRONG> Nesta página, selecione o campo <STRONG>Ativar</STRONG> e o campo <STRONG>Plano de cobertura por dimensão</STRONG> para o depósito.</P>

## <a name="set-up-transport-lead-time"></a>Configurar o prazo de entrega de transporte

Você também deve configurar o prazo de entrega de transporte entre os depósitos na página **Dias de transporte** . 
1. Vá para **Gerenciamento de estoque > Configuração > Distribuição > Dias de transporte**.
2. No campo **Ponto de recebimento**, selecione **depósito**.
3. Selecione **Depósito da remessa**, **Depósito de recebimento** e **Dias de transporte**. 
4. (Opcional) você também pode definir o tempo de transporte, dependendo do modo de entrega, na guia **Dias de transporte por modo de entrega** .


[!INCLUDE[footer-include](../../includes/footer-banner.md)]