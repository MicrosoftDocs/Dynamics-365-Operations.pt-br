---
title: "Gerenciar trabalhos de produção na subcontratação"
description: "Este tópico explica como operações subcontratadas são gerenciadas no Microsoft Dynamics 365 para as operações. Ou seja explica como as operações de produção que são atribuídas a um recurso são gerenciadas por um fornecedor."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 79430358bebd93fd96f1169d22737d3537dbfc08
ms.lasthandoff: 03/31/2017


---

# <a name="manage-subcontracting-work-in-production"></a>Gerenciar trabalhos de produção na subcontratação

Este tópico explica como operações subcontratadas são gerenciadas no Microsoft Dynamics 365 para as operações. Ou seja explica como as operações de produção que são atribuídas a um recurso são gerenciadas por um fornecedor.

Em [processos de produção (production-process-overview.md]), os trabalhos podem ser feitas pelos recursos que são ou lucros administrados por fornecedores. Normalmente, os recursos de fornecedor são usadas para nivelar a demanda adicional ultrapassa periódica que a capacidade disponível recursos próprios da empresa. O fornecedor pode também poder oferecer o [] recursos específicos do recurso (resource-capabilities.md) ou recursos ao preço mais baixo.  

Dependendo dos recursos de fornecedor usada em um processo de produção, o [] (roteiro) routes-operations.md geralmente tem requisitos logísticos adicionais, porque o material e os produtos devem primeiro semiconcluídos serem efetuados para o local do fornecedor. O resultado de subcontratada operação deve ser enviado qualquer um local que recebe a próxima operação ou um depósito preenchido de mercadorias.  

A subcontratar operações ou as atividades são usadas, que afetam todos os estágios de operações, a definição das operações necessárias na produção, em custos, a previsão, planejamento em, e programar, o gerenciamento de logística para materiais, produtos semiconcluídos e, de mercadorias concluídas. Finalmente, esses recursos costumam seus próprios processos para contabilidade e controle de custo.  

Para recursos internos, uma taxa de custo fixo é normalmente atribuído por um período. Em contraste, os custos de recursos subcontratados com base no preço de compra de serviço relacionada. O serviço é definido como um, e outros produtos usado para levar a aquisição e comprar processos para uma operação subcontratada fornecida.  

Atualmente, não haverá conceito explícito semiconcluídos de produtos no Microsoft Dynamics 365 para as operações. Para uma ordem de produção que exija mais de uma operação para transformar matérias-primas uma mercadoria concluída, o item concluído é lançado de volta ao estoque apenas na última operação. Produtos semiconcluídos que o produto anterior de operações é contabilizado em trabalho em andamento (WIP), mas não lançadas ou não são rastreados em estoque. Embora você pode dividir os roteiros e listas de materiais (BOMs) em várias unidades menores, nos aumentos essa abordagem o número de produtos, em, BOMs e roteiros a serem gerenciadas.  

Há dois métodos para modelagem subcontratação de trabalho para operações de produção. Esses métodos diferentes na forma como o processo a subcontratação puder ser modelado, na forma como os produtos semiconcluídos representados no processo, e a maneira que o controle de custos será gerenciada.

-   Subcontratação de operações de roteiro em ordens de produção ou ordens de lote
    -   Os produtos de serviço deverão ser um produto do estoque, e seja parte da BOM.
    -   Este método oferece suporte primeiro a entrar, primeiro a sair (FIFO) ou custo padrão.
    -   Produtos semiconcluídos são representados por produto de serviço em processo.
    -   O controle de custos atribuídos os custos associados com os trabalhos para subcontratados custo materiais.
-   Subcontratação de atividades do fluxo de produção de um fluxo de produção magro
    -   O serviço é um produto de serviço de não em estoque, não faz parte da BOM.
    -   Este método usa contratos de compra como contratos de serviço.
    -   Este método usa custos de fluxo inverso.
    -   Este método permite a aquisição e assíncrona agregada. (O fluxo material independe do processo de compras.)
    -   O controle de custos atribuídos trabalho subcontratados em seu próprio bloco de divisão de custo previsto.

## <a name="subcontracting-of-route-operations"></a>Subcontratação de operações de roteiro
Para usar a subcontratação de operações de roteiro para a produção ou de lotes os produtos, ordens de serviço que são usados para compras de serviço devem ser definidos como um produto ** serviço ** tipo. Adicionalmente, devem ter um grupo modelo de item tenha ** produtos do estoque ** opção do conjunto abaixo ** diretiva de estoque ** ** Sim **. Essa opção define se um produto são explicados como o estoque no recebimento de produtos (** produtos do estoque ** = ** Sim **), ou se o produto expensed em uma conta de lucros e perdas (** produtos do estoque ** ** ** = nenhum). Embora esse comportamento possa aparecer contraditório tem, com base no fato que somente os produtos que tiverem esta política criarão as transações de estoque que podem ser usadas no controle de custo para calcular os custos planejados e para determinar os custos reais quando uma ordem de produção é concluído.  

Para ser considerado no cálculo de planejamento e de custo, serviço deve ser adicionado à BOM. A linha da BOM deve ser do tipo fornecedor ** ** e, deve-se atribuir a operação do roteiro que o serviço será atribuída. Esta operação de roteiro deve ter o recurso de custos e recurso de requisito que aponta para um recurso de ** fornecedor ** digite que conecta a operação relacionada e serviço correspondente na conta de fornecedor.  

Quando essa configuração é usada, ordem de compra será criada para o produto de serviço relacionados, com base na previsão da ordem de produção. Ordem de compra de serviço é usado como âncora subcontratadas para as operações. Os trabalhos subcontratados podem ser gerenciadas através ** trabalho subcontratados ** página de listagem no controle de produção. Os trabalhos subcontratados são usados para enviar a matéria-prima e, eventualmente, produto semiconcluídos ao fornecedor à vista da operação. Também são usados para obter os produtos resultantes de operação subcontratada na entrada de item, em que o produto de serviço são usados para identificar a chegada semiconcluídos de produto. Quando a linha de ordem de compra for recebida, a operação de produção é atualizada como concluídas.  

Uma ordem de produção pode ter muitas operações, e cada operação pode ser atribuída a um fornecedor diferente. Portanto, uma ordem de produção ponta a ponta pode disparar mais ordens de compra.

## <a name="subcontracting-of-production-flow-activities"></a>Subcontratação de atividades do fluxo de produção
[Lean manufacturing]) (lean-manufacturing-overview.md a solução modela subcontratação de trabalho como um serviço relacionada a uma atividade do fluxo de produção [] (http://ax.help.dynamics.com/en/wiki/create-a-production-flow-version/) (tópico de guia de tarefa). Assim, esse tipo de subcontratação também é referido como atividade- baseada subcontratação []. (activity-based-subcontracting.md) Um tipo de custo previsto do grupo especial, ** terceirização direta **, foi introduzido, e serviços a subcontratação não são parte da BOM de OS bens concluídos. Quando você usa o lean manufacturing, todas as atividades serão definidas pelos kanban que podem ser relacionados a uma ou várias atividades do fluxo de produção. Até essa soa explicação, assim como uma explicação das ordens de produção. Entretanto, enquanto que as ordens de produção devem terminar com sempre um produto acabado, você pode criar kanban forneça um produto semiconcluídos. Você não precisa introduzir um novo produto e o nível de BOM.  

Como as regras kanban podem ser muito dinâmico, será possível modelar diferentes grades de fonte para os mesmos produto em um fluxo de produção. Quando você usa a subcontratação magra, fluxo material e o fluxo financeiro estão separados restritamente. Qualquer fluxo material são representadas por atividades do kanban. Ordens de compra para o produto de serviço e as postagens de recebimento dos serviços automatizados podem ser, com base no status dos trabalhos kanban o fluxo de produção. Os trabalhos kanban podem ser iniciados e concluída antes mesmo que as ordens de compra sejam criados. Os documentos da subcontratação (recebimento de ordem de compra e de compra de serviço) podem ser agregados por período e pelo serviço. Portanto, o número de documentos e de linhas de compra pode ser mantido pequeno, mesmo em operações repetitivas altamente onde fornecedores fornecem subcontratados serviços em um fluxo de uma única peça.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Subcontratação de modelagem em um fluxo de produção

Em [fluxo de produção magro (lean-manufacturing-modeling-lean-organization.md]), a atividade de processo pode ser definida conforme quando subcontratada atribuídos a uma célula de trabalho (grupo de recursos que possui) um único recurso de fornecedor. Quando uma célula de trabalho é subcontratada, as atividades relacionadas de processo devem estar vinculadas a um ativo linha de contrato de compra que contém o item de serviço e o preço de serviço. O contrato de serviço de atividades também define a taxa de cálculo entre a quantidade de bens dos trabalhos kanban e o valor resultante de serviço. Você pode selecionar se a quantidade de serviço será calculada com base no número de trabalho, a quantidade de bens que é informada no trabalho, ou da quantidade total de produto (essa quantidade total inclui sucateados produto).  

Atividades de transferência podem ser definidas como subcontratadas. Esta definição implicitamente ocorre quando você selecionar a pessoa responsável para o envio na atividade de transferência. _Quando você marca ** remetente ** ou ** destinatário **, correspondente origem ou de destino depósito ficar fornecedor- gerenciar um depósito, subcontratar atividade ser consideradas. Quando você selecionar transportadora ** **, a atividade será subcontratada sempre. Atividades subcontratadas como de processo, uma atividade de subcontratada transferência devem ser conectados a um contrato de serviço antes que o fluxo de produção pode ser ativado.

### <a name="backflush-costing"></a>Custos de fluxo inverso

A contabilização de custo previsto de trabalho subcontratados é totalmente integrada em custos para a solução de fabricação tendenciosa (custos de fluxo inverso). Quando o recebimento de ordem de compra de serviço for lançada, ou quando ocorre faturamento, os custos de serviço são atribuídos ao fluxo de produção. Para custos de fluxo inverso, variações de serviços subcontratados é calculada para a compensação do bloco subcontratação de custo padrão de bens recebidos com as quantidades recebidas e faturadas reais de serviço.

## <a name="material-supply-for-subcontracted-operations"></a>Fonte material subcontratadas para operações
Produtos semiconcluídos e outros materiais relacionados devem ser transferidos a localização onde os trabalhos são executados fisicamente. Quando você usa operações e atividades subcontratadas, essa transferência está relacionada com freqüência em transportar adicional a um site de operada. Atribuindo o material EM a BOM, a operação subcontratada você declara que o material deve ser preparado local de entrada do grupo de recursos para o recurso atribuído. O planejamento mestre ou o magro reabastecimento provisionam o material nesse local.  

Modelagem do estoque que está localizado no site do fornecedor, é uma prática recomendada na indústria de definir um depósito fornecedor- gerenciado. Facilite definir um depósito fornecedor- gerenciado criando um novo depósito e à conta de fornecedor. Para documentar que o material deve ser transferido para o fornecedor antes que uma operação seja executada, atribua o depósito fornecedor- gerenciado o depósito de entrada do grupo de recursos que retém o recurso.  

Para reabastecer o material nesse depósito, você pode usar várias estratégias:

-   Ordens de transferência
-   Transferir diários
-   Kanban de saída
-   Direcionar a compra ao local do fornecedor

Os produtos forem semiconcluídos a exceção a ela. Para transferir bens semiconcluídos, você estará restrito a estas opções:

-   Para ordens de produção e de lote, os produtos semiconcluídos só podem ser transferidos logicamente usando o diário de lista de separação ** trabalho subcontratados ** página de listagem. Este diário cria um documento de nota de entrega que pode ser usado para transferir semiconcluído e a matéria-prima ao fornecedor.
-   Para operações subcontratadas os fluxos de produção, a transferência do produto está documentada semiconcluídos pelo recebimento de kanban de saída ou de produção local do fornecedor. Modelagem para uma atividade explícita de transferência, você pode encerrar um kanban de produção em uma atividade de transferência adicional.

** Observação: ** Um roteiro de uma única ordem de produção não pode a vários sites. Essa regra também se aplica para subcontratados trabalho. Portanto, os depósitos que representam as localizações materiais fornecedor- gerenciadas devem ser definidos no mesmo site que recursos internos usados no roteiro. Embora os fluxos de produção podem a sites, não pode transportar semiconcluídos produtos de um site para outro, porque essa operação implica uma alteração do contexto de custo previsto.  

Normalmente, o depósito de saída e a localização de um grupo de recursos subcontratado atribuídos diretamente ao depósito e o local da próxima etapa de operação no roteiro ou no fluxo de produção. Essa configuração ajudar a reduzir o valor do relatório que ocorre de trabalho ou operações de transferência adicionais numérica que deve ser modelado.


