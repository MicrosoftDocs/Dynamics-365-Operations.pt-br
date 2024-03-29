---
title: Atribuir listas de tarefas a lojas ou funcionários
description: Este artigo descreve como atribuir listas de tarefas a lojas ou a funcionários no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.search.industry: ''
ms.openlocfilehash: faff772051738f624b86fd23fb6bf29173e909ea
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746185"
---
# <a name="assign-task-lists-to-stores-or-employees"></a>Atribuir listas de tarefas a lojas ou funcionários

[!include [banner](includes/banner.md)]

Este artigo descreve como atribuir listas de tarefas a lojas ou a funcionários no Microsoft Dynamics 365 Commerce.

O gerenciamento de tarefas no Dynamics 365 Commerce permite atribuir uma lista de tarefas a vários armazenamentos ou funcionários, ou a uma combinação de lojas e funcionários. Por exemplo, um gerente regional de 20 lojas pode desejar atribuir a lista de tarefas **Preparação para o período de festas** a todas as 20 lojas.

## <a name="start-the-task-list-assignment-process"></a>Iniciar o processo de atribuição da lista de tarefas

Antes de iniciar o processo de atribuição de tarefas, certifique-se de ter criado uma lista de tarefas seguindo as etapas do artigo [Criar listas de tarefas e adicionar tarefas](task-mgmt-create-lists.md). Para iniciar o processo de atribuição de uma lista de tarefas, siga estas etapas.

1. Acesse **Retail e Commerce \> Gerenciamento de tarefas \> Administração de gerenciamento de tarefas**.
1. Selecione a lista de tarefas a ser atribuída.
1. Selecione **Iniciar processo**.
1. Na caixa de diálogo **Iniciar processo**, na guia **Geral**, no campo **Nome do processo**, digite um nome (por exemplo, **Lojas da região leste**).
1. No campo **Data de destino**, especifique uma data.
1. Para atribuir a lista de tarefas às lojas, na guia **Lojas**, use o filtro **Hierarquia da organização** para localizar e selecionar os armazenamentos.

    Para atribuir a lista de tarefas aos funcionários, na guia **trabalhadores**, localize e selecione os funcionários.

1. Selecione **OK** para iniciar o processo. A lista de tarefas é atribuída às lojas ou aos funcionários selecionados.

A ilustração a seguir mostra um exemplo de como localizar e selecionar armazenamentos na caixa de diálogo **Iniciar processo**.

![Localizando e selecionando armazenamentos na caixa de diálogo Iniciar processo.](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a>Atribuir listas de tarefas em uma base recorrente

Às vezes varejistas têm tarefas recorrentes, como "lista de verificação de feriados da quinta-feira" ou "primeiro dia do mês". Portanto, eles podem desejar atribuir a lista de tarefas em uma base recorrente.

1. Acesse **Retail e Commerce \> Gerenciamento de tarefas \> Administração de gerenciamento de tarefas**.
1. Selecione a lista de tarefas a ser atribuída.
1. Selecione **Iniciar processo**.
1. Na caixa de diálogo **Iniciar processo**, na guia **Geral**, no campo **Nome do processo**, digite um nome.
1. Defina a opção **Recorrência** como **Sim**.
1. No campo **Deslocamento de data de destino recorrente em dias**, insira um número de dias. Por exemplo, se você inserir **4**, a data de destino será a data de recorrência mais quatro dias.
1. Na guia **Executar em segundo plano**, selecione **Recorrência**.
1. Na caixa de diálogo **Definir recorrência**, insira os critérios de frequência e selecione **OK**.

A ilustração a seguir mostra um exemplo de como inserir critérios de frequência na caixa de diálogo **Definir recorrência**.

![Inserindo critérios de frequência na caixa de diálogo Definir recorrência.](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a>Rastrear status da lista de tarefas

Se você for gerente regional ou gerente de armazenamento, talvez queira rastrear o status das listas de tarefas que foram atribuídas a vários armazenamentos ou funcionários. Em seguida, você poderá acompanhar os armazenamentos ou trabalhadores que não concluíram as tarefas atribuídas no tempo. O back-office do Commerce permite que você exiba o status das listas de tarefas, reatribua tarefas ou altere o status de uma tarefa.

Para rastrear o status da lista de tarefas de todas as tarefas, siga estas etapas.

1. Acesse **Retail e Commerce \> Gerenciamento de tarefas \> Processos de gerenciamento de tarefas**.
1. Selecione a guia **Todas as listas de tarefas** para exibir o status de todas as listas de tarefas atribuídas a vários armazenamentos.

Para rastrear o status da lista de tarefas de todas as tarefas atribuídas a você, siga estas etapas.

1. Acesse **Retail e Commerce \> Gerenciamento de tarefas \> Processos de gerenciamento de tarefas**.
1. Selecione a guia **Minhas tarefas** ou **Todas as tarefas** para exibir ou atualizar o status das tarefas atribuídas a você.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do gerenciamento de tarefas](task-mgmt-overview.md)

[Configurar gerenciamento de tarefas](task-mgmt-configure.md)

[Criar listas de tarefas e adicionar tarefas](task-mgmt-create-lists.md)

[Gerenciamento de tarefas em PDV](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
