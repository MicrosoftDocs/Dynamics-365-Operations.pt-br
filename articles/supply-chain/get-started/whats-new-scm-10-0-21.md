---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.21 (outubro de 2021)
description: Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Supply Chain Management 10.0.21.
author: kamaybac
ms.date: 10/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: cf38717ab3768249e3c9b988ee3893c5e539bcd0
ms.sourcegitcommit: 90ffd763d18f97654b9dbc9e3f71c998e6094c6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739377"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10021-october-2021"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.21 (outubro de 2021)

[!include [banner](../includes/banner.md)]

Este tópico lista os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management, versão 10.0.21. Esta versão tem um número de compilação de 10.0.960 e está disponível da seguinte maneira:

- **Versão preliminar de teste:** agosto de 2021
- **Disponibilidade geral da versão (atualização automática):** setembro de 2021
- **Disponibilidade geral da versão (atualização automática):** outubro de 2021

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. A coluna *Recurso* fornece links para o [plano de lançamento](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), no qual é possível ver as datas de lançamento oficiais de cada recurso. A coluna *Mais informações* fornece mais detalhes e/ou links para documentação relacionada.

A maioria desses recursos deve ser habilitada usando [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) antes que você possa usá-los.

| Área de recursos | Recurso | Mais informações |
|---|---|---|
| Estoque&nbsp;e&nbsp;logística | [A Contabilidade de estoque global é um suplemento para o Dynamics 365 Supply Chain Management](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Home page de Contabilidade de Estoque Global](../global-inventory-accounting/global-inventory-accounting-home.md) |
| Estoque&nbsp;e&nbsp;logística | [Ajustes de lançamento disponível usando códigos associados a contrapartidas](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [Exibir códigos de motivo de contagem de estoque](../warehousing/reason-codes-for-counting-journals.md) |
| Estoque&nbsp;e&nbsp;logística | [Política de exportação de dados referenciada de cotação de venda](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | Escolha se as alterações aos dados referenciados pelas cotações não farão com que essas cotações de venda relacionadas (ou linhas) sejam incluídas na próxima exportação incremental. As exportações incrementais serão executadas mais rapidamente se você optar por não incluir essas cotações ou linhas.<br><br>Este recurso adiciona uma configuração chamada **Ignorar dados de cotação de venda referenciados durante o controle de alterações** à página **Parâmetros de contas a receber**. |
| Estoque&nbsp;e&nbsp;logística | [Lances lacrados](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sealed-bidding) | [Lance selado para RFQs](../procurement/sealed-bidding.md) |
| Estoque&nbsp;e&nbsp;logística | [Reserva fácil para o Suplemento Visibilidade de Estoque](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/soft-reservation-inventory-visibility-add-in) | [Reservas de Visibilidade de Estoque](../inventory/inventory-visibility-reservations.md) |
| Estoque&nbsp;e&nbsp;logística | [Melhorias de dedução e de peso variável para gerenciamento de reembolsos](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [Gerenciar deduções usando a bancada de dedução](../rebate-management/deduction-workbench.md )<br><br>[Processar, revisar e lançar reembolsos](../rebate-management/process-review-post.md)<br><br>[Negociações de gerenciamento de reembolsos](../rebate-management/rebate-management-deals.md) |
| Estoque&nbsp;e&nbsp;logística | [Instruções da etapa do aplicativo de depósito](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Personalizar títulos e instruções de etapas para o aplicativo móvel Warehouse Management](../warehousing/mobile-app-titles-instructions.md) |
| Estoque&nbsp;e&nbsp;logística | [Intervalos de trabalho e acompanhamento de atualizações para custo Landed](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [Atualizar rastreamento a ser armazenado](../landed-cost/update-tracking-putaway.md )<br><br>[Processamento de mercadorias em trânsito](../landed-cost/in-transit-processing.md) |
| Planejamento Mestre | [Dias negativos para Otimização do Planejamento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [Tolerância a atraso (dias negativos)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um deles fornece uma melhoria incremental para um recurso existente. Por serem apenas melhorias, não estão listados no [plano de liberação](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária). Se você quiser usar qualquer um desses recursos, deve ativá-los explicitamente em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome&nbsp;do recurso&nbsp;no gerenciamento&nbsp;de recursos | Mais informações |
|---|---|---|
| Gerenciamento de custo | Detalhes do andamento de fechamento de estoque | Esta versão prévia do recurso habilita uma exibição detalhada do progresso de fechamento de estoque. |
| Compras | Impedir consumo excessivo de reservas de orçamento geral quando várias requisições de compra estão no fluxo de trabalho | Esse versão prévia do recurso melhora a verificação de erros quando os usuários enviam e aprovam requisições de compra que excedem o saldo restante de uma linha de reserva de orçamento geral. Isso ajuda a evitar o consumo em excesso de reservas de orçamento gerais quando várias requisições de compra estão no fluxo de trabalho. |
| Controle de produção | Mostrar números de série, de lote e da placa de licença completos na interface de execução da área de produção | Esse recurso oferece uma experiência melhor para exibir listas de números de placas de licença, de lote e de série na interface de execução de produção. A exibição é alterada de um modo de exibição de cartão com um número limitado de caracteres para um modo de exibição de lista que fornece espaço suficiente para mostrar os valores completos. A lista também oferece a capacidade de procurar números específicos. |
| Vendas e marketing | Limitar o número de ordens de venda que podem ser selecionadas para lançamento | Esse recurso permite definir o número máximo de solicitações de venda que podem ser selecionados ao postar confirmações, listas de separação, guias de remessa e faturas da página de lista de ordens de venda. Ele é habilitado automaticamente. O recurso adiciona uma configuração chamada **Número máx. de ordens de venda para postagem** à página **Parâmetros de contas a receber**. A nova configuração usa como padrão o valor *100*. O recurso ajuda a melhorar o desempenho da página de lista de ordens de venda quando um número substancial de ordens de venda é selecionado. Não tem impacto no número de ordens de venda que podem ser processadas por uma tarefa periódica. |
| Gerenciamento de depósito | Dissocie o trabalho de armazenamento de ASNs | Esse recurso é necessário para enviar e receber avisos de remessa antecipada (ASNs) quando você está executando uma carga de trabalho do gerenciamento de depósito em uma unidade de escala (como parte de uma topologia híbrida distribuída). Isso adiciona uma nova tabela de banco de dados dedicada ao armazenamento de informações sobre o trabalho de armazenamento. Anteriormente, essas informações eram armazenadas em tabelas que também são usadas para os ASNs. |
| Gerenciamento de depósito | Unidades mistas de slots | Permite que o sistema encaixe itens em locais que incluam unidades mistas (que incluem caixas e ocorrências). Para cada linha de modelo de encaixe, este recurso permite que você escolha se a linha deve encaixar itens em locais de unidade mista ou única. |
| Gerenciamento de depósito | Usar API mais rápida para fechamento/reabertura de contêineres na estação de embalagem | Quando esta versão prévia do recurso é habilitada, são criadas transações de estoque relacionadas a contêineres usando o novo e leve processo, que melhora o desempenho de fechamento ou de reabertura de contêineres durante o processamento manual da estação de embalagem. |

## <a name="features-turned-on-by-default-in-this-release"></a>Recursos ativados por padrão nesta versão

A tabela a seguir lista os recursos ativados por padrão na versão 10.0.21. A maioria dos recursos ativados atomicamente pode ser desativada no [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Nome do recurso | Habilitar data | Recurso adicionado em | Estado do recurso | Módulo |
| :--- | :--- | :--- | :--- | :--- |
| Armazenamento de relatório de estoque disponível | 01/09/2021 | 01/04/2020 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Cancelamento da ordem de transferência | 01/09/2021 | 13/07/2020 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Desbloquear Diário de Estoque | 01/09/2021 | 17/08/2020 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Exibições salvas do Gerenciamento de estoque | 01/09/2021 | 30/9/2020 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Navegação para a versão da BOM a partir de linhas da BOM | 01/09/2021 | 11/11/2019 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Usando unidade de medida e quantidade de unidades em diários de estoque | 01/09/2021 | 11/11/2019 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Permitir valores de atributos de lote vazios | 01/09/2021 | 11/11/2019 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Incrementar automaticamente os números de linha das linhas de ordens de transferência de estoque | 01/09/2021 | 11/10/2019 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Fluxo de trabalho de aprovação do diário de estoque | 01/09/2021 | 06/01/2020 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Habilitar o recurso de aviso de parâmetros de gerenciamento de qualidade de estoque | 01/09/2021 | 07/10/2019 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Criar ordem de transferência a partir da linha de venda | 01/09/2021 | 31/08/2019 | Ativado por padrão | Gerenciamento de estoque e depósito |
| Seleção de modelo de previsão nos detalhes de Previsão de demanda | 01/09/2021 | 11/10/2019 | Ativado por padrão | Planejamento Mestre |
| Visualização do progresso do planejamento mestre | 01/09/2021 | 07/10/2019 | Ativado por padrão | Planejamento Mestre |
| Confirmação automática da Otimização de Planejamento | 01/09/2021 | 11/10/2019 | Ativado por padrão | Planejamento Mestre |
| Confirmação paralela das ordens planejadas | 01/09/2021 | 31/08/2019 | Ativado por padrão | Planejamento Mestre |
| Mensagem de êxito de envio de lance | 01/09/2021 | 15/05/2019 | Ativado por padrão | Compras |
| Link de referência de RFQ adicionado à OC | 01/09/2021 | 31/08/2019 | Ativado por padrão | Compras |
| Capacidade de confirmar ordens de compra aceitas da colaboração do fornecedor em lote | 01/09/2021 | 10/09/2019 | Ativado por padrão | Compras |
| Aprimoramentos ao cXML de compra | 01/09/2021 | 11/11/2019 | Ativado por padrão | Compras |
| Exibir o link &quot;Abrir solicitações de cotação publicadas&quot; como um bloco | 01/09/2021 | 30/9/2020 | Ativado por padrão | Compras |
| Perguntas e respostas de RFQ | 01/09/2021 | 19/02/2020 | Ativado por padrão | Compras |
| Informações sobre produtos com materiais perigosos e documentação de remessa | 01/09/2021 | 14/06/2020 | Ativado por padrão | Gerenciamento de informações sobre o produto |
| Validação estrita em quantidades de ordem padrão | 01/09/2021 | 24/06/2020 | Ativado por padrão | Gerenciamento de informações sobre o produto |
| Recurso de gerenciamento de país de origem | 01/09/2021 | 13/07/2020 | Ativado por padrão | Gerenciamento de informações sobre o produto |
| Exibições salvas para produtos liberados | 01/09/2021 | 30/9/2020 | Ativado por padrão | Gerenciamento de informações sobre o produto |
| Aprimoramentos nas caixas de diálogo Aprovar e Transferir trabalhos | 01/09/2021 | 11/10/2019 | Ativado por padrão | Controle de produção |
| Placa de licença para relatório de conclusão adicionada ao Dispositivo de ficha de trabalho | 01/09/2021 | 31/08/2019 | Ativado por padrão | Controle de produção |
| Um novo botão Parar intervalo foi adicionado à página Terminal de Ficha de Trabalho | 01/09/2021 | 19/02/2020 | Ativado por padrão | Controle de produção |
| Habilite o recebimento parcial de itens subcontratados e corrija um problema com o cálculo de sucata das linhas de BOM do tipo Fornecedor. | 01/09/2021 | 11/11/2019 | Ativado por padrão | Controle de produção |
| Exibições salvas para controle de produção | 01/09/2021 | 17/08/2020 | Ativado por padrão | Controle de produção |
| Dynamics 365 Guides para Fabricação | 01/09/2021 | 13/07/2020 | Ativado por padrão | Controle de produção |
| Execução do piso de produção | 01/09/2021 | 30/9/2020 | Ativado por padrão | Controle de produção |
| Recurso para bloqueio de dispositivo de ficha de trabalho e terminal de ficha de trabalho para que eles possam ser limpos | 01/09/2021 | 10/05/2020 | Ativado por padrão | Controle de produção |
| Alocação de encargos em uma ordem de venda | 01/09/2021 | 30/9/2020 | Ativado por padrão | Vendas e marketing |
| Limitar o número de ordens de venda que podem ser selecionadas para lançamento | 01/09/2021 | 01/09/2021 | Ativado por padrão | Vendas e marketing |
| Limpar histórico de atualizações de ordens de venda | 01/09/2021 | 01/09/2021 | Ativado por padrão | Vendas e marketing |
| Alterar a sequência numérica do trabalho de contagem cíclica | 01/09/2021 | 07/10/2019 | Ativado por padrão | Gerenciamento de depósito |
| Reabastecimento de demanda de onda baseado em tarefa | 01/09/2021 | 07/10/2019 | Obrigatório | Gerenciamento de depósito |
| Ocultar o campo Valor Total nas páginas &quot;Todas as Cargas&quot; e &quot;Detalhes da Carga&quot; | 01/09/2021 | 07/10/2019 | Ativado por padrão | Gerenciamento de depósito |
| Impressão de etiqueta do ciclo | 01/09/2021 | 19/02/2020 | Obrigatório | Gerenciamento de depósito |
| Associar transações de estoque da ordem de compra com carga | 01/09/2021 | 06/01/2020 | Obrigatório | Gerenciamento de depósito |
| Layouts aprimorados da etiqueta da placa de licença | 01/09/2021 | 19/02/2020 | Ativado por padrão | Gerenciamento de depósito |
| Bloqueio de trabalho em toda a organização | 01/09/2021 | 19/02/2020 | Obrigatório | Gerenciamento de depósito |
| Detalhes da linha de trabalho | 01/09/2021 | 11/10/2019 | Ativado por padrão | Gerenciamento de depósito |
| Tornar editável o campo de status do estoque de movimento do dispositivo móvel | 01/09/2021 | 16/10/2019 | Ativado por padrão | Gerenciamento de depósito |
| Confirmar remessas de saída de trabalhos em lote | 01/09/2021 | 13/07/2020 | Ativado por padrão | Gerenciamento de depósito |
| Controlar se uma página de resumo do recebimento deve ser exibida em dispositivos móveis | 01/09/2021 | 01/04/2020 | Ativado por padrão | Gerenciamento de depósito |
| Aviso para resolver nomes ambíguos de &#39;Loc/LP&#39; | 01/09/2021 | 01/04/2020 | Ativado por padrão | Gerenciamento de depósito |
| Capturar grades de produtos e dimensões de rastreamento no aplicativo de depósito durante o recebimento do item de carga | 01/09/2021 | 10/05/2020 | Ativado por padrão | Gerenciamento de depósito |
| Não permita a criação de cargas que não atendam aos requisitos do modelo de criação de carga de onda. | 01/09/2021 | 17/08/2020 | Ativado por padrão | Gerenciamento de depósito |
| Avaliar todas as ações para diretivas de localização de várias SKUs | 01/09/2021 | 30/9/2020 | Ativado por padrão | Gerenciamento de depósito |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes tópicos de ajuda. Eles não estão necessariamente relacionados aos novos recursos adicionados para esta versão, conforme listado na seção anterior, mas podem ajudar você a obter mais dos recursos existentes.

| Área de recursos | Tópicos novos ou atualizados |
|---|---|
| Planejamento Mestre | [Previsões de estoque](../master-planning/inventory-forecast.md) |
| Planejamento Mestre | [Parâmetros não usados pela Otimização de Planejamento](../master-planning/planning-optimization/not-used-parameters.md) |
| Planejamento Mestre | [Métodos de reabastecimento e modificação de quantidade](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| Planejamento Mestre | [Agendamento com capacidade infinita](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Planejamento Mestre | [Exibir histórico e logs de planejamento](../master-planning/planning-optimization/plan-history-logs.md) |
| Gerenciamento de depósito | [Estratégias de embalagem do contêiner](../warehousing/container-packing-strategy-overview.md) |
| Gerenciamento de depósito | [Cenários de exemplo de contagem cíclica](../warehousing/cycle-counting-scenarios.md) |
| Gerenciamento de depósito | [Importar ASNs de entrada por meio da entidade de dados V3](../warehousing/import-asn-data-entity.md) |
| Gerenciamento de depósito | [Separação em excesso para ordens de venda e ordens de transferência](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| Gerenciamento de depósito | [Agendar impressão de etiqueta o ciclo durante o ciclo](../warehousing/configure-task-based-wave-label-printing.md) |
| Gerenciamento de depósito | [O que há de novo ou mudou no aplicativo móvel Warehouse Management](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.21 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.21 dos aplicativos de Finanças e Operações (outubro de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.21, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 e nuvens do setor: plano 2 do ciclo de lançamentos de 2021

Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira [Dynamics 365 e nuvens do setor: plano 2 do ciclo de lançamentos de 2021](/dynamics365-release-plan/2021wave2/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Recursos removidos e preteridos do Supply Chain Management

O tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descreve os recursos que foram ou serão removidos ou preteridos do Supply Chain Management.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes da remoção.

Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
