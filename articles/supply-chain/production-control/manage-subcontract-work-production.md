---
title: Gerenciar trabalhos de subcontratação na produção
description: Este tópico explica como operações subcontratadas são gerenciadas no Dynamics 365 Supply Chain Management. Em outras palavras, explica como as operações de produção que são alocadas para um recurso são gerenciadas por um fornecedor.
author: cvocph
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup, ProdBOMVendorListPagePreviewPane, ProdBOMVendor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11728694565b10bf0336671f6c1b5f43cbcadf78
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825810"
---
# <a name="manage-subcontracting-work-in-production"></a>Gerenciar trabalhos de subcontratação na produção

[!include [banner](../includes/banner.md)]

Este tópico explica como operações subcontratadas são gerenciadas no Dynamics 365 Supply Chain Management. Em outras palavras, explica como as operações de produção que são alocadas para um recurso são gerenciadas por um fornecedor.

Nos [processos de produção](production-process-overview.md), o trabalho pode ser feito por recursos que de propriedade ou administrados por fornecedores. Normalmente, os recursos de fornecedor são usados para nivelar a demanda adicional periódica que ultrapassa a capacidade disponível de recursos próprios da empresa. O fornecedor também pode oferecer [recursos](resource-capabilities.md) específicos ou recursos com preço mais baixo.  

Dependendo dos recursos do fornecedor usados em um processo de produção, um [roteiro](routes-operations.md) geralmente tem requisitos de logística adicionais, porque o material e os produtos semiacabados primeiro devem ser transportados para o local do fornecedor. O resultado da operação subcontratada deve ser transportado para o local que é alocado para a próxima operação ou para um depósito de mercadorias acabadas.  

Quando as operações ou atividades de subcontratação são usadas, elas afetam todos os estágios das operações, desde a definição das operações que são obrigatórias, na produção, avaliação de custo, previsão, planejamento e agendamento, até o gerenciamento de logística de materiais, produtos semiacabados e mercadorias acabadas. Por fim, esses recursos exigem seus próprios processos para contabilidade e controle de custo.  

Para recursos internos, uma taxa de custo fixo normalmente é alocada durante um período. Em contraste, o custo de recursos subcontratados é baseado no preço de compra do serviço relacionado. O serviço é definido como outro produto e é usado para conduzir os processos de aquisição e compra de uma determinada operação subcontratada.  

Atualmente, não há nenhum conceito explícito de produtos semifinalizados no Supply Chain Management. Para uma ordem de produção que exija mais de uma operação para transformar matérias-primas uma mercadoria acabada, a mercadoria concluída é lançada de volta ao estoque apenas na última operação. Os produtos semiacabados que as operações anteriores produzem são contabilizados no trabalho em andamento (WIP), mas não são lançados ou rastreados no estoque. Embora você possa dividir os roteiros e listas de materiais (BOMs) em várias unidades menores, essa abordagem aumenta o número de produtos, BOMs e roteiros a serem gerenciados.  

Há dois métodos para modelagem de trabalho de subcontratação para operações de produção. Esses métodos diferentes na forma como o processo a subcontratação pode ser modelado, na forma como os produtos semiacabados são representados no processo e na maneira pela qual o controle de custos é gerenciado.

-   Subcontratação de operações de roteiro em ordens de produção ou ordens de lote
    -   O produto de serviço deve ser um produto em estoque e deve fazer parte da BOM.
    -   Este método oferece suporte PEPS (primeiro a entrar, primeiro a sair) ou custo padrão.
    -   Os produtos semiacabados são representados por produto de serviço no processo.
    -   O controle de custos aloca os custos associados ao trabalho subcontratado aos custos de materiais.
-   Subcontratação de atividades do fluxo de produção em um fluxo de produção de lean
    -   O serviço é um produto de serviço de não estocado, e não faz parte da BOM.
    -   Este método usa contratos de compra como contratos de serviço.
    -   Este método usa custos de fluxo inverso.
    -   Este método permite a aquisição agregada e assíncrona. (O fluxo do material é independente do processo de compras.)
    -   O controle de custos aloca trabalho subcontratados em seu próprio bloco de divisão de custo.

## <a name="subcontracting-of-route-operations"></a>Subcontratação de operações de roteiro
Para usar a subcontratação de operações de roteiro para a ordens de produção ou de lotes, o produto de serviço que é usado para a compra do serviço deve ser definido como produto do tipo de **Serviço**. Além disso, ele deve ter um grupo de modelo de item que tenha a opção **Produto em estoque** na **Política de estoque** definida como **Sim**. Esta opção define se um produto é considerado como estoque no recebimento de produtos (**Produto em estoque** = **Sim**) ou se o produto é considerado em uma conta de lucros e perdas (**Produto estocado** = **Não**). Embora esse comportamento possa aparecer contraditório, ele tem como base o fato de que somente os produtos que tem esta política criarão as transações de estoque que podem ser usadas no controle de custo para calcular o custo planejado e para determinar o custo real quando uma ordem de produção é concluída.  

Para ser considerado no cálculo de planejamento e de custo, o serviço deve ser adicionado à BOM. A linha da BOM deve ser do tipo **Fornecedor** e deve ser alocada para a operação de rota à qual o serviço está alocado. Esta operação de roteiro deve ter o recurso de custos e recurso de requisito que aponta para um recurso do tipo **Fornecedor** que conecta a operação e o serviço relacionado à conta do fornecedor correspondente.  

Quando essa configuração é usada, uma ordem de compra é criada para o produto de serviço relacionado, com base na previsão da ordem de produção. A ordem de compra do serviço é usada como uma âncora para as operações subcontratadas. O trabalho subcontratado pode ser gerenciado através da página de listagem **Trabalho subcontratado** no controle de Produção. O trabalho subcontratado é usado para enviar matéria-prima e, eventualmente, um produto semiacabado ao fornecedor na preparação da operação. Ele também é usado para obter o produto resultante da operação subcontratada na entrada de item, em que o produto de serviço é usado para identificar a chegada do produto semiconcluído. Quando a linha de ordem de compra for recebida, a operação de produção será atualizada como concluída.  

Uma ordem de produção pode ter muitas operações, e cada operação pode ser alocada a um fornecedor diferente. Portanto, uma ordem de produção ponta a ponta pode disparar várias ordens de compra.

## <a name="subcontracting-of-production-flow-activities"></a>Subcontratação de atividades do fluxo de produção
A solução [lean manufacturing](lean-manufacturing-overview.md) modela o trabalho de subcontratação como um serviço que está relacionado a uma atividade de um [fluxo de produção](tasks/create-production-flow-version.md) (tópico do Guia de tarefas). Portanto, este tipo de subcontratação também é mencionado como [subcontratação baseada em atividade.](activity-based-subcontracting.md) Um tipo de grupo de custo especial, **Terceirização direta**, foi introduzido e os serviços de subcontratação não fazem parte da BOM de mercadorias acabadas. Quando você usa o lean manufacturing, todas as atividades são definidas pelos kanbans que podem ser relacionados a uma ou várias atividades do fluxo de produção. Até agora, essa explicação parece como uma explicação das ordens de produção. Entretanto, enquanto as ordens de produção devem sempre terminar com um produto acabado, você pode criar kanbans para fornecer um produto semiacabado. Você não precisa introduzir um novo produto e o nível de BOM.  

Como as regras kanban podem ser muito dinâmica, é possível modelar diferentes variantes de fornecimento para o mesmo produto em um fluxo de produção. Quando você usa a subcontratação de lean manufacturing, o fluxo material e o fluxo financeiro são separados restritamente. Todo o fluxo de material é representado por atividades kanban. As ordens de compra dos produtos de serviço e os lançamentos de recebimentos desses serviços podem ser automatizados com base no status de trabalhos kanban no fluxo de produção. Os trabalhos kanban podem ser iniciados e concluídos antes mesmo de as ordens de compra serem criadas. Os documentos da subcontratação (ordem de compra e recebimento de compra do serviço) podem ser agregados por período e por serviço. Portanto, o número de documentos e de linhas de compra pode ser mantido pequeno, mesmo em operações altamente repetitivas onde fornecedores fornecem serviços subcontratados em um fluxo único.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modelagem de subcontratação em um fluxo de produção

Em um [fluxo de produção de lean manufacturing](lean-manufacturing-modeling-lean-organization.md), uma atividade do processo pode ser definida como subcontratada quando é alocada para uma célula de trabalho (grupo de recursos) que tem um recurso de fornecedor único. Quando uma célula de trabalho é subcontratada, as atividades relacionadas ao processo devem estar vinculadas a uma linha de contrato de compra ativo que contém o item de serviço e o preço do serviço. O contrato de serviço da atividade também define a taxa de cálculo entre a quantidade do produto e o trabalho kanban e a quantidade resultante de serviço. Você pode selecionar se a quantidade de serviço será calculada com base no número de trabalho, na quantidade de bens que é informada nos trabalhos, ou na quantidade total do produto (essa quantidade total inclui produtos sucateados).  

Atividades de transferência também podem ser definidas como subcontratadas. Esta definição ocorre implicitamente quando você seleciona a pessoa responsável para o envio na atividade de transferência. Quando você marca **Expedidor** ou **Destinatário**, se o depósito de origem ou de destino correspondente for um depósito gerenciado por fornecedor, a atividade é considerada subcontratada. Quando você seleciona **Transportadora**, a atividade é sempre subcontratada. Como as atividades subcontratadas do processo, uma atividade de transferência subcontratada deve ser conectada a um contrato de serviço antes que o fluxo de produção possa ser ativado.

### <a name="backflush-costing"></a>Custos de fluxo inverso

A contabilização de custos do trabalho subcontratado está totalmente integrada na avaliação de custos para a solução de lean manufacturing (avaliação de custos de fluxo inverso). Quando o recebimento da ordem de compra de serviço for lançado, ou quando ocorrer faturamento, o custo de serviço é alocado ao fluxo de produção. Para avaliação de custos de fluxo inverso, a variação de serviços subcontratados é calculada para a compensação do bloco de subcontratação de custo padrão de produtos recebidos com as quantidades reais recebidas e faturadas de serviço.

## <a name="material-supply-for-subcontracted-operations"></a>Fornecimento de material para operações subcontratadas
Produtos semiacabados e outros materiais relacionados devem ser transferidos para a localização na qual os trabalhos são executados fisicamente. Quando você usa operações e atividades subcontratadas, essa transferência geralmente está relacionada com transporte adicional para um local operado pelo fornecedor. Alocando material na BOM para a operação subcontratada, você declara que o material deve ser preparado como o local de entrada do grupo de recursos do recurso alocado. O planejamento mestre ou o reabastecimento de lean manufacturing provisiona o material para esse local.  

Para modelo o estoque que está localizado no local do fornecedor, recomendamos definir um depósito gerenciado pelo fornecedor. É possível definir facilmente um depósito gerenciado pelo fornecedor criando um novo depósito e atribuindo à conta do fornecedor. Para documentar que o material deve ser transferido para o fornecedor antes que uma operação seja executada, aloque o depósito gerenciado pelo fornecedor para o depósito de entrada do grupo de recursos que retém o recurso.  

Para reabastecer o material nesse depósito, você pode usar várias estratégias:

-   Ordens de transferência
-   Transferir diários
-   Kanbans de retirada
-   Compra direta ao local do fornecedor

Os produtos semiacabados são exceção a esta regra. Para transferir bens semiacabados, você estará restrito a estas opções:

-   Para ordens de produção e de lote, os produtos semiacabados só podem ser transferidos logicamente usando o diário da lista de separação da página de listagem **Trabalho subcontratado**. Este diário criará um documento de nota de entrega que pode ser usado para transferir produto semiacabado e a matéria-prima ao fornecedor.
-   Para operações subcontratadas nos fluxos de produção, a transferência de produtos semiacabados está documentada pelo recebimento de kanbans de produção ou de retirada no local do fornecedor. Para modelar uma atividade explícita de transferência, você pode encerrar um kanban de produção em uma atividade de transferência adicional.

**Observação:** Um roteiro de produção de uma ordem de produção única não pode passar por vários sites. Essa regra também se aplica para trabalho subcontratado. Portanto, os depósitos que representam as localizações de materiais gerenciadas pelo fornecedor devem ser definidas no mesmo site como recursos internos usados no roteiro. Embora os fluxos de produção possam passar pelos sites, eles não podem transportar produtos semiacabados de um site para outro, porque essa operação implica em uma alteração do contexto do custo previsto.  

Normalmente, o depósito de saída e o local de um grupo de recursos subcontratado são alocados diretamente ao depósito e ao local da próxima etapa de operação no roteiro ou no fluxo de produção. Essa configuração ajuda a reduzir o valor do relatório de trabalho que ocorre ou o número de transferência adicionais que deve ser modelado.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]