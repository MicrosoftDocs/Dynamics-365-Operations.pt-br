---
title: Configurar razões
description: Este tópico fornece informações sobre como configurar razões para cada entidade legal. Ele inclui informações sobre como selecionar moedas, calendários fiscais, o plano de contas e as estruturas de conta que devem ser usadas com cada entidade legal.
author: kweekley
manager: ''
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Ledger
audience: Application User
ms.reviewer: roschlom
ms.search.scope: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-09
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 929ab7ae66a217de836ce49373faed76325c4d3a
ms.sourcegitcommit: ac0a676c91e3053ad7f9432d576c9af3ff98a99a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "4440568"
---
# <a name="configure-ledgers"></a>Configurar razões

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre como configurar razões para cada entidade legal. Ele inclui informações sobre como selecionar moedas, calendários fiscais, o plano de contas e as estruturas de conta que devem ser usadas com cada entidade legal.

## <a name="selecting-the-chart-of-accounts"></a>Selecionar o plano de contas

Para cada entidade legal no Microsoft Dynamics 365 Finance, é necessário configurar detalhes sobre o razão. A página **razão** permite selecionar o plano de contas e as estruturas de conta que serão usadas para a entidade legal selecionada. Você pode compartilhar seu plano de contas e as estruturas de conta, configurando a página **razão** em cada entidade legal para usar o mesmo plano de contas e estruturas de conta. Você também pode compartilhar parte da configuração em cada entidade legal e ter configurações específicas em cada entidade legal.

Se as entidades legais precisarem ter diferentes planos de contas ou estruturas de conta diferentes, o recurso substituição da entidade legal pode ser útil. Ao usar o mesmo plano de contas e estruturas de conta para várias entidades legais e, depois, gerenciar as exceções por substituições da entidade legal, você pode simplificar a manutenção ao longo do tempo.

Para configurar o plano de contas para uma entidade legal, vá para **Razão geral \> Configuração do razão \> Razão**. Na página **Razão**, selecione um **Plano de contas**, e depois selecione os planos de contas que serão usados. Observe que o plano de contas não pode ser alterado depois que você seleciona um valor e lança transações na entidade legal.

Para obter mais informações sobre como planejar e configurar o plano de contas e as contas principais, consulte [Planejar o plano de contas](plan-chart-of-accounts.md).

## <a name="selecting-account-structures"></a>Selecionar estruturas de contas

Cada entidade legal no Dynamics 365 Finance pode ser configurada para usar uma ou mais estruturas de conta. Cada estrutura de conta define as dimensões financeiras e as combinações de contas principais e dimensões financeiras, que serão permitidas quando as transações forem lançadas. Você pode usar as mesmas estruturas de conta em mais de uma entidade legal.

Observe que, se você tiver várias estruturas de conta, poderá selecionar somente estruturas de conta que não tenham combinações sobrepostas de contas principais e dimensões financeiras. Por exemplo, uma de suas estruturas de conta está configurada para adicionar uma unidade de negócios para contas principais entre 1000 e 1999. Em outra estrutura de conta, você adicionou uma dimensão financeira de departamento para contas principais que começam com 1. Nesse caso, somente uma das estruturas de conta pode ser adicionada na mesma entidade legal.

Para configurar estruturas de conta para o razão, na página **Razão**, na FastTab **Estruturas de conta**, selecione **Adicionar**, selecione uma estrutura de conta na lista e, em seguida, selecione **Selecionar**. Pode levar alguns minutos para que as estruturas de conta sejam adicionadas e salvas. Observe que as estruturas de conta selecionadas por você devem estar ativas. Caso contrário, os detalhes das estruturas de conta não entrarão em vigor nas entidades legais nas quais estão vinculados.

Para remover uma estrutura de conta, na página **Razão**, na FastTab **Estruturas de conta**, selecione **Remover**. Observe que, se você remover uma estrutura de conta do razão, não remova as transações que foram lançadas usando a configuração dessa estrutura de conta.

Para obter mais informações sobre como configurar suas estruturas de conta, consulte [Configurar estruturas de conta](configure-account-structures.md).

## <a name="configuring-calendars-for-the-ledger"></a>Configurar calendários para o razão

Outro componente do razão é o calendário fiscal. Você deve selecionar um calendário fiscal para cada entidade legal. Você pode usar o mesmo calendário fiscal em mais de uma entidade legal. Quando você seleciona um calendário fiscal para o razão, uma cópia é feita. Essa cópia é chamada de calendário do razão. O calendário do razão permite que você selecione o status dos períodos e dos módulos em cada período.

Para acessar e atualizar o calendário da entidade legal selecionada, na página **Razão**, no painel de ações, selecione **Calendário do razão**.

Para selecionar o calendário, selecione **Calendários fiscais** e, em seguida, selecione o calendário na lista. Se você alterar o calendário fiscal depois que as transações forem lançadas na entidade legal, será necessário selecionar **Recalcular períodos do razão**. Em seguida, na caixa de diálogo exibida, você pode atualizar os saldos do razão para os períodos no calendário. É recomendável executar o processo **Recalcular períodos do razão** no modo **Lote** e executá-lo quando processos não críticos estiverem ocorrendo no sistema. Dependendo do número de combinações de transações e dimensões financeiras, esse processo pode levar algum tempo.

Se nenhum calendário fiscal for selecionado para uma entidade legal, você receberá uma mensagem de erro ao tentar lançar uma transação nessa entidade legal.

Para obter mais informações, consulte [Calendários fiscais, anos fiscais e períodos](../budgeting/fiscal-calendars-fiscal-years-periods.md).

## <a name="using-a-balancing-financial-dimension"></a>Usar uma dimensão financeira de balanço

Depois de ter selecionado o plano de contas e adicionado uma ou mais estruturas de conta, você pode selecionar uma única dimensão financeira a ser usada como a dimensão financeira de balanço. A dimensão selecionada deve existir em todas as estruturas de conta. Ele também deve ser equilibrado em todas as entradas contábeis. Em outras palavras, os débitos e os créditos devem ser iguais para a conta principal e a dimensão financeira de balanço. O sistema cria transações automaticamente para balancear as entradas, com base nas contas principais especificadas nos campos **Interunidade - crédito** e **Interunidade - débito** na página **Contas para transações automáticas**.

Para obter mais informações sobre balanceamento de entradas, consulte [Diários balanceados para contabilidade interunidade](example-balanced-journals-interunit-accounting.md).

## <a name="configuring-currencies-for-the-ledger"></a>Configurar moedas para o razão

A página **Razão** também é usada para controlar e definir as moedas que serão usadas quando as transações são lançadas no razão geral. Você deve especificar a moeda contábil, que é a moeda usada na coluna **Moeda contábil** no razão geral de todos os comprovantes. Além disso, na coluna **Moeda de relatório**, você pode selecionar uma segunda moeda. Se você selecionar uma moeda de relatório, todas as transações serão registradas na coluna **Moeda de relatório** do razão geral em todos os comprovantes.

Se as transações forem lançadas em uma moeda diferente, o sistema converterá automaticamente o valor da transação da moeda de transações na moeda contábil e na moeda organizacional no comprovante. Na página **Razão**, no campo **Tipo de taxa de câmbio da moeda contábil**, selecione o tipo de taxa de câmbio configurado para as taxas de câmbio que devem ser usadas para converter valores da moeda da transação na moeda contábil em um comprovante. Se você tiver selecionado uma moeda de relatório, também deve definir o campo **Tipo de taxa de câmbio da moeda organizacional** para indicar a taxa de câmbio que deve ser usada para converter valores da moeda de transação na moeda de relatório em um comprovante.

Se estiver usando a funcionalidade de orçamento, você também poderá definir o campo **Tipo de taxa de câmbio do orçamento** para indicar a taxa de câmbio que deve ser usada para converter transações de orçamento de uma moeda para outra.

Se você usar duas moedas ou se usar uma única moeda, mas as transações forem lançadas em uma moeda diferente, será necessário configurar a FastTab **Contas para reavaliação de moeda** na página **Razão**. Nessa FastTab, você define as contas de lucros e perdas realizadas e não realizadas padrão que serão usadas por padrão quando as transações são lançadas, se nenhuma conta for especificada na página **Contas para reavaliação de moeda**. (A página **Contas para reavaliação de moeda** é usada para configurar contas diferentes para ganhos e perdas realizados e não realizados para cada moeda.)

Os ganhos e perdas realizados são lucros e perdas feitas a partir de transações concluídas. Eles são registrados no demonstrativo de lucros e perdas. Os ganhos e perdas não realizados são lucros e perdas que foram materializados, mas a transação não foi concluída. Por exemplo, você lançou uma nota fiscal, mas a nota fiscal ainda não foi liquidada e paga. Os ganhos e perdas não realizados são registrados no balanço.

Para obter mais informações sobre como usar duas moedas, consulte [Moeda dupla](dual-currency.md).
