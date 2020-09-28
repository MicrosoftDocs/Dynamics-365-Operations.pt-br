---
title: Configurar funções nos modelos de estrutura de detalhamento de trabalho
description: Este tópico fornece informações sobre como configurar informações da função em modelos de estrutura de detalhamento de trabalho.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5dfb429eae933ba4d687ec4cbd417d2f78308e47
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760476"
---
# <a name="set-up-roles-on-work-breakdown-structure-templates"></a>Configurar funções nos modelos de estrutura de detalhamento de trabalho

[!include [banner](../includes/banner.md)]

Os gerentes de projeto podem configurar modelos de estrutura de detalhamento de trabalho (WBS) que podem ser aplicados durante a criação de uma WBS para novos projetos. Os gerentes de projeto podem adicionar funções ao criar um modelo. Use o procedimento a seguir para atribuir uma função a um modelo de WBS. 

1. Selecione **Gerenciamento e contabilidade de projeto** > **Configuração** > **Projetos** > **Modelos de estrutura de detalhamento de trabalho**.
2. Selecione **Detalhes** para um modelo de WBS selecionado.
3. Selecione uma tarefa na lista e, no campo **Função**, selecione uma função para atribuir à tarefa.

## <a name="work-with-a-wbs"></a>Trabalhar com um WBS

Você pode criar um novo WBS ou pode copiar uma WBS de um modelo existente de WBS. Um gerente de projeto pode gerenciar os recursos ao atribuir funções às novas tarefas na WBS. As funções poderão ser substituídas depois que um recurso for adquirido ou depois que um recurso confirmado para trabalhar na tarefa for identificado. Essa flexibilidade permite que os gerentes de projeto executem as seguintes tarefas:

- Identificar o número de recursos necessários para os pacotes de trabalho WBS.
- Estimar custos de projeto.
- Determinar um orçamento preliminar.
- Estimar a duração da atividade com base em funções e em recursos.
- Desenvolver alguns planos de gerenciamento de projetos com base nas informações disponíveis sobre o projeto.

Outras opções foram adicionadas à WBS para melhorar o uso da funcionalidade de recursos.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opção</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Atribuições de recursos</td>
<td>Exiba os recursos atribuídos, as datas, o número de horas e o tipo de reserva para tarefas na WBS.</td>
</tr>
<tr class="even">
<td>Gerar equipe automaticamente</td>
<td>Adicione automaticamente recursos planejados usando as funções associadas a uma tarefa. O Finance sugere automaticamente recursos planejados usando vários critérios de análise de decisão baseada em funções. Depois que as funções e o esforço (horas) forem definidos para as tarefas em uma WBS e depois de a estrutura ter sido liberada, selecione <strong>Gerar equipe automaticamente</strong>. O número necessário de recursos planejados é adicionado à WBS e à guia <strong>Agendamento de projeto e equipe</strong>.</td>
</tr>
<tr class="odd">
<td>Recurso (lista suspensa)</td>
<td>Na página <strong>Iniciar atribuição de recursos</strong>, você pode selecionar recursos para reserva fixa ou reserva flexível com base na duração especificada. Você pode ajustar as configurações de exibição para ver e definir a duração de atividades de recurso. Você pode selecionar e atribuir recursos no nível do pacote de trabalho usando as seguintes opções:
<ul>
<li><strong>Aceitar</strong> – confirme as alterações feitas no recurso atribuído a uma tarefa.</li>
<li><strong>Cancelar</strong> – cancele as alterações feitas no recurso atribuído a uma tarefa.</li>
<li><strong>Atribuir automaticamente</strong> – Um recurso recrutado disponível que tem uma função correspondente é selecionado e atribuído automaticamente à tarefa selecionada.</li>
</ul></td>
</tr>
</tbody>
</table>

1. Na página **Todos os projetos** , selecione o projeto **Fase de atualização 2 de XYZ** .
2. Selecione **Plano** > **Atividades** > **Estrutura de detalhamento de trabalho**.
3. Selecione **Nova** para adicionar as seguintes atividades de um único nível à WBS:

    - Início
    - Planejamento
    - Executando
    - Monitoramento e controle
    - Fechar

4. Definir datas e trabalho (horas), conforme mostrado na ilustração.

    [![Configuração de datas e esforço](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Selecione a linha de tarefa **Início** e, no campo **Função**, selecione **Gerente de Projeto Sênior**.
6. Selecione **Publicar**.
7. Na mesma linha, no campo **Recurso**, selecione **Daniel Goldschmidt** e, em seguida, **Aceitar**.
8. Selecione a linha de tarefas **Planejamento** e, no campo **Função**, selecione **Analista de negócios**.
9. Selecione **Publicar** e selecione **Gerar equipe automaticamente**.
10. Na caixa de mensagem exibida, selecione **Sim**.
11. No campo **Recurso**, verifique se o valor é **Analista de negócios 1**.
12. Para o recurso **Analista de negócios 1**, abra a pesquisa e selecione **Iniciar atribuições de recurso**. Em seguida, selecione um trabalhador para a tarefa.
13. Selecione **Atribuição flexível** &gt; **Capacidade total**.

    > [!NOTE] 
    > Você não receberá um aviso de que o recurso especificado agora é 2 porque o número de recursos permanece em 1.

14. Na página **Estrutura de detalhamento de trabalho**, valide a atribuição de recursos na WBS e selecione **Salvar**.
