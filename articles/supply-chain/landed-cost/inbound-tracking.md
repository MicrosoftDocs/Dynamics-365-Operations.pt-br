---
title: Rastrear viagens de entrada e percursos de contêiner de remessa
description: Este tópico explica como você pode usar a página Acompanhamento de entrada para rastrear o progresso de viagens e os percursos do contêiner de remessa.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 94754447b3f363716595de4902f48188c4ebbda9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022004"
---
# <a name="track-inbound-voyages-and-shipping-container-journeys"></a>Rastrear viagens de entrada e percursos de contêiner de remessa

[!include [banner](../../includes/banner.md)]

A página **Acompanhamento de entrada** permite rastrear o progresso de viagens e percursos do contêiner de remessa. Cada viagem e percurso é dividido por *atividades*, cada um com sua própria linha na página. Você pode usar a página para exibir e inserir datas estimadas e datas reais por atividade.

Normalmente, dependendo da configuração no [Centro de controle de acompanhamento](delivery-information-setup.md#tracking-control-center), essas atividades mostram automaticamente a data de aterrissagem estimada no destino final. Também de acordo com a configuração, a data final geralmente atualiza a data de entrega ou a data confirmada nas linhas da ordem de compra. Para linhas de ordem de transferência, você pode configurar o sistema para atualizar a data de recebimento.

Para abrir a página **Acompanhamento de entrada**, acesse **Custo de entrega \> Acompanhamento \> Acompanhamento de entrada**.

## <a name="filter-the-activities-list"></a>Filtrar a lista de atividades

Você pode usar os campos **Viagem** e **Contêiner de remessa** na parte superior da página **Acompanhamento de entrada** para filtrar a página, de forma que mostre apenas as atividades associadas ao contêiner de viagens e/ou de remessa selecionado.

## <a name="update-tracking-information"></a>Atualizar informações de acompanhamento

Para atualizar a agenda para uma viagem ou percurso, insira a data de início da primeira atividade. A data de término prevista da última atividade será atualizada. A configuração de cada modelo de trecho e percurso no [Centro de controle de acompanhamento](delivery-information-setup.md#tracking-control-center) determina os prazos de entrega estimados. As datas de término estimadas usam o prazo de entrega da data de início da atividade. Em seguida, quando a data de término real é registrada, a data de início da próxima atividade é atualizada para a mesma data que a data de término real da atividade anterior. O prazo de entrega real é atualizado de forma que a comparação e a análise possam ser feitas. Notas adicionais podem ser inseridas no campo **Observação**.

A ordem das atividades na grade é determinada pela ordem dos trechos no modelo de percurso relevante. Se a ordem dos trechos na jornada associada mudar, o controle de acompanhamento também será alterado.

Você pode atualizar as datas de todos os contêineres, selecionando **Atualizar data de início** ou **Atualizar data de término real** no Painel de Ações. Como alternativa, você pode inserir as datas por contêiner na remessa. Essa abordagem permite maior flexibilidade, pois os contêineres podem ser divididos em um ambiente de vários percursos.

## <a name="buttons-on-the-action-pane"></a>Botões no Painel de Ações

Você pode usar os botões no Painel de Ações da página **Acompanhamento de entrada** para trabalhar com viagens de entrada e percursos. A tabela a seguir descreve os botões disponíveis.

| Botão | Descrição |
|---|---|
| Edição | Editar uma viagem ou jornada de contêiner de remessa. |
| Novo | Crie uma nova viagem ou jornada de contêiner de remessa. |
| Excluir | Exclua uma viagem selecionada ou jornada de contêiner de remessa. |
| Atualizar data de início | Atualiza a data de início de uma atividade para todos os contêineres em uma viagem. Quando a data de início de uma atividade específica ou um trecho de uma jornada é atualizado, as datas de início estimadas subsequentes são atualizadas com base no prazo de entrega especificado. |
| Atualizar data de término real | Atualize a data de término de uma atividade para todos os contêineres em uma viagem. Quando a data de término de uma atividade específica é atualizada, as atividades subsequentes são atualizadas com base no prazo de entrega especificado. |
| Adicionar atividades | Adicione manualmente uma atividade a uma viagem. Por exemplo, você pode adicionar uma atividade de fumigação. A adição pode levar à alteração na data de entrega confirmada das mercadorias na embarcação ou da viagem. Quando uma atividade é adicionada ao percurso, os dias estimados não são inseridos até a data de início de um trecho do percurso ser atualizada. |

## <a name="information-and-settings-on-the-overview-tab"></a>Informações e configurações na guia Visão geral

A guia **Visão geral** mostra uma lista de todas as atividades pertencentes ao contêiner de viagem e/ou remessa selecionado na parte superior da página. A tabela a seguir descreve os campos disponíveis para cada atividade.

| Campo | Descrição |
|---|---|
| Trecho | A ID do trecho para a atividade, conforme definido pelo modelo de percurso. |
| Modo de entrega | O método de entrega esperado da atividade. |
| Atividade | Geralmente, este campo identifica o trabalho ou a tarefa associada à atividade. Exemplos típicos incluem *Navegação* e *Liquidação*. |
| Descrição | Uma descrição mais longa da atividade. |
| Data de início | Este campo inicialmente mostra a data de início estimada da atividade. No entanto, depois que a data de término real da atividade anterior for inserida, ela mostrará a data de início real. Este campo é usado para determinar a data de término prevista, com base no prazo de entrega. |
| Data de término estimada | O valor deste campo é calculado com base na data de início e na hora de entrega. Em geral, você não editará o valor diretamente. |
| Data de término real | Um usuário deverá atualizar este campo assim que possível após a atividade ocorrer. O prazo de entrega real é atualizado. |
| Dias estimados | O período estimado (em dias) necessário para concluir a atividade. |
| Dias reais | O período real (em dias) necessário para concluir a atividade. |
| Observação | Use este campo para adicionar notas e detalhes diversos sobre a atividade. |

## <a name="information-and-settings-on-the-general-tab"></a>Informações e configurações na guia Geral

A guia **Geral** mostra informações sobre o trecho selecionado na guia **Visão geral**. Embora ele repita algumas das informações exibidas na guia **Visão geral**, ele também inclui informações adicionais sobre o trecho selecionado.
