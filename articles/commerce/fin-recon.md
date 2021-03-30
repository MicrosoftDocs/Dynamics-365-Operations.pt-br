---
title: Reconciliação financeira em lojas de varejo
description: Este tópico descreve a reconciliação financeira em lojas de varejo para PDV para o Microsoft Dynamics 365 Commerce.
author: anpurush
manager: AnnBe
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 99c238ecfbb6cb29f4fefefdca32525b99a01dc8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251322"
---
# <a name="financial-reconciliation-in-retail-stores"></a>Reconciliação financeira em lojas de varejo

[!include [banner](includes/banner.md)]

Na versão 10.0.10 e anterior do Microsoft Dynamics 365 Commerce, a funcionalidade que o cliente de PDV (ponto de venda) oferece para os processos de fechamento do dia nas lojas de varejo permite que os gerentes e funcionários de loja realizem operações de fechamento do dia. Por exemplo, eles podem fazer declarações de meios de pagamento e o fechamento cego de turnos, além de reconciliar transações de turno e fechar turnos. No entanto, não existe um recurso no PDV para finalizar as informações financeiras de turnos de forma que elas possam ser usadas para lançar dados financeiros no Commerce Headquarters. Normalmente, os gerentes de loja são responsáveis por realizar essa tarefa. Para poder aprovar um turno, eles devem examinar as informações, fazer as correções necessárias e finalizar os totais do turno. Os totais finalizados devem ser lançados nos módulos financeiros do Commerce Headquarters.

Além disso, no Commerce versão 10.0.10 e anteriores, os gerentes de loja podem examinar e fazer alguns ajustes nas linhas do demonstrativo no Commerce Headquarters. No entanto, a capacidade é limitada e os gerentes raramente têm acesso ao cliente do Commerce Headquarters. Além disso, a revisão e o ajuste do demonstrativo financeiro de varejo só podem ser feitos quando os demonstrativos são criadas no Commerce Headquarters. Porém, esse processo normalmente é noturno. Por isso os gerentes de loja devem aguardar a aprovação do turno quando os demonstrativos financeiros de varejo no Commerce Headquarters.

No Commerce versão 10.0.11 e posterior, os gerentes de loja podem examinar, ajustar e finalizar turnos no próprio cliente de PDV. Esses dados são usados para criar e lançar demonstrativos financeiros de varejo no Commerce Headquarters.

> [!NOTE]
> A funcionalidade relacionada à reconciliação financeira nas lojas de varejo se aplica somente se a criação de ordem baseada em um fluxo constante está ativada. Para obter mais informações, consulte [Criação de ordens baseadas em um fluxo constante para transações de loja de varejo](trickle-feed.md).

## <a name="set-up-financial-reconciliation"></a>Configurar a reconciliação financeira

Siga estas etapas para usar a funcionalidade de reconciliação financeira.

1. No espaço de trabalho **Gerenciamento de recursos**, ative o recurso **Demonstrativos de varejo - Fluxo constante**.
1. No perfil da funcionalidade de PDV para a loja apropriada, defina a opção **Habilitar reconciliação financeira na loja** como **Sim**.

## <a name="more-information-about-financial-reconciliation"></a>Mais informações sobre reconciliação financeira

Quando a funcionalidade de reconciliação financeira está ativada, alguns dos parâmetros definidos na FastTab **Demonstrativo/fechamento** da página **Lojas de varejo** no Commerce Headquarters são sincronizados com o banco de dados do canal. O mesmo conjunto de critérios de cálculo e limites de valor usado para os demonstrativos de varejo é imposto.

Quando a operação **Fechar turno** é chamada, o sistema valida se os valores calculados pelo sistema e os valores declarados coincidem. Se forem diferentes, e se a diferença exceder os limites definidos, o usuário será solicitado e poderá fazer os ajustes necessários.

É possível fazer ajustes para cada meio de pagamento. Quando um meio de pagamento é selecionado, o usuário pode ver os totais para diferentes tipos de transação e editar os totais de um tipo de transação específico. Durante a edição, o sistema mostra o valor calculado original e o valor substituído para esse tipo de transação. O usuário também pode capturar anotações como parte do processo de edição. As anotações podem ser usadas para fins de auditoria.

Os usuários podem ignorar os prompts e mensagens de validação e continuar para fechar o turno. No entanto, se um usuário ignorar os prompts de validação, os mesmos problemas ocorrerão e precisarão ser corrigidos quando o turno lançar demonstrativos financeiros no Commerce Headquarters.

A operação **Fechar turno** no PDV também valida se todas as transações no banco de dados offline foram sincronizadas com o banco de dados do canal. Se alguma transação não for sincronizada, o usuário receberá uma mensagem de aviso porque essa situação pode fazer com que os valores do sistema sejam calculados incorretamente. Nessa situação, o usuário pode finalizar a operação **Fechar turno** e tentar sincronizar as transações offline com o banco de dados do canal. Como alternativa, o usuário pode ajustar manualmente os valores calculados pelo sistema para considerar as transações que não foram sincronizadas de forma que o conjunto correto de números financeiros seja finalizado e lançado. 

Quando é usado o lançamento de demonstrativo com base em um fluxo constante, para que o lançamento das transações seja separado do lançamento de finanças, você pode optar por ajustar os valores calculados pelo sistema das transações offline ausentes. Dessa forma, você garante que as informações financeiras sejam sempre consideradas e publicadas corretamente, independentemente das transações que estão faltando. As transações offline podem ser sincronizadas com o banco de dados do canal e o Commerce Headquarters e lançadas posteriormente, à parte dos lançamentos financeiros.

Os detalhes da reconciliação financeira de um turno são sincronizados com o Commerce Headquarters usando o trabalho P.

As demonstrativos financeiros de varejo no Commerce Headquarters não calculam os totais para mostrar os detalhes nas linhas dos demonstrativos. Em vez disso, os valores finalizados no cliente de PDV são usados para criar e lançar demonstrativos financeiros de varejo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]