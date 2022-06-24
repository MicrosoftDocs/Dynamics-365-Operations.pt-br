---
title: Visão geral do fluxo de trabalho de subscrições
description: Este artigo oferece uma visão geral do fluxo de trabalho de subscrições.
author: sorenva
ms.date: 05/07/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c112e1816d7ede80e0e30fe318d159e22ab540b7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897419"
---
# <a name="subscription-workflow-overview"></a>Visão geral do fluxo de trabalho de subscrições 

[!include [banner](../includes/banner.md)]


Você é o administrador de subscrições de uma empresa de iluminação que oferece subscrições para a manutenção de equipamentos de luz. Um cliente entra em contato com a sua empresa para adquirir uma subscrição anual para a manutenção de equipamentos de luz.

## <a name="setting-up-subscriptions"></a>Configurando subscrições

Para configurar uma subscrição, você deve primeiro criar um grupo de subscrições para o novo contrato de serviço ou verificar se já existe um grupo de subscrições. Se já existir um grupo, você deverá configurá-lo para faturar o cliente anualmente e acumular a receita de vendas todos os meses do ano. Para obter mais informações sobre como configurar as subscrições, consulte [Configurar grupos de subscrições](set-up-subscription-groups.md).

Uma vez criado o grupo de subscrições, você poderá criar a subscrição. Para obter mais informações sobre como criar subscrições de serviço, consulte [Criar subscrições de serviço de um grupo de subscrições](create-service-subscriptions-from-subscription-group.md).

## <a name="create-and-modify-subscription-transactions"></a>Criar e modificar transações de subscrição

Depois de configurar a subscrição, crie a transação de taxa de subscrição para o primeiro período de faturamento, que é um ano. As transações são do tipo **Normal**. Portanto, você só pode criar transações de subscrição onde as datas inicial e final correspondam aos períodos criados anteriormente no formulário **Tipos de período**. Para obter mais informações sobre transações de taxa, consulte [Criar transações de taxa de subscrição](create-subscription-fee-transactions.md).

Depois de configurar a subscrição para o cliente, você se lembra de que eles negociaram um desconto de 10% sobre todas os preços de lista das ofertas de serviço. Portanto, é preciso reduzir o preço da taxa da transação criada.

Mais tarde, o contato do seu contato cliente lhe telefona para dizer que, embora desejem manter o contrato de serviço para o equipamento de luz, eles planejam introduzir um novo equipamento de luz ainda este ano. Portanto, eles precisam da cobertura de manutenção somente até outubro de 2013. Para reduzir o número de meses da subscrição do cliente, você cria uma nova transação de taxa de subscrição do tipo **Dias de redução**. Para obter mais informações sobre como reduzir dias, consulte [Reduzir os dias para taxas de subscrição](reduce-the-days-on-subscription-fees.md).

## <a name="invoice-and-accrue-subscription-transactions"></a>Faturar e acumular transações de subscrição

Agora você concluiu a configuração da subscrição e está pronto para faturar o cliente pela subscrição. Para obter mais informações sobre como faturar as subscrições, consulte [Faturar transações de subscrições](invoice-subscription-transactions.md).

Dois dias depois, o cliente liga para dizer que a subscrição deve ser faturada em dólares norte-americanos, não em euros. Portanto, você cria uma nota de crédito e também uma nova transação de subscrição na moeda correta. Para obter mais informações sobre como creditar transações de subscrição de crédito, consulte [Creditar transações de subscrição](credit-subscription-transactions.md).

No final de cada mês, a receita mensal pode ser acumulada pela subscrição do cliente na conta de lucros e perdas e nas contas WIP. Para obter mais informações sobre como acumular receita para subscrições, consulte [Acumular receita de subscrição](accrue-subscription-revenue.md).

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]