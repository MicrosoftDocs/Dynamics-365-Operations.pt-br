---
title: Atualização manual de contadores de ativo
description: Este tópico descreve atualização manual de contadores de ativo no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875506"
---
# <a name="manual-update-of-asset-counters"></a>Atualização manual de contadores de ativo

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Contadores são usados para criar registros em um ativo relacionado, por exemplo, o número de horas na operação, ou número de quantidades geradas.

Se o tipo de contador selecionado para um contador for definido para herdar valores do contador (**Gerenciamento de ativos** > **Configuração** > **Tipos de ativos** > **Contadores** > **Geral** Guia Rápida > **Herdar valores do contador de ativos** botão de alternância definido como "Sim"), então, quando você criar uma nova linha do contador desse tipo, cada ativo filho que usa o mesmo tipo de contador é atualizado automaticamente.

Em **Todos os ativos**, você cria horas ou registros do contador da quantidade em um ativo com base nas leituras do ativo.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos**.

2. Selecione o ativo da lista e clique em **Contadores**. No formulário **Contadores de ativo**, você verá uma lista de todos os registros do contador anteriores no ativo selecionado.

3. Clique em **Novo** para criar um novo registro. O ID do ativo é inserido automaticamente.

4. No campo **Contador**, selecione o contador relevante. Somente estão disponíveis contadores relacionados ao tipo de ativo selecionado no ativo. A unidade relacionada é inserida automaticamente no campo **Unidade**.

5. Selecione a data e a hora do registro do contador.

6. No campo **Valor**, insira o número desde o último registro do contador ou no campo **Valor agregado**, insira o número total de contagem.

- Se você instalar fisicamente um novo contador em um ativo, você precisará registrar a alteração no ativo em **Contadores de ativo**. Em seguida, crie duas linhas de registro com carimbos de data/hora idênticos, e na linha referente ao novo contador, marque a caixa de seleção **Redefinição do contador**. Ao criar as duas linhas de registro, a primeira linha deve ser para o contador que você está substituindo. No campo **Totais**, o número de contagem total é a soma total do contador de todos os valores registrados nesse tipo de contador.  
- Se a caixa de seleção **Redefinir contador** for selecionada em um ativo que usa um plano de manutenção com um tipo de intervalo "Uma vez..." ou "Uma vez atingido...", o contador ainda ficará ativo na nova linha do contador porque você cria uma linha do contador separada e inicia um novo contador.

![Figura 1](media/11-work-orders.png)


Se precisar efetuar registros do contador em vários ativos, isso poderá ser feito em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Contadores de ativos**.

>[!NOTE]
>Você pode configurar um intervalo para definir desvios em registros de contadores manuais, e o tipo de mensagem a ser exibido se os registros estiverem fora do intervalo definido. Consulte o tópico [Contadores](../setup-for-objects/counters.md) referente à configuração dos contadores.
