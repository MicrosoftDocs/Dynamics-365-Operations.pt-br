---
title: "Formalizar processos de negócios"
description: "O recurso de processo empresarial permite criar um modelo de processo empresarial para processos que precisam ser concluídos dentro de sua organização."
author: ShielaSogge
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ShielaS
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 812db9f1d319e4d16f83700a7153a0a3b318963e
ms.openlocfilehash: 48f80eac5009e1a241d501b0c4a3a70b78f5d709
ms.contentlocale: pt-br
ms.lasthandoff: 03/23/2018

---
# <a name="formalize-business-processes"></a>Formalizar processos empresariais
O recurso de processo empresarial permite criar um modelo de processo empresarial para processos que precisam ser concluídos dentro de sua organização. Por exemplo, a sua empresa poderá concluir uma auditoria de RH a cada ano. Um modelo pode ser criado para rastrear todas as tarefas que compõem a auditoria para ajudar a garantir que todas as tarefas são executadas, cada vez que o processo for concluído e, se necessário, para ajudar a garantir que as tarefas serão executadas na ordem correta. Os modelos podem ser reutilizados para processos recorrentes ou copiados para serem usados como ponto de partida para criar novos processos.

Depois que um modelo é criado, um processo pode ser iniciado e rastreado no espaço de trabalho do processo comercial.  Quando um processo comercial for iniciado, as tarefas serão atribuídas às pessoas apropriadas e terão uma data de vencimento. Nós abrangeremos os detalhes desses componentes abaixo.

## <a name="business-process-template"></a>Modelo do processo de negócios
Um modelo do processo comercial lista um grupo de tarefas que compõem um processo comercial. Os gerentes e os assistentes de recursos humanos podem criar processos comerciais por padrão.  Entretanto, isso pode ser alterado na configuração de segurança, editando a obrigação Manter processos comerciais genéricos.

Um proprietário do processo pode ser definido para cada processo.  O proprietário de processo terá visibilidade de todas as tarefas do processo e poderá reatribuir as tarefas ou alterar as datas de vencimento.  Por exemplo, o diretor de RH poderá criar um modelo de processo comercial para uma análise de benefícios.  O gerente de Remuneração e benefícios pode ser definido como o proprietário do processo, de forma que possa ter informações sobre as tarefas que precisam ser concluídas como parte da análise.  Um proprietário do processo não pode criar ou excluir processos comerciais ativos ou modelos de processos comerciais.

## <a name="task"></a>Tarefa
Um processo comercial geralmente consistem em várias tarefas. Algumas tarefas podem ser concluídas no Dynamics 365 for Talent[?], como revisão de ofertas internas de curso. Neste caso, um item de menu seria selecionado no campo do link da Tarefa. Outras tarefas podem envolver a revisão ou preenchimento de formulários em um site. A seleção do URL no campo Link da tarefa permite que o endereço Web seja inserido. Você pode inserir URLs para sites internos e externos neste campo. Você também pode criar tarefas para atividades que você concluir manualmente, como revisar a acessibilidade de todas as estruturas. Neste exemplo, um link de tarefa não é obrigatório. Essa flexibilidade permite acompanhar vários tipos de tarefas em um processo abrangente.

As tarefas podem ser atribuídas a um trabalhador específico ou a uma posição. Por exemplo, o gerente de Remuneração e benefícios sempre será a pessoa que conduz uma análise dos prêmios de seguro.   Ao criar esta tarefa, selecione Posição para o tipo de atribuição e depois selecione gerente de Remuneração e benefícios da lista de Posições. Quando o processo for iniciado, a tarefa será atribuída ao trabalhador que está na posição de Gerente de remuneração e benefícios. Você também pode atribuir uma tarefa a um trabalhador específico, selecionando Trabalhador no campo Tipo de atribuição e, em seguida, selecionando a pessoa apropriada.

As datas de vencimento da tarefa dependem de data de destino inserida no início do processo. Algumas tarefas devem ser concluídas antes e outras após a data de destino.  Ao definir uma tarefa, você irá inserir uma data de vencimento que é relativa à data de destino no campo Diferença da data de vencimento desde a data de destino. Por exemplo, suponha que o Gerente de remuneração e benefícios tenha que fazer uma análise dos prêmios de seguro 10 dias antes da auditoria de RH ser executada. A tarefa criada terá uma data de vencimento relativa à data de destino de -10. Portanto, se o processo for iniciado em 13 de maio, a tarefa vencerá em 3 de maio. Observação: As datas de vencimento também podem ser ajustadas após o processo ser iniciado.

Tarefas complexas podem exigir várias etapas ou precisar que a pessoa execute as tarefas para fornecer informações adicionais. É possível adicionar instruções a tarefa, e incluir também a formatação RTF para as instruções. As instruções podem fornecer informações adicionais sobre como concluir a tarefa à pessoa que está atribuída para concluí-la.

Iniciar um processo Um processo pode ser iniciado dentro de um Modelo de processo comercial, selecionando Iniciar processo.  Quando um processo for iniciado, as tarefas serão criadas para os trabalhadores selecionados e/ou as posições definidas nas tarefas incluídas no modelo do processo comercial. Uma data de vencimento também será atribuída a cada tarefa, adicionando ou subtraindo os dias de compensação de data-alvo (consulte informações sobre dias de compensação na seção da tarefa). Os processos comerciais ativos podem ser exibidos no espaço de trabalho Processos comerciais. 

## <a name="employee-self-service"></a>Autoatendimento para funcionários
Quando uma tarefa foi atribuída a um funcionário, as tarefas atribuídas poderão ser exibidas na página Autoatendimento para funcionários. Os funcionários que têm uma tarefa de processo comercial atribuída a eles poderão ver a tarefa, sua descrição, as instruções para conclui-la e o nome de uma pessoa de contato, e poderão abrir a página Dynamics365 ou a página da web associada, utilizando a página Autoatendimento para funcionários. As tarefas podem ser marcadas como em andamento, canceladas ou concluídas.

## <a name="business-process-workspace"></a>Espaço de trabalho do processo comercial
Os profissionais de RH podem exibir os processos comerciais ativos usando o espaço de trabalho Processo comercial. O espaço de trabalho lista todos os processos ativos e as tarefas associadas a cada um. A lista de tarefas abrangente pode ser filtrada por data de vencimento. A página também lista tarefas vencidas e tarefas atribuídas especificamente ao profissional de RH. Eles também podem atualizar o status de todas as tarefas e, se necessário, reatribuir as tarefas para ajudar a manter o andamento de todo o processo comercial.

## <a name="my-business-processes-workspace"></a>Espaço de trabalho Meus processos comerciais
Os proprietários do processo podem exibir os processos comerciais ativos atribuídos a eles do espaço de trabalho Meu processo comercial. O espaço de trabalho lista todos os processos ativos e as tarefas associadas que o usuário possui.  A lista de tarefas abrangente pode ser filtrada por data de vencimento. A página também lista as tarefas atribuídas especificamente ao proprietário do processo. O proprietário do processo também pode atualizar o status de todas as tarefas, bem como reatribuir todas as tarefas.

## <a name="navigating-business-processes"></a>Navegação pelos Processos comerciais
1.   Para adicionar um modelo de processo comercial, navegue até o link Processos comerciais - Administração de processos comerciais.
 - a.   Novo criará um novo modelo.
 - b.   Copiar do modelo copiará o modelo selecionado para um novo.
 - c.   Iniciar processo iniciará o processo comercial selecionado, atribuirá tarefas e calculará as datas de vencimento.  
2.  Para exibir os processos ativos e tarefas associadas, navegue até o espaço de trabalho Processos comerciais.

