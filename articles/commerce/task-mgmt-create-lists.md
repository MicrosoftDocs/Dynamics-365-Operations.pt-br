---
title: Criar listas de tarefas e adicionar tarefas
description: Este tópico descreve como criar listas de tarefas e adicionar tarefas a elas no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: a0e49d1eced3bb62e78c630b137a5b86121682f3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795228"
---
# <a name="create-task-lists-and-add-tasks"></a>Criar listas de tarefas e adicionar tarefas

[!include [banner](includes/banner.md)]

Este tópico descreve como criar listas de tarefas e adicionar tarefas a elas no Microsoft Dynamics 365 Commerce.

Uma *tarefa* define uma parte específica do trabalho ou uma ação que alguém deve concluir em ou antes de uma data de vencimento especificada. No Dynamics 365 Commerce, uma tarefa pode incluir instruções e informações detalhadas sobre uma pessoa para contato. Ele também pode incluir links para operações de Back-Office, operações de ponto de venda (PDV) ou páginas do site para ajudar a melhorar a produtividade e fornecer o contexto que o proprietário da tarefa requer para concluir a tarefa com eficiência.

Uma *lista de tarefas* é um conjunto de tarefas que devem ser concluídas como parte de um processo comercial. Por exemplo, pode haver uma lista de tarefas que um novo trabalhador deve preencher durante a integração, uma lista de tarefas para caixas que trabalham com turnos à noite ou uma lista de tarefas que deve ser preenchida para preparar o armazenamento para um período de final de ano futuro. Em Commerce, todas as listas de tarefas que têm uma data de destino podem ser atribuídas a qualquer quantidade de lojas ou funcionários e podem ser configuradas como recorrentes.

Os gerentes e trabalhadores podem criar listas de tarefas no back-office do Commerce e, depois, atribuí-las a um conjunto de lojas.

## <a name="create-a-task-list"></a>Criar uma lista de tarefas

Para criar uma lista de tarefas, siga estas etapas.

1. Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Administração de gerenciamento de tarefas**.
1. Selecione **Novo**, e depois insira os valores nos campos **Nome**, **Descrição** e **Proprietário**.
1. Selecione **Salvar**.

## <a name="add-tasks-to-a-task-list"></a>Adicionar tarefas a uma lista de tarefas

Para adicionar tarefas a uma lista de tarefas, siga estas etapas.
 
1. Na Guia Rápida **Tarefas** de uma lista de tarefas existente, selecione **Novo** para adicionar uma tarefa.
1. Na caixa de diálogo **Criar uma nova tarefa**, no campo **Nome**, insira um nome para a tarefa.
1. No campo **Deslocamento da data de vencimento a partir da data de destino**, insira um valor inteiro positivo ou negativo. Por exemplo, insira **-2** se a tarefa deve ser concluída dois dias antes da data de vencimento da lista de tarefas.
1. No campo **Notas**, insira instruções detalhadas.
1. No campo **Pessoa para contato**, insira o nome de um especialista no assunto que o proprietário da tarefa pode contatar se precisar de ajuda.
1. No campo **Link de contato**, insira um link, com base na natureza da tarefa.

> [!TIP]
> Embora você possa usar o campo **Atribuído a** para atribuir tarefas a alguém enquanto está criando uma lista de tarefas, recomendamos que você evite atribuir tarefas durante a criação da lista de tarefas. Em vez disso, atribua as tarefas depois que a lista for instanciada para armazenamentos individuais.

## <a name="use-task-links-to-help-improve-worker-productivity"></a>Use links de tarefas para ajudar a melhorar a produtividade do trabalhador

Commerce permite vincular tarefas a operações específicas do PDV, como a execução de um relatório de vendas, a exibição de um vídeo de treinamento online para a orientação de novos funcionários ou a execução de uma operação de back-office. Esse recurso ajuda os proprietários da tarefa a obter as informações necessárias para concluir uma tarefa com eficiência.

Para adicionar links de tarefas ao criar uma tarefa, siga estas etapas.

1. Na Guia Rápida **Tarefas** de uma lista de tarefas existente, selecione **Editar**.
1. Na caixa de diálogo **Editar tarefas**, no campo **Link das tarefas**, selecione uma ou mais das seguintes opções:

    - Selecione o **Item do menu** para configurar uma operação de back-office, como "Kits de produtos".
    - Selecione a **Operação de PDV** para configurar uma operação de PDV, como "Relatórios de vendas".
    - Selecione a **URL** para configurar uma URL absoluta.

A ilustração a seguir mostra a seleção de links de tarefas na caixa de diálogo **Editar tarefa**.

![Selecionando links de tarefas na caixa de diálogo Editar tarefa](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a>Configurar uma operação de PDV para que possa ser vinculada a uma tarefa

Para configurar uma operação de PDV para que possa ser vinculada a uma tarefa, siga estas etapas.

1. Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> PDV \> Operações de PDV**.
1. Selecione **Editar**, localize a operação de PDV e marque a caixa de seleção **Habilitar gerenciamento de tarefas** para ela.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do gerenciamento de tarefas](task-mgmt-overview.md)

[Configurar gerenciamento de tarefas](task-mgmt-configure.md)

[Atribuir listas de tarefas a lojas ou funcionários](task-mgmt-assign-lists.md)

[Gerenciamento de tarefas em PDV](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
