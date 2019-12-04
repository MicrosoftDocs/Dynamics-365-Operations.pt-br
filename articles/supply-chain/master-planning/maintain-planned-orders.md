---
title: Manter ordens planejadas
description: Este tópico fornece informações sobre como gerenciar ordens planejadas. Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada.
author: roxanadiaconu
manager: AnnBe
ms.date: 11/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68bccb632255eac975dc150cf322d4c579ff2f24
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813767"
---
# <a name="maintain-planned-orders"></a>Manter ordens planejadas

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre como gerenciar ordens planejadas. Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada.

Você pode gerenciar ordens planejados no espaço de trabalho **Planejamento mestre**, na lista **Ordem planejada** ou nas listas **Ordens de produção planejadas**, **Ordens de compra planejadas** e **Transferência planejada**. 

## <a name="planned-order-status"></a>Status da ordem planejada
Você pode usar o campo **Status** para ajudar a acompanhar seu progresso. Os seguintes valores são usados:

-   Quando o planejamento mestre gerar ordens planejadas, elas terão o status **Não processado**.
-   Se você optar por não confirmar uma ordem planejada, poderá atribuir a ela o status **Concluído**.
-   Se você desejar confirmar uma ordem planejada, poderá alterar o status para **Aprovado**. As ordens planejadas com o status **Aprovada** são respeitadas pelo planejamento mestre e, portanto, não são modificadas nem excluídas durante uma execução de um planejamento mestre posterior. 

## <a name="firming-planned-orders"></a>Confirmar ordens planejadas 
Ao confirmar ordens planejadas, ordens reais são criadas. Elas também são conhecidas como *ordens em aberto* ou *liberadas*. Ao ser confirmada, uma ordem planejada é movida para a seção de ordens do módulo relevante.

Você pode selecionar duas opções de confirmação na página **Ordens planejadas**:

-   **Confirmar** – Isso confirmará uma ou várias ordens planejadas selecionadas.
-   **Confirmar tudo** – Isso confirmará todas as ordens planejadas no filtro. Ao usar **Confirmar tudo**, não é necessário selecionar a ordem planejada, todas as ordens planejadas no filtro serão confirmadas. Essa opção pode ser útil se você estiver confirmando uma grande quantidade de ordens planejadas.

> [!NOTE]
> É possível rastrear uma ordem planejada que foi confirmada no **Histórico de confirmação**, acessando **Formulário Ordens planejadas > Exibir > Histórico de confirmação**.

## <a name="parallelize-firming"></a>Paralelizar confirmação
Se você estiver planejando confirmar várias ordens ao mesmo tempo, a paralelização da execução pode melhorar o tempo de execução ou o desempenho. Essa opção está disponível ao confirmar várias ordens planejadas com **Confirmar** ou **Confirmar tudo**. Estão disponíveis os seguintes parâmetros:

-   **Paralelizar confirmação** – Se estiver definido como **Sim**, o processo de confirmação será paralelizado com o número de threads definido em **Número de threads**.
-   **Número de threads** – Controla o número de threads usado para paralelizar o processo de confirmação. O parâmetro será exibido somente quando **Paralelizar confirmação** estiver definido como **Sim**.


<a name="additional-resources"></a>Recursos adicionais
--------

[Visão geral de planos mestres](master-plans.md)



