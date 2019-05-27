---
title: Formalizar processos empresariais
description: Este tópico explica como você pode usar o recurso Processo comercial para criar um modelo de processo comercial para processos que devem ser concluídos na sua organização.
author: andreabichsel
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.openlocfilehash: 85950a1413cfd8745bb78a52eb9f7c81b8976605
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517321"
---
# <a name="formalize-business-processes"></a>Formalizar processos empresariais

[!include[banner](includes/banner.md)]

O recurso Processo comercial permite criar um modelo de processo comercial para processos comerciais que devem ser concluídos na sua organização. Por exemplo, sua empresa conclui uma auditoria de recursos humanos (RH) todo ano. Nesse caso, você pode criar um modelo que rastreia todas as tarefas do processo de auditoria. Esse modelo poderá então ajudar a garantir que todas as tarefas sejam realizadas sempre que a auditoria for realizada. Além disso, se as tarefas tiverem que ser concluídas em uma ordem específica, o modelo pode ajudar a garantir que sejam feitas na ordem correta.

Os modelos podem ser reutilizados para processos recorrentes. Eles também podem ser copiados e usados como ponto de partida para criar novos modelos.

Depois que um modelo de processo comercial é criado, um processo comercial pode ser iniciado e rastreado no espaço de trabalho **Processo comercial**. Quando um processo comercial é iniciado, as tarefas são atribuídas às pessoas apropriadas, e têm uma data de vencimento.

## <a name="business-process-templates"></a>Modelos de processo comercial
Um modelo de processo comercial lista um grupo de tarefas que compõem um processo comercial. Por padrão, os gerentes e os assistentes de RH podem criar processos comerciais. No entanto, você pode alterar as funções que podem criar processos comerciais modificando a obrigação **Manter processos comerciais genéricos** na configuração de segurança.

Para cada processo comercial, você pode definir um proprietário de processo. O proprietário de processo tem visibilidade de todas as tarefas do processo e pode reatribuir as tarefas ou alterar as datas de vencimento. Por exemplo, o diretor de RH cria um modelo de processo comercial para uma análise de benefícios e especifica o Gerente de remuneração e benefícios como o proprietário do processo. O Gerente de remuneração e benefícios então terá visibilidade das tarefas que devem ser concluídas como parte da análise.

Um proprietário de processo não pode criar novos processos comerciais ou modelos de processo comercial, nem excluir processos comerciais ativos ou modelos de processo comercial.

## <a name="tasks"></a>Tarefas
Um processo comercial geralmente consiste em várias tarefas. Algumas tarefas, como uma revisão de ofertas internas de curso, podem ser concluídas no Microsoft Dynamics 365 for Talent[?]. Nesse caso, uma opção é selecionada no campo **Link da tarefa**. Outras tarefas podem envolver a revisão ou o preenchimento de páginas em um site. Nesse caso, **URL** é selecionado no campo **Link da tarefa** e, em seguida, o endereço da Web pode ser inserido. Você pode inserir URLs para sites internos e externos. Você também pode criar tarefas para atividades que conclui manualmente, como uma revisão da acessibilidade de todas as estruturas. Nesse caso, um link de tarefa não é obrigatório. Essa flexibilidade permite acompanhar vários tipos de tarefas em um processo abrangente.

As tarefas podem ser atribuídas a um trabalhador específico ou a uma posição. Por exemplo, o Gerente de remuneração e benefícios sempre será a pessoa que faz uma análise dos prêmios de seguro. Portanto, ao criar essa tarefa, selecione **Posição** no campo **Tipo de atribuição** e, em seguida, selecione **Gerente de remuneração e benefícios** na lista de **Posições**. Quando o processo comercial é iniciado, a tarefa é atribuída ao trabalhador que estiver na posição de **Gerente de remuneração e benefícios**. Para atribuir uma tarefa a um trabalhador específico, selecione **Trabalhador** no campo **Tipo de atribuição** e, em seguida, selecione a pessoa apropriada.

As datas de vencimento das tarefas dependem da data de destino inserida no início do processo comercial. Algumas tarefas devem ser concluídas antes da data de destino, e outras talvez possam ser concluídas após a data de destino. Ao definir uma tarefa, no campo **Diferença da data de vencimento desde a data de destino**, você especifica uma data de vencimento relativa à data de destino. Por exemplo, o Gerente de remuneração e benefícios deve fazer uma análise dos prêmios de seguro 10 dias antes da auditoria de RH ser concluída. Nesse caso, a tarefa criada para a análise tem uma **Diferença da data de vencimento desde a data de destino** de valor **-10**. Portanto, se o processo comercial for iniciado em 13 de maio, a tarefa vencerá em 3 de maio.

> [!NOTE]
> As datas de vencimento também podem ser ajustadas após o processo comercial ser iniciado.

Tarefas complexas podem exigir várias etapas, ou as pessoas que executam as tarefas talvez precisem fornecer informações adicionais. Nesses cenários, é possível adicionar instruções a uma tarefa. As instruções podem fornecer à pessoa que está atribuída para concluir a tarefa informações adicionais sobre como concluí-la. Você pode até incluir a formatação RTF nas instruções.

## <a name="starting-a-business-process"></a>Como iniciar um processo comercial
Em um modelo de processo comercial, é possível iniciar um processo comercial selecionando **Iniciar processo**. Quando um processo é iniciado, as tarefas são criadas para os trabalhadores selecionados ou as posições definidas nas tarefas incluídas no modelo. Uma data de vencimento também é atribuída a cada tarefa, adicionando ou subtraindo o número de dias de compensação da data de destino, conforme explicado na seção "Tarefas". Você pode exibir os processos comerciais ativos no espaço de trabalho **Processos comerciais**.

## <a name="employee-self-service"></a>Autoatendimento para funcionários
Depois que uma tarefa é atribuída a um funcionário, ele pode exibir essa e todas as suas tarefas atribuídas na página **Autoatendimento para funcionários**. Para cada tarefa de processo comercial atribuída a ele, o funcionário pode ver o nome e a descrição da tarefa, as instruções para concluí-la e o nome de uma pessoa de contato. Na página **Autoatendimento para funcionários**, o funcionário também pode abrir a página associada no Microsoft Dynamics 365 ou a página da Web associada, e pode marcar as tarefas como em andamento, canceladas ou concluídas.

## <a name="business-process-workspace"></a>Espaço de trabalho do processo comercial
Os profissionais de RH podem exibir os processos comerciais ativos no espaço de trabalho **Processo comercial**. Esse espaço de trabalho lista todos os processos ativos e as tarefas associadas a cada um. A lista de tarefas abrangente pode ser filtrada por data de vencimento. Esse espaço de trabalho também lista tarefas vencidas e tarefas atribuídas especificamente ao profissional de RH. O profissional de RH também pode atualizar o status de todas as tarefas e, conforme necessário, reatribuir as tarefas para ajudar a manter o andamento de todo o processo comercial.

## <a name="my-business-processes-workspace"></a>Espaço de trabalho Meus processos comerciais
Os proprietários de processo podem exibir os processos comerciais ativos atribuídos a eles no espaço de trabalho **Meu processo comercial**. Esse espaço de trabalho lista todos os processos ativos que o usuário possui, e as tarefas associadas. A lista de tarefas abrangente pode ser filtrada por data de vencimento. O espaço de trabalho também lista as tarefas atribuídas especificamente ao proprietário do processo. O proprietário do processo também pode atualizar o status de todas as tarefas e reatribuir qualquer tarefa.

## <a name="navigating-business-processes"></a>Navegação pelos processos comerciais
Para criar ou copiar um modelo de processo comercial, ou iniciar um processo comercial, navegue até Processos comerciais - links – Administração de processos comerciais. Então, você poderá executar as seguintes ações:

- Selecionar **Novo** para criar um novo modelo de processo comercial.
- Selecionar **Copiar do modelo** para copiar o modelo selecionado em um novo modelo.
- Selecionar **Iniciar processo** para iniciar o processo comercial selecionado, atribuir tarefas e calcular as datas de vencimento.

Para exibir os processos ativos e as tarefas associadas, abra o espaço de trabalho **Processos comerciais**.

