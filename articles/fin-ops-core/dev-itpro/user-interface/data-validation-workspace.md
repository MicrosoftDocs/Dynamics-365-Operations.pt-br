---
title: Espaço de trabalho da lista de verificação de validação de dados
description: O espaço de trabalho Lista de verificação de validação de dados permite acompanhar processos de validação de dados entre empresas, áreas e pessoas.
author: bking
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DataValidationWorkspace
audience: Application User
ms.reviewer: rhaertle
ms.assetid: ''
ms.search.region: Global
ms.author: bking
ms.openlocfilehash: 1fdc2ae0363690984544c59a356540a9b737956d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569088"
---
# <a name="data-validation-checklist-workspace"></a>Espaço de trabalho da lista de verificação de validação de dados

[!include [banner](../includes/banner.md)]

Este tópico fornece uma visão geral do **espaço de trabalho Lista de verificação de validação** e da configuração associada.

O espaço de trabalho da **Lista de verificação de validação de dados** permite acompanhar processos de validação de dados entre empresas, áreas e pessoas. A lista de verificação pode ser usada durante uma nova implementação, após uma atualização ou após uma migração. Dependendo de sua exibição do espaço de trabalho da **Lista de verificação de validação de dados**, você verá todas as tarefas e status de um projeto de validação de dados, ou apenas as tarefas atribuídas a você.

Primeiro é necessário selecionar um projeto de validação de dados na parte superior do espaço de trabalho. Todos os dados mostrados no espaço de trabalho são, em seguida, filtrados pelo projeto de validação de dados selecionado.

## <a name="summary-tiles"></a>Blocos do resumo

Os blocos de **Resumo** fornecem uma visão geral do processo e indicadores que o ajudam a manter o processo de validação de dados em andamento. Você pode consultar todas as tarefas restantes, tarefas concluídas, tarefas em andamento e tarefas não iniciadas para o processo. Essas informações são para todas as empresas incluídas no projeto de validação de dados selecionado.

## <a name="tasks-and-status-section"></a>Seção de tarefas e status

Na seção **Tarefas e status**, o status do projeto de validação geral de dados é exibido de várias formas: status por entidade legal, por área e por lista de tarefas. Você pode selecionar o filtro para exibir o status de uma empresa específica. Cada guia de status fornece uma divisão pela porcentagem que foi concluída e número de tarefas restantes.

A última guia se refere à lista de tarefas detalhadas. É exibida a lista de tarefas completa. Você pode filtrar a lista de tarefas de várias maneiras. Clique em **Editar tarefa** para alterar o status de uma tarefa ou atribuir uma tarefa. Clique em **Anexos** para exibir anexos de uma tarefa.

O nome da tarefa é um hiperlink para a página que o usuário deve acessar para concluir o trabalho. Você pode definir esse hiperlink usando o campo **Nome do item de menu** ao editar ou criar uma tarefa do formulário **Configurar o projeto de validação de dados**.

Você pode anexar arquivos, notas, imagens e URLs a uma tarefa ao usar a ação **Anexos**. Por exemplo, você pode anexar um arquivo de relatório que foi impresso para a tarefa. Um ícone será exibido na coluna **Anexo** para a tarefa se um anexo estiver presente.

A opção **Concluído por** será preenchida automaticamente depois que a tarefa for concluída com o nome do trabalhador que concluiu a tarefa. Quando uma tarefa é marcada como concluída, o campo **Data de conclusão** é atualizado automaticamente para a data e hora atuais.

## <a name="configure-data-validation-project-page"></a>Configurar página do projeto de validação de dados

Antes de usar o espaço de trabalho **Lista de verificação de validação de dados**, você deve configurar o processo usando a página **Configurar o projeto de validação de dados**. (Clique em **Espaços de trabalho** \> **Lista de verificação de validação de dados** \> **Configurar o projeto de validação de dados**.)

## <a name="task-areas"></a>Áreas de tarefa

Use áreas de tarefas para agrupar tarefas de validação de dados em áreas lógicas de propriedade na sua organização. Por exemplo, contas a pagar, contas a receber, ou contabilidade podem ser usadas como áreas de tarefa.

O **Nome do item de menu** é associado ao compromisso de trabalho da tarefa e pode ser usado para ir diretamente à página associada no link da tarefa no espaço de trabalho. Por exemplo, uma tarefa de validação de dados para executar o relatório **Classificação por vencimento de contas a pagar** para contas a pagar pode ser vinculada à página **Relatório de classificação por vencimento de contas a pagar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]