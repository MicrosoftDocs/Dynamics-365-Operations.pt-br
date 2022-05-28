---
title: Atualizar rastreamento a ser armazenado
description: Este tópico descreve como configurar e executar o acompanhamento de atualizações para a tarefa periódica de armazenamento.
author: Weijiesa
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: f02ba71b4eb32551cebc6cf160f0285eac8ae7ad
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673960"
---
# <a name="update-tracking-for-put-away"></a>Atualizar rastreamento a ser armazenado

[!include [banner](../includes/banner.md)]

A tarefa periódica *Acompanhamento de atualizações para armazenamento* foi criada para ser executada como um lote recorrente noturno. Ela identifica quais viagens receberam todas as transações de estoque e quais viagens não têm um valor para a data de término real. Em seguida, ela define a data final real como a data atual, conforme necessário.

As *Atividades de contêiner* são criadas para cada *trecho* de uma jornada para cada *contêiner de remessa*. Esses valores são definidos pelo modelo de jornada selecionado quando uma viagem é criada. Para cada registro de atividades de contêiner, os valores podem ser definidos para os campos **Data de início**, **Data de término previsto** e **Data final real**. Esses campos podem ser atualizados quando a confirmação é recebida de que um trecho começou ou foi preenchido.

Normalmente, as informações relacionadas a datas confirmadas são fornecidas por terceiros, como um controlador de frete, porque essas ações são mantidas fora do Microsoft Dynamics 365 Supply Chain Management. No entanto, as informações de terceiros não são necessárias para rastrear a chegada de bens de um trecho de jornada no depósito (conforme marcado pelo armazenamento de bens). Portanto, o controle pode ser determinado com base nas informações contidas no Dynamics 365 Supply Chain Management.

Para configurar e executar a tarefa periódica *Acompanhamento de atualizações para armazenamento*, siga estas etapas:

1. Acesse **Custo Landed \> Tarefas periódicas \> Acompanhamento de atualizações para armazenamento**.
1. Na caixa de diálogo **Acompanhamento de atualizações para armazenamento**, na seção **Parâmetros**, defina os seguintes campos:

    - **Trecho** – Selecione o nome/número de identificação exclusivo para a parte de uma jornada para a qual você deseja atualizar o rastreamento. O valor selecionado deve representar a chegada da viagem no depósito.
    - **Atividade** – Selecione a atividade que foi realizada durante o trecho selecionado. Esses valores são atribuídos por linha de modelo de jornada no centro de controle de rastreamento.

1. Para limitar o conjunto de registros que deve ser incluído na atualização, selecione o botão **Filtrar** na Guia Rápida **Registros a serem incluídos**. Uma caixa de diálogo de consulta padrão é exibida, na qual você pode definir critérios de seleção, critérios de classificação e junções. Os campos funcionam da mesma forma que em outros tipos de consultas no Supply Chain Management. Os campos aqui são somente leitura e mostram os valores relacionados à sua consulta.
1. Na guia rápida **Executar em segundo plano**, configure as opções de lote e de agendamento conforme necessário, da mesma forma que em outros tipos de trabalho no Supply Chain Management.
1. Selecione **OK** para aplicar suas configurações e para executar ou agendar a atualização.
