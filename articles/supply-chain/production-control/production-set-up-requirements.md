---
title: Requisitos da configuração da produção
description: Este artigo fornece informações sobre os requisitos de instalação antes que você possa trabalhar com controle de produção.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bfde8b40927ceaa216878d58ef72c5d91e9ebe01
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968787"
---
# <a name="production-setup-requirements"></a>Requisitos da configuração da produção

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre os requisitos de instalação antes que você possa trabalhar com controle de produção. 

O controle de produção é integrado a recursos em outros módulos. Esta interconectividade permite que você altere as ordens de produção e garante que sejam atualizadas automaticamente em todos os outros processos e cálculos relacionados no sistema. Os processos de configuração a seguir são listados na ordem em que devem ser concluídos.

## <a name="required-baseline-setup-in-other-modules"></a>Configuração de linha de base necessária em outros módulos
As informações em outros módulos devem ser configuradas antes que você possa trabalhar com Controle de produção. Esta configuração inclui as seguintes tarefas:

-   Configurar as informações gerais sobre a empresa.
-   Configurar a contabilidade.
-   Definir grupos de itens.
-   Configurar contas contábeis de grupos de itens.
-   Configurar a tabela de item de estoque em Gerenciamento de estoque.
-   Crie listas de materiais (BOMs) e versões de BOM em Gerenciamento de informações sobre produtos.

## <a name="required-calendar-and-resource-setup"></a>Configuração necessária de calendário e do recurso
Antes de usar Controle de produção, abra Administração da organização e crie e defina o calendário e os recursos de operações na seguinte ordem:

1.  **Modelos de horário de trabalho** - configure modelos de horário de trabalho para definir os horários disponíveis para o planejamento da produção.
2.  **Calendários** - configure calendários de horário de trabalho para definir os dias do ano que estão disponíveis para o agendamento da produção.
3.  **Grupos de recursos** – configure grupos de recursos para agrupar os recursos de operações para obter uma visão geral das habilidades livres quando você executa o agendamento. Você não precisa configurar grupos de recursos antes de configurar recursos de operações. No entanto, é recomendável que você compreenda como agrupar recursos ao configurar o Controle de produção.
4.  **Recursos** – configure os recursos de operações para definir os recursos usados para completar o processo de produção e para planejar a capacidade.

## <a name="required-production-parameters-setup"></a>Configuração dos parâmetros de produção necessários
**Parâmetros de controle de produção** - configure parâmetros de produção básicos para definir como o sistema processa e lida com as ordens de produção. Defina como as ordens de produção são criadas, estimadas, agendadas e consumidas. Você também pode selecionar que tipo de comentário você deseja e como a contabilização de custos é concluída.

## <a name="required-journal-name-identification"></a>Identificação de nome do diário necessário
**Nomes de diários de produção** – especifique os nomes de diário de produção usados para registrar e lançar transações.

## <a name="setup-if-you-use-operations"></a>Configurar se você usa operações
As operações representam as atividades específicas que são concluídas para produzir o produto acabado. **Observação:** você deve conhecer os tipos de atividades necessárias para produzir o item e a ordem e as prioridades dessas atividades. Você também deve saber quais recursos estão envolvidos, e quantos.

1.  **Operações** - configure operações para representar as tarefas que devem ser concluídas para produzir o item concluído.
2.  **Relações** - configure relações de operação para estabelecer propriedades detalhadas. Para definir relações de operação, clique em **Relações** na página **Operações**.

## <a name="setup-if-you-use-routes"></a>Configurar se você usa roteiros
Se você estiver trabalhando com roteiros, as operações deverão ser definidas para todos os roteiros de produção configurados. O roteiro representa o caminho traçado pelo item de operação em operação, do início ao fim do processo de produção.

1.  **Categorias de custo** - configure categorias de custo para definir o custo por hora dos processos especificados e o tempo de configuração.
2.  **Grupos de custo** - configure grupos de custos para criar e manter tipos diferentes de avaliações de custo.
3.  **Grupos de roteiros** - configure grupos de roteiros para definir parâmetros relacionados a grupos de roteiros. Você deverá configurar grupos de roteiros antes de criar roteiros de produção.
4.  **Roteiros** - configure roteiros de produção e defina as configurações padrão para controlar o planejamento, os custos e a definição de preços de operações de roteiro, assim como o relatório de progresso.
5.  **Versão do roteiro** - configure versões de roteiro para habilitar variações de item em produção.

## <a name="optional-advanced-settings"></a>Configurações avançadas opcionais
1.  **Grupos de produção** - configure grupos de produção para estabelecer relações entre a ordem de produção e as contas contábeis. As contas contábeis são usadas para lançar ou para agrupar ordens para relatório.
2.  **Pools de produção** - crie pools de produção para agrupar ordens de produção para processar ordens de produção urgentes ou para excluir e lançar grupos de ordens.
3.  **Propriedades** – defina as propriedades para criar atributos especiais que podem ser atribuídos aos recursos para controlar a ordem das produções. Esses atributos estão conectados ao modelo de horário de trabalho.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
