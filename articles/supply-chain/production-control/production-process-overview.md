---
title: Visão geral do processo de produção
description: Este tópico fornece uma visão geral dos processos de produção. Ele descreve as várias fases de ordens de produção, de ordens de lotes e de kanbans, desde a criação da ordem até o fechamento do período financeiro.
author: cvocph
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, Kanban, ProdTable, ProdTableOverview, EcoResProductDiscreteManufacturingWorkspace, KanbanPrepareProductForLeanWorkspace, EcoResProductProcessManufacturingWorkspace, OpResLifecycleManagementWorkspace, ProdParmCostEstimation, ProdParmRelease, ProdSchedule, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19832"
- intro-internal
ms.assetid: 0e83c7ea-feba-4ed6-8717-8b48a3b8804a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42a71d9f8a7229b147d5e322456c44c4d0d7b7f7303d8b13946eed7e68c75343
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776839"
---
# <a name="production-process-overview"></a>Visão geral do processo de produção

[!include [banner](../includes/banner.md)]

Este tópico fornece uma visão geral dos processos de produção. Ele descreve as várias fases de ordens de produção, de ordens de lotes e de kanbans, desde a criação da ordem até o fechamento do período financeiro. 

A produção de produtos, um processo que também é conhecido como o ciclo de vida de produção, segue etapas específicas necessárias para concluir a fabricação de um item. O ciclo de vida começa com a criação da ordem de produção, da ordem de lote ou do kanban. Termina com um item fabricado, acabado, pronto para o cliente ou para outra fase da produção. Cada etapa do ciclo de vida exige diferentes tipos de informações para executar o processo. Conforme cada etapa é concluída, a ordem de produção, ordem de lote ou kanban mostra uma alteração no status da produção. Diferentes tipos de produtos processos exigem processos de fabricação diferentes.  

O módulo **Controle de produção** está vinculado a outros módulos, como **Gerenciamento de informações do produto**, **Gerenciamento de estoque**, **Contabilidade**, **Gerenciamento de depósito**, **Contabilidade de projetos** e **Administração da organização**. Essa integração oferece suporte ao fluxo de informações necessário para concluir a fabricação de um item acabado.  

O processo de produção é normalmente influenciado pelos métodos de avaliação de contabilização de custos e de estoque que são escolhidos para um processo de produção específico. O Supply Chain Management oferece suporte aos custos reais (primeiro a entrar, primeiro a sair \[PEPS\]; último a entrar, primeiro a sair \[UEPS\]; média de movimentos; e média ponderada e periódica) e aos métodos de custo padrão. O lean manufacturing é implementado com base no princípio de custos de fluxo inverso.  

A opção dos métodos de medição de custo também define os requisitos de relatórios sobre o material e o consumo de recursos durante o processo de produção. Normalmente, os métodos de custo reais exigem relatório correto no nível do trabalho, enquanto os métodos de custo periódico permitem o relatório menos granular do material e do consumo de recursos.

## <a name="mixed-mode-manufacturing"></a>Fabricação de modo misto
Diferentes produtos e topologias de produção exigem a utilização de diferentes tipos de ordem. O Supply Chain Management pode aplicar vários tipos de ordem em um modo misto. Em outras palavras, todos os tipos de ordem podem ocorrer durante o processo completo de produção de um produto finalizado.

-   **Ordem de produção** – Este é o tipo de ordem clássico para produzir um produto específico ou variante do produto em uma determinada quantidade, em uma data específica. As ordens de produção são baseadas em listas de materiais (BOMs) e roteiros.
-   **Ordem de lote** – Este tipo de ordem é usado para processar processos discretos e das indústrias nos quais a conversão de fabricação é baseada em uma fórmula, ou quando coprodutos e subprodutos podem ser produtos finais, além ou em vez do produto principal. As ordens de lote usam tipos de BOMs e de roteiros da **Fórmula**.
-   **Kanban** – Os kanbans são usados para sinalizar processos de lean manufacturing repetitivos que são baseados em fluxos de produção, em regras kanban e nas BOMs.
-   **Projeto** – Um projeto de fabricação combina produtos e serviços com programação e orçamento específicos. A parte de fabricação de um projeto pode ser entregue através de qualquer um dos outros tipos de ordem.

## <a name="manufacturing-principles"></a>Princípios de fabricação
Para selecionar o princípio de fabricação que se aplica melhor a um produto específico e um mercado relacionado, considere os requisitos de produção e de logística, e também as expectativas do cliente sobre prazos de entrega.

-   **Fabricação para armazenamento** – Este é o princípio clássico de fabricação, no qual os produtos são gerados para o estoque, com base no reabastecimento de previsão ou de estoque mínimo (o último normalmente é calculado com base na previsão ou no consumo histórico).
-   **Fabricação por encomenda** – Os produtos padrão são fabricação por encomenda ou acabamento por encomenda. Embora a pré-produção possa ser feita usando o princípio Fabricação para armazenamento, as etapas caras da cadeia de valores, ou as etapas que criam variantes, são disparadas por uma ordem de venda ou uma ordem de transferência.
-   **Configurado conforme o pedido** – Assim como para o princípio Fabricação por encomenda, as operações finais da cadeia de valores são fabricação por encomenda. A variante do produto real que é gerada não é predefinida, mas é criada no momento da entrada de ordem, com base no módulo de configuração do produto de vendas. O princípio Configurado conforme o pedido exige um certo nível de unificação do processo para uma determinada linha de produtos.
-   **Projeto sob encomenda** – Os processos Projeto sob encomenda geralmente são tratados por um projeto e começam com a fase de engenharia. Durante a fase de engenharia, os produtos reais que são necessários para atender o pedido são criados e descritos. As ordens de produção, as ordens de lote, ou os kanbans podem ser criados para produzir os produtos.

## <a name="overview-of-the-production-life-cycle"></a>Visão geral do ciclo de vida de produção
As etapas a seguir no ciclo de vida de produção podem ocorrer para todos os tipos de ordem de fabricação de modo misto. No entanto, nem todos são representados como um status da ordem explícito.

1.  **Criado** – Você pode criar uma ordem de produção, uma ordem de lote, ou um kanban manualmente, ou você pode configurar o sistema para gerá-los com base em vários sinais de demanda. O planejamento mestre cria ordens de produção, ordens de lote ou kanbans através da confirmação ordens planejadas. Outros sinais de demanda são ordens de venda ou sinais de fornecimento vinculado de outras ordens de produção ou kanbans. Para kanbans de quantidade fixa, os sinais de demanda são gerados quando os kanbans são registrados como vazios.
2.  **Estimado** – Você pode calcular previsões para o consumo de material e recursos. A estimativa gera transações de estoque para as matérias-primas que têm um status **Em ordem**. Os recebimentos de produtos, coprodutos e subprodutos principais são gerados quando as ordens de produção ou as ordens de lote são estimadas. Se a BOM contiver as linhas do tipo **Fornecimento vinculado**, ordens de compra para materiais ou serviços de operação subcontratados são geradas e vinculadas à ordem de produção ou ordem de lote. Os itens ou as ordens são reservados de acordo com a estratégia de reserva da ordem de produção, e o preço dos produtos concluídos é calculado com base nas configurações de parâmetro.
3.  **Agendado** – Você pode agendar a produção com base em operações, trabalhos individuais ou ambos.
    -   **Plano de operações** – Este método de planejamento fornece um plano aproximado de longo prazo. Usando este método, você pode atribuir datas inicial e final às ordens de produção. Se as ordens de produção estiverem anexadas a operações de roteiro, será possível atribuí-las a grupos de centros de custo.
    -   **Planejamento de trabalho** – Este método de planejamento fornece um plano detalhado. Cada operação é dividida em trabalhos individuais com datas, horas específicas e recursos de operações atribuídos. Se a capacidade finita for usada, os trabalhos serão atribuídos a recursos de operações com base em disponibilidade. Você pode exibir e alterar o plano em um gráfico de Gantt.
    -   **Programação de kanban** – Os trabalhos kanban são agendados no quadro de agenda kanban ou planejados automaticamente com base na configuração de planejamento automático das regras kanban.

4.  **Liberado** – Você pode liberar a ordem de produção ou a ordem de lotes quando a agenda estiver concluída e o material estiver disponível para ser separado ou preparado. A verificação de disponibilidade de material ajuda o supervisor do chão de fábrica a avaliar a disponibilidade do material para ordens de produção ou ordens de lote. Também é possível imprimir documentos de ordem de produção, como listas de separação, ficha de trabalho, cartão de roteiro e roteiro de trabalho. Quando a ordem de produção é liberada, o status da ordem muda para indicar que a produção pode ser iniciada. Quando o gerenciamento de depósito é usado, a versão da ordem de produção ou da ordem de lote libera as linhas da BOM de produção no gerenciamento de depósito. As ondas de depósito e o trabalho de depósito são gerados, de acordo com a configuração do depósito.
5.  **Preparados**/**Separados**– Quando todos os materiais e recursos estiverem preparados no local de produção, as linhas da BOM de produção ou as linhas do kanban serão atualizadas para **Separados**. As ordens de fornecimento vinculado e o trabalho do depósito relacionado geralmente são concluídos neste estágio. Os cartões kanban ou fichas de trabalho necessários para relatar o andamento da produção devem ser atribuídos e impressos.
6.  **Iniciado** – Quando uma ordem de produção, uma ordem de lote, ou um kanban é iniciado, você pode relatar o consumo de materiais e de recursos em relação à ordem. O sistema pode ser configurado para lançar automaticamente o consumo de material e de recursos que são alocados para a ordem quando esta for iniciada. Essa alocação é conhecida como pré-liberação, liberação antecipada ou autoconsumo. Você pode alocar manualmente materiais para ordens de produção ou ordens de lote criando diários de lista de separação adicionais. Também é possível alocar manualmente mão-de-obra e outros custos de roteiro para a ordem. Se você estiver usando o agendamento de operações, poderá alocar esses custos criando um diário de cartões de roteiro. Se você estiver usando o agendamento de trabalhos, poderá alocar os custos criando um diário de ficha de trabalho. As ordens de produção ou as ordens de lote podem ser iniciadas em lotes da quantidade final solicitada. Em uma ordem de produção, uma ordem de lote ou um kanban, os trabalhos que são criados podem ser iniciados e relatados separadamente nos diários, do terminal da execução de fabricação (terminal MES), ou dos quadros kanban.
7.  Trabalhos em andamento **Concluído** do relatório – Use o Terminal MES, os diários de produção, os quadros kanban, móveis ou os recursos de verificação móveis para relatar o andamento da produção por trabalho ou por recurso. O consumo de materiais e recursos será lançado, e os status dos kanban, ordens de produção, e ordens de lote relacionados pode ser atualizados para **Recebido** ou **Informado como concluído**. O trabalho de armazenamento para o depósito pode ser criado, dependendo da configuração do depósito.
8.  **Informado como concluído** (o recebimento de produtos) – Quando uma ordem de produção ou uma ordem de lote é relatada como concluída, a quantidade de bens acabados que foram concluídos é atualizada no estoque. Essa quantidade inclui a quantidade de coprodutos e subprodutos relevantes. Se estiver usando contabilidade WIP (trabalho em andamento), um diário-razão será gerado para reduzir as contas WIP e aumentar o estoque dos bens acabados. Quando o custo de uma ordem de produção é calculado, o custo real da produção é lançado. Se os custos de material e mão-de-obra associados a uma produção ainda não estiverem alocados em um diário ou por pré-liberação, eles poderão ser alocados automaticamente por baixa de estoque. A alocação com de baixa de estoque envolve a pós-dedução dos processos de transação de estoque. Se a ordem de produção estiver concluída, marque a caixa de seleção **Trabalho final** para alterar o status restante para **Concluído**. Caso contrário, deixe o campo em branco para permitir o relatório de quantidades adicionais geradas.
9.  **Avaliação de qualidade** – Um recebimento de produtos pode acionar a criação de ordens de qualidade, dependendo da configuração dos processos de teste e das regras de qualidade que são estabelecidas para produtos específicos. Como uma ordem de qualidade pode atualizar o status de estoque ou os atributos do lote dos produtos testados, a avaliação de qualidade é um processo obrigatório em várias indústrias.
10. **Armazenar** e **Remeter a ordem** – Após a avaliação de recebimento de produtos e de qualidade, o trabalho opcional de armazenamento direciona os produtos recebidos para o próximo ponto de consumo, depósito de bens acabados ou para uma zona de remessa, se houver requisitos de remeter a ordem.
11. **Concluído** – Antes de encerrar a produção, os custos reais serão calculados para a quantidade que foi produzida. Todos os custos previstos de material, mão-de-obra e custos gerais indiretos são revertidos e substituídos por custos reais. Se você marcar a caixa de seleção **Concluído** ao executar o cálculo de custos, o status da ordem de produção mudará para **Trabalho final**. Esse status evita que custos adicionais sejam lançados em uma ordem de produção concluída.
12. **Fechamento do período** – Alguns princípios de contabilização de custos, como a média periódica, custos de fluxo inverso, PEPS ou UEPS, exigem atividades periódicas para fechar o estoque ou o período financeiro. Normalmente, o sistema tenta informar todo consumo de materiais e recursos, e também as correções de estoque e sucata, antes dos períodos serem fechados. Este relatório normalmente é feito usando diários de movimentos de estoque ou diários de ajuste. A meta é avaliar o desempenho econômico de unidades operacionais por período. Em alguns casos, quando são usadas ordens de produção de execução longa que se estendem pelos períodos de relatórios financeiros, os diários de produção são usados para informar o andamento da produção e o consumo de recursos até o fim do período.


## <a name="additional-resources"></a>Recursos adicionais

[​Comentários da produção​](production-feedback.md)

[Visão geral dos modelos de configuração de produto](../pim/product-configuration-models.md)

[​Visão geral de lean manufacturing​](lean-manufacturing-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]