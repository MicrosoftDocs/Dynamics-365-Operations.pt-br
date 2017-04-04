---
title: "com base Atividade- subcontratação"
description: "Este tópico descreve, em detalhes, como usar atividades subcontratadas um fluxo de produção para o lean manufacturing."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8e57c53ca894aa44b71e15c1f66bd7c722ea8a81
ms.lasthandoff: 03/31/2017


---

# <a name="activity-based-subcontracting"></a>com base Atividade- subcontratação

Este tópico descreve, em detalhes, como usar atividades subcontratadas um fluxo de produção para o lean manufacturing.

No Microsoft Dynamics 365 para operações, há duas abordagens para subcontratar: ordens de produção e lean manufacturing. A perspectiva de fabricação tendenciosa, os trabalhos são modelados subcontratação de como um serviço relacionada a uma atividade de um fluxo de produção. Um tipo especial tipo de custo previsto de grupo que é chamado ** terceirização direta ** foi introduzido, e serviços a subcontratação deixou parte de uma lista de materiais (BOM). A contabilização de custo previsto de trabalho subcontratados é totalmente integrada a solução de custos para o lean manufacturing.

## <a name="production-flows-that-involve-subcontractors"></a>Fluxos de produção que envolvem subcontratados
O princípio básico de um fluxo de produção não é alterado quando as atividades são subcontratadas. O material ainda direta entre as localizações, material de converter atividades de processo a produtos, as atividades e de transferência movem material ou produtos de um local para outra. Será possível modelar localizações e células de trabalho como padrões gerenciadas atribuir a conta de fornecedor para um depósito ou a um recurso de um grupo de recursos.  

Com base nos recursos, novidades lean manufacturing não requer qualquer recursos específicos para oferecer suporte ao fluxo de material e produtos. Os possíveis cenários envolvendo fornecedores como prestadores de serviços de produção ou de transporte podem ser modelados com a arquitetura do fluxo de produção e atividades.  

Por exemplo, um subcontratado concede certeza de que é um supermercado está localizado no subcontratado. Quando as unidades de manuseio é esvaziadas o subcontratado, os cartões kanban são retornados à célula do assembly remessa com a seguinte. No supermercado subcontratado é reabastecido. As transferências a subcontratado e podem ser modeladas como atividades de transferência explícitas para oferecer uma separação e um processo de remessa. Se um registro explícito não é necessário para dar suporte físico transporte, atividades de transferência podem ser omitidas.  

Um subcontratado pode ser usada para balancear carga a capacidade total de fluxo de produção. Por exemplo, um fluxo de produção for modelado usando regras kanban agendados. O planejador usa em branco de planejamento do kanban para programar e carregar o nível ambas as células de trabalho em demanda. O planejador também monitorar a agenda consolidada de fonte para o supermercado ** plano de fornecimento ** na página. Vários subcontratados podem ser modelados em um ou em vários fluxos de produção, e pode haver várias regras kanban que podem ser usadas para fornecer os mesmos produtos no mesmo local em atividades diferentes. O planejador possível converter kanban para uma regra kanban alternativo reprogramar um kanban criada originalmente para produção interna a um processo alternativo. Na verdade, a natureza subcontratada de trabalho não tem impacto no fluxo de produção. O mesmo princípio de operação se aplica para duas células de trabalho ou internas paralelas para duas células subcontratadas.   

Como qualquer outra atividade de um fluxo de produção, as atividades podem subcontratadas consumir fornecer e material e inventariados produtos, não inventariados (WIP\]\[do trabalho em andamento), além semiconcluídos. Em todos os casos, os processos para programar e executar atividades subcontratadas são iguais. Além disso, esses suzana o mesmo que os processos de trabalho interno.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Processo de compra para atividades subcontratadas (serviços)
O processo de compra para atividades subcontratadas é baseado em material físico fluxo registrado pelo progresso dos trabalhos kanban, por exemplo, Inicial ou concluído. O fluxo financeiro, por exemplo, custos, subcontratados de trabalho é um fluxo secundário que rastreia o fluxo físico. Ao mesmo tempo, o processo de compra é um processo independente que permita o ajuste manual dos documentos de compra em cada etapa. Aqui está o processo de compra para atividades subcontratadas:

1.  Criar um acordo de compra. O contrato de compra é criada para o serviço e conectado à atividade do fluxo de produção.
2.  Criar uma ordem de compra. Uma ordem de compra de versão pode ser criado para o serviço, com base nos trabalhos kanban agendados. O trabalho para o mesmo serviço podem ser agrupados a linhas de ordem de compra, na dia, semana ou mês. Linhas de ordem de compra podem ser criadas a qualquer momento depois que os trabalhos kanban são criados. Linhas de ordem de compra podem ser criadas mesmo após vestuário. Esta opção é selecionada se um subcontratado geralmente fornece serviço sem aviso adicional, com base nos kanban ou nos cartões kanban que recebe o subcontratado. Neste caso, os desvios entre a ordem de compra e a nota fiscal podem ser minimizados.
3.  Gerar, cartões kanban material, e uma lista de separação para enviar para o subcontratado para preparar para processar. Com a modelagem detalhada do fluxo de produção, a preparação é feita no quadro kanban para atividades de processo com a lista de separação e a função de preparação. Alternativamente, a preparação é feita no quadro kanban para trabalhos de transferência usando a lista de separação e o início ou a conclusão. Para material inventariado, os dois processos possam ser aceitos por um processo de WMS- separação e de remessa. Um conhecimento de embarque pode ser criada em demanda.
4.  Gerar unidades de manuseio e cartões kanban do kanban. Depois que suzana, cartões são retornados subcontratado. Geralmente, as fichas incluem uma observação de entrega que especifica físico material enviado. Uma referência aos serviços proporcionados não é necessária. A entrada de material ou produto do cliente é registrada no quadro kanban, segundo os cartões kanban. (O quadro kanban para atividades do processo ou o quadro kanban para trabalhos de transferência são usados, dependendo das atividades modeladas.).
5.  Crie um advisory de recebimento. O advisory recebimento pode ser usada para substituir um documento da guia de remessa para os serviços recebidos. Os advisories de recebimento podem ser gerados com base nos trabalhos kanban concluído para a atividade de subcontratação um período selecionado. Para cada recibo de trabalho, os advisories é criada para a linha de ordem de compra. O advisory recebimento pode ser impressa e enviada para o subcontratado como confirmação de recebimento.
6.  Gerar uma nota fiscal.

O processo termina quando o subcontratado é faturado para um período. A conciliação de nota fiscal é feita nos advisories de recibo que são criados. Como os advisories representam de recebimento o recebimento físico como material, a correspondência tripartido é simplificada.

## <a name="configuring-activities-for-subcontracting"></a>Configurando atividades para subcontratar
As seções a seguir descrevem como definir atividades para subcontratar.

### <a name="subcontracted-services"></a>Subcontratados serviços

O item de pagamento usado na atividade- subcontratação deve ser baseada um produto que tenha as seguintes propriedades:

-   ** Tipo de produtos: ** Serviço
-   ** Grupo modelo de estoque: ** Não armazenado

Esse requisito impõe uso de modelos de estoque (FIFO) do primeiro a entrar, primeiro a sair. ** Observação: ** O cálculo do custo previsto de produto aos custos padrão de serviço estão definidos. Um contrato de compra com o fornecedor é necessário. Se não, o serviço não pode ser usado para a atividade- subcontratação base.

### <a name="subcontracted-process-activities"></a>Atividades subcontratadas de processo

Para configurar uma atividade do processo de uma atividade subcontratada, rastrear essas etapas.

1.  Configurar uma célula de trabalho subcontratada. Para configurar uma célula de trabalho como subcontratada, crie um recurso de ** ** digite-a fornecedor e associar-l à célula de trabalho (grupo de recursos.) Uma categoria de custo previsto de preparação ** terceirização direta ** tipo de custo previsto do grupo deve ser atribuída à célula de trabalho. As categorias de custo previsto para a instalação e a quantidade não é obrigatória.
2.  Depois que uma atividade do processo é criada e relacionada a uma célula de trabalho subcontratada, configure um serviço da atividade para a versão de fluxo de produção pode ser ativada. Concluir essa etapa ** atividade ** ** em detalhes ** página. Para atividades associadas a uma célula de trabalho, subcontratada ** o serviço ** o estilo FastTab será exibido. Neste FastTab, adicionar um serviço padrão que é válida para todos os itens de saída. Se itens específicos de saída exigem serviços diferentes ou parâmetros diferentes de serviço (por exemplo, uma taxa de serviço) diferente, você pode adicionar outros serviços à atividade.

## <a name="subcontracted-transfer-activities"></a>Atividades subcontratadas de transferência
Uma atividade de transferência é configurada como uma atividade subcontratada, dependendo ** ** enviado pela configuração da atividade de transferência. As opções a seguir estão disponíveis:

-   ** O remetente ** – a atividade for subcontratado se a transferência de depósito será gerenciada por um fornecedor (como definido por uma propriedade de depósito). Todos os contratos de compra selecionados de serviços devem ter o mesmo ID do fornecedor do depósito.
-   ** O destinatário ** – a atividade for subcontratado se a transferência para o depósito será gerenciada por um fornecedor (como definido por uma propriedade de depósito). Todos os contratos de compra selecionados de serviços devem ter o mesmo ID do fornecedor do depósito.
-   ** O transportador ** – a atividade é subcontratada a qualquer fornecedor que oferecem o serviço. Seja válido, uma operadora será criada para o gerenciamento de depósito e deve ter uma conta atribuído ao fornecedor.

Quanto para atividades de processos, você deverá configurar o serviço padrão para atividades de transferência subcontratadas ** contrato de serviço em FastTab ** ** atividade ** ** detalhes ** página.

## <a name="service-quantity-calculation"></a>Cálculo da quantidade de serviços
O processo de compra inteira baseia-se em referência de um serviço. Essa referência de item é medida em uma unidade de medida de um serviço. Os serviços são medidos normalmente em número de unidades (serviços) ou horário. Para calcular a quantidade de serviço, com base na conclusão registrada dos trabalhos kanban, você pode usar os seguintes métodos:

-   ** O cálculo baseado no número de trabalho ** – um trabalho kanban igual unidades de *n* de serviço, independentemente da quantidade de bens que é fornecida. Lean manufacturing em um trabalho, corresponde a uma unidade de manuseio. Esse método de cálculo se aplica a todos os serviços com um preço fixo por unidade de manuseio. Portanto, esse método se aplica geralmente atividades de transferência. Entretanto, também poderá aplicar processar as atividades que suzana unidades de manuseio inteiras.
-   ** O cálculo que é baseado na quantidade de bens ** – a quantidade de serviço é relativo à quantidade de bens agendado/fornecida. Quando a quantidade fornecida de produtos é calculada, as quantidades de erro podem ser incluídas ou excluídas. Esse método de cálculo se aplica a todos os casos em que o preço de serviço por unidade de produtos é concordado processados.
-   ** O cálculo que é baseado no tempo da atividade ** – tempo teóricos de atividades é calculado, com base no tempo de processamento da atividade, quantidade processada total, e da taxa de transferência processados de produto. Esse método de cálculo se aplica aos serviços que são pagos para a hora e têm uma variação por produto a partir processados.

## <a name="cost-accounting-of-subcontracted-services"></a>Contabilização de custo previsto subcontratados de serviços
Quando o recebimento consultivo ou guia de remessa do fornecedor em uma ordem de compra que foi criado para um fluxo de produção (ou seja uma ordem de compra que foi gerado com base em trabalhos kanban para atividades subcontratadas) é lançada, o valor de recebimento será contabilizado em contas WIP de fluxo de produção. Os desvios das notas fiscais são explicados também para o fluxo de produção. Uma categoria de custo estimado para subcontratados trabalhos foi introduzida. Essa categoria de custo previsto transparente permite o acompanhamento do valor de trabalho atribuídos subcontratados o WIP e consumidos por período.  

Os custos de fluxo inverso para o lean manufacturing o final de um período de custo reais calcular as variações de produto geradas no fluxo de produção durante o período de custos.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modelando transferências subcontratadas atividades como
Contatos frequentemente consulte o transporte improdutivo e pensam que não adiciona sem valor. Entretanto, quando o custo a subcontratação são comparados a produção interna de custo, custo de atividades de transporte adicionais devem ser consideradas. Um fluxo de produção que meça várias localizações e exige serviço de transporte deve modelagem os custos de transporte como parte do custo de fornecer produtos ao cliente. 

a subcontratação baseada em Atividade- permitem lean manufacturing integrar transportadoras e fornecedores de transporte que movem material e produtos entre as localizações de um fluxo de produção. Modelando uma atividade de transferência, você pode atribuir uma operadora ou fornecedor. Atividades de transferência/trabalho são baseadas em um serviço e um contrato de compra, e pode criar ordens de compra e advisories de recebimento, com base em trabalho reais de transferência. Essa funcionalidade é igual à funcionalidade de atividades subcontratadas de processo.  

Portanto, o dynamics 365 para operações suporta agora o cálculo de BOM que contém serviço de transporte, a criação de ordens de compra relacionadas, registro integrado de recebimento, e a integração do serviço de transporte em custos do fluxo de produção.


