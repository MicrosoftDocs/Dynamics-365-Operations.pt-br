---
title: "Subcontratação baseada em atividade"
description: "Este tópico descreve detalhadamente como usar atividades subcontratadas em um fluxo de produção para lean manufacturing."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 000bfcf5c3daea75fc257374dd471c62e94fbc16
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="activity-based-subcontracting"></a>Subcontratação baseada em atividade

[!include[banner](../includes/banner.md)]


Este tópico descreve detalhadamente como usar atividades subcontratadas em um fluxo de produção para lean manufacturing.

No Microsoft Dynamics 365 for Finance and Operations, há duas abordagens de subcontratação: ordens de produção e lean manufacturing. Na abordagem de lean manufacturing, o trabalho de subcontratação é moldado como serviço relacionado a uma atividade de um fluxo de produção. Um tipo especial de tipo de grupo de custo denominado **Terceirização direta** foi introduzido, e os serviços de subcontratação não fazem mais parte de uma lista de materiais (BOM). A contabilização de custos de trabalho subcontratado está totalmente integrada na solução de custos para lean manufacturing.

## <a name="production-flows-that-involve-subcontractors"></a>Fluxos de produção que envolvem subcontratados
O princípio básico de um fluxo de produção não muda quando as atividades são subcontratadas. Ainda há fluxos de material entre locais, as atividades de processo convertem materiais em produtos e as atividades de transferência movem material ou produtos de um local para outro. Você pode moldar locais e células de trabalho como gerenciado por fornecedor atribuindo a conta do fornecedor a um depósito ou a um recurso de um grupo de recursos.  

Com base nesses recursos, o lean manufacturing não requer qualquer característica específica para dar suporte ao fluxo de material e produtos. Todos os cenários possíveis envolvendo fornecedores como provedores de produção ou serviços de transporte podem ser moldados com base na arquitetura de atividades e fluxo de produção.  

Por exemplo, um subcontratado trabalha fora de um supermercado que está localizado no subcontratado. Quando unidades de manuseio de material são esvaziadas no subcontratado, os cartões kanban são retornados para a célula de montagem juntamente com a próxima remessa. O supermercado no subcontratado e então reabastecido. As transferências ao e do subcontratado podem ser moldadas como atividades de transferência explícitas para dar suporte a um processo de seleção e envio. Se um registro explícito não for necessário para dar suporte ao transporte físico, as atividades de transferência podem ser omitidas.  

Um subcontratado pode ser usado para balancear a carga da capacidade geral do fluxo de produção. Por exemplo, um fluxo de produção é moldado por meio de regras kanban programadas. O planejador usa o quadro de programação kanban para programar e nivelar a carga de células de trabalho sob demanda. O planejador também monitora a agenda de suprimentos consolidada para o supermercado na página **Plano de fornecimento**. Vários subcontratados podem ser moldados em um ou vários fluxos de produção, e talvez haja várias regras kanban que possam ser usadas para fornecer o mesmo produto ao mesmo local por meio de atividades diferentes. O planejador pode converter kanbans em uma regra kanban alternativa para reprogramar um kanban que foi criado originalmente para produção interna de um processo alternativo. Na verdade, a natureza subcontratada da célula de trabalho não tem impacto sobre o fluxo de produção. O mesmo princípio de trabalho aplica-se a duas células de trabalho internas paralelas ou a duas células subcontratadas.   

Assim como outra atividade em um fluxo de produção, as atividades subcontratadas podem consumir e fornecer materiais e produtos inventariados, não inventariados (trabalho em processo \[WIP\]) e semifinalizados. Em todos os casos, os processos de agendamento e execução de atividades subcontratadas são os mesmos. Além disso, eles processam o mesmo que os processos para trabalho interno.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Processo de compra para atividades subcontratadas (serviços)
O processo de compra para atividades subcontratadas é baseado no fluxo de materiais físicos registrado por progresso de trabalho do kanban, como Iniciar ou Concluir. O fluxo financeiro, como custo de trabalho subcontratado, é um fluxo secundário que acompanha o fluxo físico. Ao mesmo tempo, o processo de compra é um processo independente que permite o ajuste manual dos documentos de compra em cada etapa. Este é o processo de compra das atividades subcontratadas:

1.  Crie um contrato de compra. O contrato de compra é criado para o serviço e conectado à atividade do fluxo de produção.
2.  Criar uma ordem de compra. Uma ordem de compra de liberação pode ser criada para o serviço, com base nos trabalhos kanban agendados. Trabalhos para o mesmo serviço podem ser agrupados nas linhas de ordem de compra por dia, semana ou mês. As linhas de ordem de compra podem ser criadas a qualquer momento após a criação dos trabalhos kanban. As linhas de ordem de compra podem ser criadas até mesmo depois do fato. Essa opção geralmente é selecionada se um subcontratado fornecer serviços sem aviso adicional, com base nos kanbans ou cartões kanban que o subcontratado recebe. Nesse caso, desvios entre a ordem de compra e a fatura podem ser minimizados.
3.  Gere cartões kanban, material e uma lista de separação a serem enviados ao subcontratado para a preparação do processamento. Com base na modelagem detalhada do fluxo de produção, a preparação é feita no quadro kanban para atividades de processo por meio da lista de separação e da função de preparação. Alternativamente, a preparação é feita no quadro kanban para trabalhos de transferência por meio da lista de separação e do início e da conclusão. Para material inventariado, os processos podem receber suporte de um processo Lista de separação ou Remessa. Um conhecimento de embarque pode ser criado sob demanda.
4.  Gere unidades de manuseio de material kanban e cartões kanban. Após o processamento, os cartões são retornados no subcontratado. Geralmente, os cartões incluem uma nota de entrega que especifica o material físico que foi enviado. Uma referência para os serviços fornecidos não é necessária. A chegada do material ou produto no cliente é registrada no quadro kanban, dependendo dos cartões kanban. (O quadro kanban para atividades de processo ou o quadro kanban para trabalhos de transferência é usado, dependendo das atividades moldadas.)
5.  Crie um aviso de recebimento. O aviso de recebimento pode ser usado para substituir um documento de guia de remessa para os serviços recebidos. Os avisos de recebimento podem ser gerados com base nos trabalhos kanban concluídos para a atividade de subcontratação de um período selecionado. Para cada trabalho recebido, avisos são criados para a linha de ordem de compra relacionada. O aviso de recebimento pode ser impresso e enviado ao subcontratado como confirmação do recebimento.
6.  Gere uma fatura.

O processo termina quando o subcontratado é faturado em relação a um período. A conciliação da fatura é feita em comparação com os avisos de recebimento que são criados. Como os avisos de recebimento representam o recebimento físico exato do material, a correspondência de três formas é simplificada.

## <a name="configuring-activities-for-subcontracting"></a>Atividades de configuração para a subcontratação
As seções a seguir descrevem como configurar atividades para subcontratação.

### <a name="subcontracted-services"></a>Serviços subcontratados

O item de pagamento usado na subcontratação baseada em atividade deve ser um produto com as seguintes propriedades:

-   **Tipo de produto:** serviço
-   **Grupo de modelos de estoque:** fora do estoque

Esse requisito faz com que o modelo de estoque PEPS (primeiro a entrar, primeiro a sair) seja usado. **Observação:** o cálculo de custo dos produtos requer que o custo padrão do serviço seja definido. Um contrato de compra com o fornecedor é necessário. Caso contrário, o serviço não pode ser usado para subcontratação baseada em atividade.

### <a name="subcontracted-process-activities"></a>Atividades de processo subcontratadas

Para configurar uma atividade de processo como uma atividade subcontratada, siga estas etapas:

1.  Configure uma célula de trabalho subcontratada. Para configurar uma célula de trabalho como subcontratada, você deve criar um recurso do tipo **Fornecedor** e associá-lo à célula de trabalho (grupos de recursos). Uma categoria de custo de execução do grupo de custo **Terceirização direta** deve ser atribuída à célula de trabalho. As categorias de custo para configuração e quantidade não são necessárias.
2.  Após uma atividade de processo ser criada e relacionada a uma célula de trabalho subcontratada, você deve configurar um serviço para a atividade antes de a versão de fluxo de produção poder ser ativada. Conclua essa etapa na página **Detalhes da** **Atividade**. Para atividades que são associadas a uma célula de trabalho subcontratada, a Guia Rápida **Condições de serviço** é mostrada. Nessa Guia Rápida, adicione um serviço padrão válido para todos os itens de saída. Se itens de saída específicos precisarem de serviços diferentes ou parâmetros de cálculo de serviços diferentes (por exemplo, uma taxa de serviço diferente), você pode adicionar outros serviços à atividade.

## <a name="subcontracted-transfer-activities"></a>Atividades de transferência subcontratadas
A atividade de transferência é configurada como uma atividade subcontratada, dependendo da configuração **Fretado por** da atividade de transferência. As opções a seguir estão disponíveis:

-   **Expedidor** – A atividade é subcontratada se a transferência do depósito for gerenciada por um fornecedor (como definido por uma propriedade do depósito). Todos os contratos de compra selecionados para serviços devem ter a mesma ID de fornecedor que o depósito.
-   **Destinatário** – A atividade é subcontratada se a transferência para o depósito for gerenciada por um fornecedor (como definido por uma propriedade do depósito). Todos os contratos de compra selecionados para serviços devem ter a mesma ID de fornecedor que o depósito.
-   **Transportadora** – A atividade é subcontratada para qualquer fornecedor que ofereça o serviço. Para ser válida, a transportadora deve ser criada para gerenciamento de depósito e deve ter uma conta de fornecedor atribuída.

Em relação a atividades de processo, você deve configurar um serviço padrão para as atividades de transferência subcontratadas na Guia Rápida **Condições de serviço** da página **Detalhes da** **Atividade**.

## <a name="service-quantity-calculation"></a>Cálculo da quantidade de serviços
Todo o processo de compra é baseado em uma referência de item para um serviço. Essa referência de item é medida em uma unidade de medida de um serviço. Serviços são geralmente medidos no número de serviços (unidades) ou no tempo. Para calcular a quantidade de serviços, com base na conclusão registrada de trabalhos kanban, você pode usar os seguintes métodos:

-   **Cálculo baseado no número de trabalhos** – um trabalho kanban é igual a *n* unidades de serviço, independentemente da quantidade de produtos fornecidos. Em lean manufacturing, um trabalho corresponde a uma unidade de manuseio de material. Esse método de cálculo aplica-se a todos os serviços com um preço fixo por unidade de manuseio de material. Portanto, esse método geralmente se aplica a atividades de transferência. Contudo, também pode se aplicar a atividades de processo que processam as unidades de manuseio de material por completo.
-   **Cálculo que é baseado na quantidade de produtos** – A quantidade de serviço é relativa à quantidade de produtos programados/fornecidos. Quando a quantidade de produtos fornecidos é calculada, as quantidades de erro podem ser incluídas ou excluídas. Esse método de cálculo aplica-se a todos os casos nos quais o preço do serviço por unidade de produto processado é acordado.
-   **Cálculo que é baseado no tempo de atividade** – Os tempos de atividade teórica são calculados com base no tempo de processamento da atividade, na quantidade total processada e na taxa de produtividade do produto processado. Esse método de cálculo aplica-se a serviços que são pagos por hora e apresentam uma variação no tempo por produto processado.

## <a name="cost-accounting-of-subcontracted-services"></a>Contabilidade de custos dos serviços subcontratados
Quando o aviso de recebimento ou uma guia de remessa de fornecedor em uma ordem de compra criada para um fluxo de produção (em outras palavras, uma ordem de compra foi gerada com base nos trabalhos kanban para atividades subcontratadas) é lançada, o valor do recebimento é contabilizado nas contas WIP do fluxo de produção. Desvios de faturas também são contabilizados no fluxo de produção. Uma categoria de custo para trabalho subcontratado foi introduzida. Essa categoria de custo permite um controle transparente do valor de trabalho subcontratado alocado para WIP e consumido por período.  

Os custos de fluxo inverso para lean manufacturing no fim do período de custos calculam as variações reais dos produtos que são produzidos no fluxo de produção durante o período de avaliação de custo.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Transferências de modelagem como atividades subcontratadas
As pessoas geralmente consideram transporte como não produtivo e acham que ele não acrescenta valor. No entanto, quando o custo de subcontratação é comparado ao custo de produção interna, o custo de atividades de transporte adicionais deve ser considerado. Um fluxo de produção que abrange vários locais e requer serviços de transporte deve moldar o custo de transporte como parte do custo de fornecimento dos produtos ao cliente. 

A subcontratação baseada em atividade em lean manufacturing permite integrar transportadoras e fornecedores de transporte que movem materiais e produtos entre os locais de um fluxo de produção. Ao moldar uma atividade de transferência, você pode atribuir uma transportadora ou um fornecedor. Trabalho/atividades de transferência são baseados em um contrato de serviço e compra, e você pode criar ordens de compra e avisos de recebimento de acordo com os trabalhos de transferência reais. Essa funcionalidade é a mesma das atividades de processo subcontratadas.  

Portanto, o Finance and Operations agora tem suporte para cálculo da BOM que inclui serviços de transporte, criação de ordens de compra selecionadas, registro de recebimento integrado e integração de custos de serviços de transporte na avaliação de custo de fluxo de produção.




