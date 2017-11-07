---
title: "Gerenciar trabalhadores de depósito"
description: "Este artigo descreve como você pode usar o Dynamics 365 for Finance and Operations para controlar e monitorar o trabalho realizado por funcionários em depósitos."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorker, InventLocation, WHSLaborStandards, WHSWorker, WHSWorkTable, WHSWorkTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 72891
ms.assetid: feaa6f15-49d2-41f5-9b87-453463c52e4e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0b91c139987473be65fddf8b05759a5ad6f6c223
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="manage-warehouse-workers"></a>Gerenciar trabalhadores de depósito

[!include[banner](../includes/banner.md)]


Este artigo descreve como você pode usar o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition para controlar e monitorar o trabalho realizado por funcionários em depósitos.

Se você estiver usando a funcionalidade no Gerenciamento de depósito, todas as operações do trabalhador do depósito serão referenciadas como *trabalho*. Trabalhos como separação, movimentação e contagem de estoque disponível são registrados por meio de dispositivos móveis. Para que um trabalhador do depósito possa executar um trabalho, ele deve estar associado a um trabalhador do departamento de recursos humanos. Cada conta de **Trabalhador** pode ter vários usuários de trabalho de depósito associados a ela. Esses usuários podem trabalhar em depósitos diferentes e podem ter diferentes níveis de acesso aos vários menus de dispositivos móveis. Considere os usuários de trabalho de depósito como vários logons do trabalhador selecionado. Cada usuário de trabalho tem um depósito padrão; e os fluxos de trabalho específicos são expostos pelos itens de menus que estão disponíveis para esse usuário de trabalho. 

Para criar um novo usuário de trabalho, na página **Trabalhadores**, na guia **Geral**, na seção **Depósitos**, clique em **Trabalhador**. Você deve especificar uma ID de usuário, um nome de usuário, um depósito padrão e um nome de menu. Esse menu é carregado quando o usuário entra no Portal de Dispositivos Móveis de Depósito e permite que você defina a quais itens de menu o usuário terá acesso. 

Como parte da configuração de cada usuário de trabalho, você também pode definir fluxos de trabalho de processo específicos. Por exemplo, você pode usar o campo **É um supervisor de contagem cíclica** para especificar se o usuário pode processar ajustes em discrepâncias de contagem cíclica durante uma operação de contagem ou se esses ajustes devem ser analisados primeiro por outra pessoa.

## <a name="defining-labor-standards"></a>Definindo padrões de mão de obra
A página **Padrões de mão de obra** permite definir os métodos de cálculo que o sistema usa para calcular o tempo estimado que um tipo específico de trabalho deve exigir. Essa definição pode ser definida em um nível genérico ou específico. Por exemplo, você pode definir o tempo necessário para processar uma separação de ordem de venda por peso para uma definição de unidade específica quando um processo de separação é utilizado. Ao mesmo tempo, você pode registrar o tempo, com base em um outro método de cálculo, para a operação de armazenamento no estoque disponível escolhido. 

Para habilitar os padrões de mão de obra que você definiu, selecione a opção **Permitir padrões de mão de obra** para cada depósito em que os padrões de mão de obra serão usados.

## <a name="monitoring-and-controlling-warehouse-work"></a>Monitorando e controlando o trabalho de depósito
A página **Todos os trabalhos** permite monitorar e manter todos os trabalhos planejados, em andamento e concluídos. Nessa página, você pode atualizar vários processos, como atribuições de usuário do trabalho de depósito e prioridade de trabalho. Você também pode fazer uma busca minuciosa nos detalhes relacionados ao cabeçalho de trabalho e às linhas do trabalho, para ter uma noção melhor dos processos de trabalho previstos ou concluídos. 

Se você habilitar a opção **Padrões de mão de obra**, verá o tempo estimado calculado para o trabalho. Em seguida, quando o trabalho for processado, o tempo real também será exibido para cada operação de trabalho. Dessa forma, você pode comparar os cálculos de tempo estimado com o tempo real. 

Além disso, você pode usar o tempo estimado nas regras para dividir automaticamente o trabalho durante a criação do trabalho. Dessa forma, você pode equilibrar a carga de trabalho com base no tempo esperado para concluir as tarefas. 

A análise do tempo utilizado para processar itens de trabalho pode ajudar a melhorar a eficiência dos trabalhadores de depósito. Os seguintes relatórios estão disponíveis para ajudar nessa análise:

-   **Mão de obra por usuário** – Este relatório mostra a produtividade do trabalhador com base no tempo real em comparação com o tempo previsto.
-   **Mão de obra por tipo de transação de trabalho** – Você pode usar este relatório para investigar ineficiências em processos específicos do depósito. Por exemplo, você observa que as separações de ordens de transferência estão demorando mais nesta semana do que nas semanas anteriores. Você então pode usar essas informações para futuras investigações.





