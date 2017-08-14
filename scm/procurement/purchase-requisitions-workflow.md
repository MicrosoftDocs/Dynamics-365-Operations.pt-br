---
title: "fluxo de trabalho de requisição de compra"
description: "O processo de fluxo de trabalho move requisições de compra pelo processo de revisão, de um status de Rascunho para um status final de Aprovado. Quando uma requisição de compra é enviada para revisão, o processo de fluxo de trabalho é iniciado. Após a aprovação de uma requisição de compra, uma ordem de compra pode ser gerada para as linhas de requisição de compra e enviadas ao fornecedor para o preenchimento da ordem."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqAuthorization, WorkflowParticipantExpenToken
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2234
ms.assetid: dad3ba5a-2892-45d2-874a-300896f59b34
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 95d1d3a34728aab38f77635ae68bea16b08f6587
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---

# <a name="purchase-requisition-workflow"></a>fluxo de trabalho de requisição de compra

[!include[banner](../includes/banner.md)]


O processo de fluxo de trabalho move requisições de compra pelo processo de revisão, de um status de Rascunho para um status final de Aprovado. Quando uma requisição de compra é enviada para revisão, o processo de fluxo de trabalho é iniciado. Após a aprovação de uma requisição de compra, uma ordem de compra pode ser gerada para as linhas de requisição de compra e enviadas ao fornecedor para o preenchimento da ordem.

Antes que uma requisição de compra possa ser enviada para revisão, você deve configurar um fluxo de trabalho. O processo de fluxo de trabalho podem incluir uma ou mais etapas de revisão em qualquer ordem. O processo de fluxo de trabalho também pode ser configurado para ignorar as tarefas de revisão e para aprovar automaticamente a requisição de compra. Você pode configurar o fluxo de trabalho para encaminhar a requisição de compra como um único documento, ou pode encaminhar as linhas de requisição de compra individuais para os revisores apropriados. Você também pode criar um cenário onde a requisição de compra é encaminhada como um único documento para alguns revisores e as linhas de requisição de compra selecionadas são encaminhadas para outros revisores.  

Se as linhas de requisição de compra forem revisadas individualmente, o processo de revisão deverá ser concluído para todas as linhas de requisição de compra antes que o processo do fluxo de trabalho possa prosseguir para a próxima etapa e antes que o processo de revisão da requisição de compra como um todo possa ser concluído. Quando o processo de revisão for concluído para a requisição de compra e todas as suas linhas, o status geral da requisição de compra será atualizado para **Aprovado**.  

Você pode configurar seu fluxo de trabalho para representar o processo comercial para requisições de compra da sua organização. Quando você configurar seu processo de fluxo de trabalho de requisição de compra, considere as seguintes questões:

-   Quais despesas que devem ser revisadas?
-   Que despesas podem ser aprovadas automaticamente?
-   Quem deve revisar e aprovar solicitações de despesas? Para que funções esses usuários são atribuídos?
-   Qual processo deve ser seguido se um revisor não estiver disponível?

Os exemplos a seguir ilustram duas formas como você pode configurar um fluxo de trabalho para requisições de compra:

## <a name="example-1-route-a-purchase-requisition-as-a-single-document-for-review"></a>Exemplo 1: Encaminhar uma requisição de compra como um único documento para revisão
A ilustração a seguir mostra como uma requisição de compra pode fluir pelo processo de revisão de fluxo de trabalho como um único documento. As linhas da requisição de compra não são roteadas individualmente. As funções a seguir estão incluídas no processo de fluxo de trabalho deste exemplo:

-   **Solicitante** – O usuário que solicita os itens ou os serviços. O solicitante pode preparar a requisição de compra ou outro trabalhador pode preparar a requisição de compra em nome do solicitante. Esse trabalhador é chamado de preparador. O preparador é responsável pelo gerenciamento da requisição de compra em todo o processo de revisão. Somente o preparador da requisição de compra pode modificá-la.

**Observação:** Um trabalhador deve obter as permissões apropriadas para criar uma requisição de compra em nome de outra pessoa. Use a página **Permissão de requisição de compra** para configurar essas permissões.

-   **Agente de compra** – O usuário que executa uma revisão de aquisição e pode aprovar o documento.
-   **O gerente do solicitante** – O usuário que executa uma revisão administrativa e que pode aprovar o documento.

![Processo de revisão do fluxo de trabalho de requisição de compra](./media/purchreqworkflowoverview_submission.gif)  
Neste exemplo, o processo de fluxo de trabalho para a requisição de compra inclui as seguintes etapas:

1.  O preparador envia uma requisição de compra para revisão.
2.  O agente de compras recebe uma notificação. A notificação solicita que o agente de compras verifique as informações da requisição de compra. Se as informações necessárias estiverem ausentes, o agente de compras poderá adicioná-las ou devolver a requisição de compra ao preparador para adicioná-la. Quando todas as informações obrigatórias forem preenchidas, a requisição de compra poderá avançar para a próxima etapa do processo de revisão.
3.  O gerente do solicitante examina a requisição de compra. A requisição de compra pode ser encaminhada para o gerente do solicitante se, por exemplo, o valor da requisição de compra exceder o limite de gastos do solicitante para requisições de compra. O gerente do solicitante pode aprovar ou rejeitar a requisição de compra ou devolvê-la ao preparador para alterações.

## <a name="example-2-route-the-individual-purchase-requisition-lines-for-review"></a>Exemplo 2: Rotear as linhas de requisição de compra individuais para revisão
A ilustração a seguir mostra como as linhas de requisição de compra individuais podem ser encaminhadas através do fluxo de trabalho. Em geral, o processo para cada linha geralmente é igual ao processo de uma requisição de compra examinada como um único documento. Entretanto, cada linha deve concluir o processo de fluxo de trabalho individualmente, antes que o fluxo de trabalho possa ser concluído para a requisição de compra como um todo.  

Neste exemplo, um trabalhador insere uma solicitação de cartazes e camisetas para uma campanha de marketing. O custo dos cartazes é dividido entre o departamento de Marketing e o departamento de Vendas. Se os custos de cartazes ou de camisetas exceder a autoridade de limite de assinatura para os gerentes de departamento, a requisição de compra também deverá ser examinada pelo gerente de grupo.  

As funções a seguir estão incluídas no processo de fluxo de trabalho deste exemplo:

-   **Solicitante** – O usuário que solicita os itens ou os serviços. O solicitante pode preparar a requisição de compra ou outro trabalhador pode preparar a requisição de compra em nome do solicitante. Esse trabalhador é chamado de preparador. O preparador é responsável pelo gerenciamento da requisição de compra em todo o processo de revisão. Somente o preparador da requisição de compra pode modificá-la.

**Observação:** Um trabalhador deve obter as permissões apropriadas para criar uma requisição de compra em nome de outra pessoa. Use a página **Permissão de requisição de compra** para configurar essas permissões.

-   **Agente de compra** – O usuário que executa uma revisão de aquisição e pode aprovar o documento.
-   **O gerente do solicitante** – O usuário que executa uma revisão administrativa e que pode aprovar o documento.
-   **Gerente de departamento** – O usuário que executa uma revisão de despesas e que pode aprovar o documento.
-   **Gerente de grupo** – O usuário que executa uma revisão de autoridade de assinatura e que pode aprovar o documento.

![Processo de revisão do fluxo de trabalho da linha de requisição de compra](./media/purchreqlineworkflowoverview.gif)  
Neste exemplo, o processo de fluxo de trabalho para as linhas de requisição de compra inclui as seguintes etapas:

1.  O preparador envia uma requisição de compra para revisão. Cada linha é encaminhada ao revisor configurado no processo para recebê-la no processo do fluxo de trabalho.
2.  O agente de compras recebe uma notificação. A notificação solicita que o agente de compras verifique as informações da requisição de compra e nas linhas da requisição de compra. Quando a requisição de compra é aberta pelo agente de compras, todas as linhas estão visíveis, mas um indicador visual mostra quais linhas foram enviadas para o agente de compras para revisão. Se as informações necessárias estiverem ausentes, o agente de compras poderá adicioná-las ou devolver a linha da requisição de compra ao preparador para adicioná-la. Quando todas as informações obrigatórias forem preenchidas, a linha da requisição de compra poderá avançar para a próxima etapa do processo de revisão. As linhas de requisição de compra podem continuar no processo de revisão independentemente umas das outras.
3.  O gerente de linha do solicitante examina e aprova as linhas de requisição de compra. A aprovação pode ser encaminhada para o gerente do solicitante se, por exemplo, o valor de uma linha da requisição de compra exceder o limite de gastos do solicitante para linhas da requisição de compra. O gerente poderá aprovar ou rejeitar uma ou ambas as linhas de requisição de compra.
4.  O gerente de departamento para o departamento de Marketing examine as linhas de requisição de compra para os cartazes e as camisetas. O gerente do departamento de Vendas só examina a linha de requisição de compra para os cartazes, porque se trata do único custo que está sendo cobrado do departamento de Vendas.
5.  O gerente do grupo examina e aprove a linha de requisição de compra para as camisetas somente se a aprovação do gerente do grupo for necessária porque, por exemplo, o valor na linha de requisição de compra excede o limite de aprovação do gerente de departamento. O gerente do grupo não precisa aprovar a linha de requisição de compra para os cartazes.

## <a name="configuring-a-workflow-for-purchase-requisitions"></a>Configurando um fluxo de trabalho para requisições de compra
Para rotear uma requisição de compra para revisão, você deverá configurar os processos de fluxo de trabalho da requisição de compra. O processo de fluxo de trabalho definido por você controla a interação entre o usuário que solicitou os itens (o solicitante) e o revisor e aprovador no fluxo de trabalho. O roteiro da requisição de compra depende das condições especificadas na configuração do fluxo de trabalho. Por exemplo, essas condições determinam quando a requisição de compra será enviada, o usuário ou a função para a qual ela deve ser enviada e as ações que os usuários podem executar.  

Os exemplos deste tópico mostram como uma requisição de compra pode ser encaminhada através de um fluxo de trabalho como um único documento ou como linhas de requisição de compra individuais. Você também pode configurar um fluxo de trabalho para requisições de compra que refletem a revisão de controle interno das requisições de compra definidas para sua organização.  

Os participantes ou os revisores aos quais uma tarefa foi atribuída em um fluxo de trabalho podem ser membros de um grupo de usuários específico, usuários que têm uma função de segurança específica, usuários que estejam associados ao emissor em uma hierarquia administrativa ou usuários nomeados ou usuários que tenham responsabilidades específicas de despesas.

### <a name="purchase-requisition-expenditure-reviewers"></a>Revisores das despesas de requisições de compra

As configurações de revisor de despesas permitem que você encaminhe despesas dinamicamente para revisão com base no usuário atribuído a uma função de projeto ou uma dimensão financeira na qual a despesa está sendo cobrada. O processo de fluxo de trabalho usa a função de projeto ou o proprietário da dimensão financeira especificado para determinar para quem a despesa deverá ser encaminhada.  

Você poderá definir uma ou mais configurações de revisor de despesas e selecionar uma configuração ao criar um fluxo de trabalho. Você pode configurar valores de revisor de despesas para cada entidade legal em sua organização. Depois de definir as configurações de revisor de despesas, você atribui a configuração à tarefa de fluxo de trabalho.  

Não é necessário definir configurações de revisor de despesas. Você poderá atribuir usuários ou grupos de usuários específicos como revisores ao definir seu fluxo de trabalho. No entanto, se você tiver uma organização complexa, os revisores de despesas poderão aumentar a eficiência de seu processo de aprovação. Além disso, se você configurar revisores de despesas, não será necessário atualizar as atribuições de revisor de fluxo de trabalho toda vez que um revisor alterar suas funções de trabalho.  

Você pode configurar os revisores de despesa na página **Revisores das despesas de requisições de compra**. Crie uma configuração de revisor de despesas e insira valores para cada entidade legal na sua organização. Para as requisições atribuídas a um projeto, você pode especificar a função responsável por rever as requisições: Gerente do projeto, Controlador do projeto ou Gerente de vendas do projeto. As despesas serão encaminhadas ao usuário atribuído para essa função especificada. Você também poderá encaminhar a despesa ao proprietário da dimensão financeira marcando a opção apropriada da dimensão financeira na guia **Distribuições de organização**.  

Para usar um dos revisores de despesas que você configura em um fluxo de trabalho, você deverá definir a opção **Tipo de participante** como **Participantes de despesas** nas propriedades **Atribuição** para o elemento de fluxo de trabalho relevante.

<a name="see-also"></a>Consulte também
--------

[Criar uma requisição para consumo (Guia de tarefas)](/dynamics365/unified-operations/supply-chain/procurement/tasks/create-requisition-consumption)

[Definir fluxos de trabalho de processos de negócios para requisições de compra](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[Fluxos de trabalho de compras e fornecimento](procurement-sourcing-workflows.md)

[Visão geral de requisição de compra](purchase-requisitions-overview.md)




