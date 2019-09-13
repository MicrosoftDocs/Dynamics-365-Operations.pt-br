---
title: Agendar planos de manutenção
description: Este tópico explica os planos de manutenção do agendamento no Gerenciamento de Ativos.
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
ms.openlocfilehash: 6b6e5bde83474fe8971e482af518f7cee23a2220
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875500"
---
# <a name="schedule-maintenance-plans"></a>Agendar planos de manutenção

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

A programação de manutenção preventiva gera entradas de calendário de ativos, com base em planos configurados de manutenção de ativos. Você pode agendar as entradas de calendário com base em planos de serviço, nos tipos de ativo e em ativos selecionados.

1. Clique em **Gerenciamento de ativos** > **Periódico** > **Manutenção preventiva** > **Agendar planos de manutenção**.

2. Você pode selecionar um intervalo de tempo nos campos **Período** e **Frequência de período**.

>[!NOTE]
>Os campos **Período** e **Frequência do período** indicam em que fase adiante você deseja que as linhas de agendamento de manutenção a serem criadas, com base nos planos de manutenção que você criou (com base no tempo e contador). Na figura abaixo, as linhas de agendamento de manutenção (= propostas de ordem de serviço) são criadas para a data atual e três meses para frente.

3. Selecione "Sim" no botão de alternância **Criar automaticamente se especificado na linha** se as ordens de serviço devem ser criadas automaticamente de acordo com a linha de plano de manutenção.

>[!NOTE]
>Se este botão de alternância for definido como "Sim" *e* a caixa de seleção **Criar automaticamente** também estiver selecionada nas linhas de plano de manutenção em **Planos de manutenção**, as ordens de serviço serão criadas com base nas linhas do round de manutenção e as linhas do agendamento de manutenção com o status "Ordem de serviço criada" também são criadas. Se apenas uma opção for selecionada (botão de alternância **Criar automaticamente se especificado na linha** nessa caixa de seleção **Criar automaticamente** no formulário **Planos de manutenção**), apenas linhas de agendamento de manutenção são criadas cm o status "Criado". Nesse caso, nenhuma ordem de serviço é criada.

4. É possível gerar as entradas de calendário com base em planos de manutenção (tempo ou contador), ativos, tipos de ativos, locais funcionais e tipos funcionais de local. Clique no botão **Filtro** e faça as seleções, se necessário.

- Com relação ao agendamento de planos de manutenção sobre locais funcionais: se você atualizar a configuração de tipos de ativos, fabricantes e modelos de planos de manutenção na Guia Rápida **Todos os locais funcionais** > **Planos de manutenção** após ter agendado planos de manutenção, as entradas da agenda de manutenção existentes relacionadas a esse local funcional serão excluídas automaticamente. Para criar novas entradas de calendário, que correspondam ao plano de manutenção atualizado no local funcional, você deve executar uma nova agenda de plano de manutenção para esse local funcional. Ler mais sobre a configuração de tipos de ativos, fabricantes e modelos nos locais funcionais em [Criar locais funcionais](../functional-locations/create-functional-locations.md).

>*Exemplo:* você deseja criar um plano de manutenção para um local funcional específico, significando que todos os ativos configurados naquele local funcional a qualquer momento serão incluídos quando você agenda o plano de manutenção. Nesse caso, você cria um plano de manutenção e seleciona o local funcional específico, mas você NÃO adiciona quaisquer objetos no plano de manutenção. O resultado é quando você agenda esse plano de manutenção, linhas de agendamento de manutenção serão criadas para todos os ativos relacionados ao local funcional naquele momento.

- Se você alterar esses tipos de ativos, fabricantes e modelos nos **Tipos de ativos**, essas mudanças afetam apenas novos ativos que usam o tipo de ativo atualizado. Ler mais sobre a configuração do tipo de ativo fixo em [Tipos de ativo](../setup-for-objects/object-types.md).  

5. Clique em **OK** para iniciar a geração de entradas do plano de manutenção de ativos. As entradas geradas serão mostradas na página de lista **Todos os planos de manutenção**.

![Figura 1](media/09-preventive-maintenance.png)

- Na caixa de diálogo **Planos de manutenção do plano**, você pode configurar trabalhos em lotes na Guia Rápida **Executar em segundo plano** para gerar automaticamente entradas de calendário em intervalos regulares.  
- Quando você agendar a manutenção preventiva, linhas de agendamento de manutenção com data e hora planejada de início anterior à data e hora do sistema não será criada.  

A figura abaixo mostra uma ilustração gráfica de um cálculo de custos baseado no plano de manutenção.  

![Figura 2](media/10-preventive-maintenance.jpg)

Com relação a planos de manutenção baseados em contador: nas figuras abaixo, dois ciclos de registro de contador diferentes são exibidos. Eles são baseados em um plano de manutenção configurado para ativo "V0001", esperando o ativo (um carro) executar aprox. 2.000 km todo mês.

No primeiro exemplo, os estimados 2.000 km não alcançados todos os meses. De acordo com o plano de manutenção baseado em contador, o limite é de 2.000 km, o que significa que você executa um agendamento de plano de manutenção, uma linha de agendamento de manutenção deve ser criada cada vez que o limite de 2.000 km é atingido. No exemplo 1, há 4 linhas de registro, mas o limite de 2.000 km é atingido apenas uma vez. Isso significa que ao executar planos de manutenção agendados para esse ativo, por exemplo, para um período de 3 meses, apenas uma linha de agendamento de manutenção será criada.

Nesta figura, 2.000 ou mais são registrados cada mês. Portanto, três linhas de manutenção seriam criadas se você agendar planos de manutenção para esse ativo por um período de 3 meses. 

Os exemplos descritos aqui mostrar que todos os registros de contados feitos em um ativo mostram uma tendência descrevendo uso e desgaste no ativo. Essa tendência é usada como base de cálculo no momento do agendamento de plano de manutenção.

![Figura 3](media/11-preventive-maintenance.png)

![Figura 4](media/12-preventive-maintenance.png)
