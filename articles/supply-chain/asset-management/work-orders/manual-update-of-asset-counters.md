---
title: Atualização manual de contadores de ativo
description: Este artigo descreve atualização manual de contadores de ativo no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 30c672286c16a4353556a507019960edb93f8b1b
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016584"
---
# <a name="manual-update-of-asset-counters"></a>Atualização manual de contadores de ativo

[!include [banner](../../includes/banner.md)]



Os contadores são usados para criar registros em um ativo, como registros sobre o número de horas que o ativo esteve em operação ou a quantidade que foi produzida.

O tipo selecionado para um contador deve ser definido para herdar valores do contador. Ou seja, a opção **Herdar valores do contador de ativos** é definida como **Sim** na Guia Rápida **Geral** da página **Contadores** (**Gerenciamento de ativos** > **Configurar** > **Tipos de ativo** > **Contadores**). Nesse caso, ao criar uma nova linha de contador desse tipo, cada ativo filho que usar o mesmo tipo de contador será atualizado automaticamente.

Na página **Todos os ativos**, você pode criar os registros de contador de horas ou quantidade em um ativo com base nas leituras do ativo.

1. Selecione **Gerenciamento de ativos** > **Ativos** > **Todos os ativos**.

2. Selecione o ativo e, depois, no Painel de Ação, na guia **Ativo** , no grupo **Preventivo** , selecione **Contadores**. A página **Contadores de ativos** exibe uma lista de todos os registros do contador anteriores que foram feitos no ativo selecionado.

3. Selecione **Novo** para criar um registro. A ID de ativo é inserida automaticamente no campo **Ativo**.

4. No campo **Contador**, selecione o contador relevante. Somente os contadores relacionados ao tipo de ativo selecionado no ativo estão disponíveis para seleção. A unidade relacionada é inserida automaticamente no campo **Unidade**.

5. No campo **Registrado**, selecione a data e a hora para o registro do contador.

6. No campo **Valor**, insira o número desde o último registro do contador. Alternativamente, no campo **Valor agregado**, insira o número de contagem total.

Observe os seguintes pontos:

- Se instalar fisicamente um novo contador em um ativo, você deverá registrar a alteração no ativo na página **Contadores de ativos**. Em seguida, você deve criar duas linhas de registro com carimbos de data/hora idênticos. A primeira linha deve ser para o contador que está sendo substituído. Na linha relacionada ao novo contador, marque a caixa de seleção **Redefinir contador**. No campo **Totais**, o número de contagem total é a soma dos totais do contador de todos os valores registrados nesse tipo de contador.

- Se a caixa de seleção **Redefinir contador** for marcada em um ativo que usa um plano de manutenção com um tipo de intervalo "Uma vez de..." ou "Uma vez atingido...", o contador ainda ficará ativo na nova linha do contador, pois você cria uma linha de contador separada e inicia com um novo contador.

A ilustração a seguir mostra um exemplo da página **Contadores de ativos**.

![Figura 1.](media/11-work-orders.png)

Na página **Contadores de ativos** (**Gerenciamento de ativos** > **Consultas** > **Ativos** > **Contadores de ativos**), você pode criar registros de contador em vários ativos ao mesmo tempo, conforme o necessário.

>[!NOTE]
>Você pode configurar um intervalo para definir os desvios em registros de contador manuais. Também é possível especificar o tipo de mensagem exibida se os registros estiverem fora do intervalo definido. Para obter mais informações sobre como configurar contadores, consulte [Contadores](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]