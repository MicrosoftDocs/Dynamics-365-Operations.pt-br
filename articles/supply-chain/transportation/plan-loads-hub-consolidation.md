---
title: ​Visão geral de planejamento de cargas usando consolidação de hub​
description: Este artigo descreve o recurso para consolidar remessas em um hub quando entregar mercadorias em depósitos diferentes para o mesmo cliente ou quando mercadorias são recebidas de vários fornecedores no mesmo depósito.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, TMSParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbf84d551d7122516c8b5dd0be0246539e1e7e3f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004993"
---
# <a name="plan-loads-using-hub-consolidation-overview"></a>​Visão geral de planejamento de cargas usando consolidação de hub​

[!include [banner](../includes/banner.md)]

Este artigo descreve o recurso para consolidar remessas em um hub quando entregar mercadorias em depósitos diferentes para o mesmo cliente ou quando mercadorias são recebidas de vários fornecedores no mesmo depósito.

Pode ser útil consolidar as remessas em um hub quando entregar mercadorias em depósitos diferentes para o mesmo cliente ou quando mercadorias são entregues de vários fornecedores para o mesmo depósito.

## <a name="building-loads"></a>Criando cargas
Antes de usar a consolidação de hub, você deve habilitar a opção **Planejamento em trânsito** na página **Parâmetros de gerenciamento de transporte**. Você também deve criar os hubs onde ocorrerá a consolidação. O diagrama a seguir mostra um exemplo de consolidação de hub. Nesse caso, ordens de venda de depósitos diferentes irão para o mesmo cliente. Cargas básicas são criadas com base em ordens de venda de maneira normal, usando a página **Bancada de planejamento de carga**. Para consolidar as duas cargas em um hub antes que sejam enviadas para o cliente, na página **Bancada de planejamento de carga**, no campo **Transporte**, selecione **Consolidação de hub**. Quando você seleciona o hub correto para cada carregamento, os carregamentos terão o hub com o destino "entregar". Você também terá duas "linhas de solicitação de transporte" na seção **Fornecimento e demanda** na página **Bancada do planejamento de carga**. Você pode então adicionar estas duas linhas para uma nova carga. Essa nova carga terá ambas as linhas de ordem de venda e também terá o hub como o endereço de "pegar" e o cliente como o destino "entregar". As três cargas estão prontas para serem classificadas e roteadas como qualquer outra carga. Você pode selecionar qual transportadora o sistema sugere para cada carga. [![Consolidação de hub](./media/hubconsol.jpg)](./media/hubconsol.jpg) Você também pode usar o mesmo método para consolidar cargas de várias ordens de transferência. Nesse caso, o cliente A no diagrama anterior é um depósito. Como alternativa, você pode consolidar cargas de várias ordens de compra, onde as cargas são entregues de fornecedores diferentes para o mesmo depósito. Você pode ter mais de um hub de consolidação e pode consolidar vários hubs para cargas mais provenientes de depósitos diferentes. Depois de criar as cargas básicas e usar a opção de consolidação do hub, você cria os novos carregamentos usando as linhas de solicitação de transporte consolidado. Em seguida, taxar e rotear as cargas.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]