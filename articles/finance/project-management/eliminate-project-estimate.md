---
title: Eliminar uma estimativa de projeto
description: Este tópico fornece informações sobre como eliminar uma estimativa de projeto após sua conclusão.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410190"
---
# <a name="eliminate-a-project-estimate"></a>Eliminar uma estimativa de projeto

[!include [banner](../includes/banner.md)]

As estimativas de projeto fornecem a exibição financeira do trabalho que é previsto e programado para um projeto. Para trabalhar com estimativas de um projeto, você deve anexar o projeto a um projeto previsto. Um projeto previsto sempre se baseia em um projeto existente, mas vários projetos podem referenciar um único projeto previsto. Somente os projetos de preço fixo e de investimento podem ser anexados a projetos previstos; esses projetos devem pertencer ao mesmo grupo de projetos que o projeto previsto.

Para eliminar um projeto previsto, ele precisa estar concluído. As etapas a seguir explicam como eliminar uma previsão.

1. Vá para **Gerenciamento e contabilidade de projeto** > **Todos os projetos** e abra o projeto. 
2. Na guia **Gerenciar**, selecione **Previsões**. Na página **Previsão** selecione **Eliminar**.
3. Na página **Eliminar estimativa** na guia **Geral**, defina as seguintes opções:

   - **Código de período**: selecione o código de período para escolher os projetos de previsão adequados. 
   - **Data prevista**: selecione a data prevista adequada para eliminação.
   - **Eliminar com avisos WIP**: habilite esta opção para fornecer notificação quando uma previsão associada a um trabalho em andamento (WIP) for eliminada. Quando esta opção estiver desabilitada, a eliminação não poderá continuar se existir uma transação não prevista. 
   > [!NOTE]
   > Esse opção só ficará disponível quando a eliminação for aplicada a um projeto previsto. Ela não estará disponível se você estiver usando lançamentos periódicos. Esta configuração funciona com as configurações na guia **Previsão** na página **Parâmetros do projeto**, no grupo de campos **Permitir eliminação quando houver transações não previstas**.
   - **Definir estágio como Concluído**: habilite esta opção para definir a fase do projeto previsto como **Concluída** após executar a eliminação.
   - **Imprimir lista prevista**: selecione as informações a serem incluídas quando a lista prevista for impressa.
   - **Mostrar log de informações**: habilite esta opção para exibir o log de informações.
   - **Data de lançamento**: escolha a data de lançamento do razão da previsão.

4.  Selecione **OK**.
5. Depois que o processo de eliminação for concluído, o projeto previsto eliminado será exibido com um valor negativo. 

Se você não pretende eliminar uma previsão, poderá selecionar a previsão eliminada e selecionar **Reverter eliminação**.   
