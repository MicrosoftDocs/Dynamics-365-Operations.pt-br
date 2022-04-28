---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.23 (janeiro de 2022)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.23.
author: kamaybac
ms.date: 10/15/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 876f5a5f8ebf77a65ba3aa6271a2957b7dc2cb96
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570468"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10023-january-2022"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.23 (janeiro de 2022)

[!include [banner](../includes/banner.md)]

Este tópico lista os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management, versão 10.0.23. Esta versão tem um número de compilação de 10.0.1037 e está disponível da seguinte maneira:

- **Versão preliminar:** outubro de 2021
- **Disponibilidade geral da versão (atualização automática):** dezembro de 2021
- **Disponibilidade geral da versão (atualização automática):** janeiro de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. A coluna *Recurso* fornece links para o [plano de lançamento](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), no qual é possível ver as datas de lançamento oficiais de cada recurso. A coluna *Mais informações* fornece mais detalhes e/ou links para documentação relacionada. Para determinar como ativar um recurso, consulte a coluna *Habilitado por*. Para obter mais informações sobre como usar o gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Podemos atualizar este tópico para incluir recursos inseridos no build após a publicação inicial deste tópico.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Catálogo de endereços global | Definir um estado/província padrão para cada país/região na configuração de endereço | Agora, você pode definir um estado/província padrão para cada país/região na configuração do endereço do catálogo de endereços global. Quando um estado/província padrão é definido, ele será o valor padrão inserido nos campos de estado/província quando você criar um novo registro de região ou município para esse país/região. Consulte também [Configuração de endereço](../../fin-ops-core/fin-ops/organization-administration/global-address-book-address-setup.md?toc=/dynamics365/supply-chain/toc.json) | Habilitado por padrão. |
| Estoque&nbsp;e&nbsp;logística | [Pausar tarefas no aplicativo móvel do Warehouse Management](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/park-tasks-warehouse-management-mobile-app) | [Configurar desvios para as etapas nos itens de menu do dispositivo móvel](../warehousing/warehouse-app-detours.md) | Gerenciamento de recursos (*Desvios do aplicativo do Warehouse Management*) |
| Estoque&nbsp;e&nbsp;logística | [Campos promovidos do aplicativo de depósito](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Configurar campos promovidos para as etapas no dispositivo móvel](../warehousing/warehouse-app-promoted-fields.md)| Gerenciamento de recursos (*campos promovidos do aplicativo do Warehouse*) |
| Fabricação | [Integração de sistemas de execução de fabricação](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-systems-integration) | [Integração com sistemas de execução de fabricação de terceiros](../production-control/mes-integration.md) | Gerenciamento de recursos (*Integração do sistema de execução de fabricação*) |
| Fabricação | [Relatório sobre coprodutos e subprodutos da interface de execução do piso de produção](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | [Como os trabalhadores usam a interface de execução de piso de produção](../production-control/production-floor-execution-use.md) | Gerenciamento de recursos (*Relatório sobre de coprodutos e subprodutos da interface de execução de produção*) |
| Planejamento | [Suporte à Otimização de Planejamento para o planejamento baseado em prioridade](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-priority-based-planning) | [Planejamento baseado em prioridade](../master-planning/planning-optimization/priority-based-planning.md) | Gerenciamento de recursos (*Suporte ao MRP baseado em prioridade para a Otimização de Planejamento*) |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos que são novos nesta versão. Cada um desses aprimoramentos fornece uma melhoria incremental para um recurso existente. Por serem apenas aprimoramentos, não estão listados no [plano de versão](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária).

Se você quiser ativar ou desativar qualquer um desses recursos, será necessário fazer isso no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), no qual eles são listados usando os nomes mostrados na coluna *Nome do recurso no gerenciamento de recursos* da tabela a seguir.

| Módulo | Nome do recurso no gerenciamento de recursos | Mais informações |
|---|---|---|
| Gerenciamento de ativos | Contrapartidas para despesas nos diários de ordem de serviço | Esse recurso permite especificar uma contrapartida para cada despesa listada em um diário de ordem de serviço. Geralmente, você pode associar uma conta de fornecedor a cada despesa, mas também há suporte para outros tipos de conta. Ele adiciona duas novas colunas (**Tipo de contrapartida** e **Contrapartida**) à Guia Rápida **Despesa** na página **Diário de ordem de serviço**.|
| Gerenciamento de custo | Criar comprovantes relacionados para reavaliações de arredondamento de custos padrão | <p>Quando um lançamento financeiro de estoque (como uma fatura de ordem de venda ou transação de estoque) é feito, esse recurso faz com que o sistema crie um comprovante separado para quaisquer reavaliações de arredondamento de custo padrão relacionadas e o anexa ao comprovante de lançamento financeiro como um comprovante relacionado.</p><p>Sem esse recurso, o sistema registra reavaliações de arredondamento de custo padrão no mesmo lançamento do comprovante. Esse comportamento às vezes pode causar informações conflitantes da data, porque as reavaliações usam a sessão ou a data do sistema, enquanto as postagens financeiras usam a data de lançamento.</p> |
| Gerenciamento de estoque e depósito | \[Rússia\] Lançar transações de estoque financeiro Storno de acordo com o sinalizador de correção no comprovante financeiro para ordens de venda | Esse recurso afeta a funcionalidade de correções de notas de crédito para a Rússia. Ele habilita o lançamento de transações de estoque para faturas de venda de acordo com a opção de correção na contabilidade. Quando esse recurso está habilitado, não há mais discrepâncias entre o sinalizador **Correção** no comprovante financeiro da transação de estoque e o sinalizador **Estorno** nas transações de estoque. |
| Gerenciamento de estoque e depósito | (Rússia) Fazer cálculo do relatório de giro de saldo de estoque em lote | Para localizações do Supply Chain Management na Rússia, este recurso oferece a possibilidade de executar o relatório *Giro de saldo de estoque* em lote, armazená-lo e exibir os relatórios gerados anteriormente. |
| Gerenciamento de estoque e depósito | (Rússia) Usar traduções para idioma local nos principais formulários específicos de um país ou região no Gerenciamento de estoque | Para as localizações do Supply Chain Management na Rússia, este recurso permite o uso de traduções em russo de nomes de produto/item e unidades de medida nas seguintes impressões de estoque específicas da Rússia: Lista de contagem (INV-3), Lista de contagem (INV-5) e Lista de contagem (INV-6). |
| Planejamento Mestre | Serviço do Azure Machine Learning para previsão de demanda. | Esse recurso permite que o Serviço do Azure Machine Learning gere previsões de demanda com base em dados históricos. Para obter mais informações, consulte [Configuração da previsão de demanda](../master-planning/demand-forecasting-setup.md). |
| Compras | Limpar histórico de atualizações de ordens de compra | Esse recurso permite que você limpe registros históricos temporários relacionados a atualizações de ordens de compra. Ele adiciona um novo botão chamado **Limpar histórico de atualização de compra** ao Painel de Ações na página **Todas as ordens de compra**. Esse recurso é habilitado por padrão. |
| Controle de produção | (Versão preliminar) Separação automática de materiais habilitados de depósito para listas de separação lançadas automaticamente | Este recurso permite que você separe automaticamente e resolva dimensões de estoque para diários de lista de separação derivados e de fluxo inverso lançados automaticamente. |
| Controle de produção | Validar vencimento de matérias-primas em relação à data de consumo planejada | Este recurso altera como as datas de vencimento do lote são validadas ao reservar um lote de matéria-prima a ser usada durante a produção. Quando este recurso estiver habilitado, a data de vencimento do lote será validada em relação à data de consumo planejada (a data da matéria-prima), conforme estabelecida na linha da BOM de produção ou na linha da fórmula da ordem de lote. Quando esse recurso estiver desabilitado, a data de vencimento do lote será validada em relação à data de entrega planejada da ordem de produção ou de lote (como anteriormente). |
| Vendas e marketing | Limpar histórico de atualizações de vendas com base na idade | Esse recurso permite definir a idade máxima dos registros a serem mantidos durante a execução da tarefa periódica **Limpeza do histórico de atualizações de vendas**. Os registros mais antigos serão excluídos. Isso é útil quando você define que a tarefa seja executada periodicamente porque a idade é sempre calculada em relação à data em que a tarefa é executada. Sem esse recurso, você só pode definir uma data específica para que os registros mais antigos sejam mantidos. Para obter mais informações, consulte [Agendar limpeza de dados de histórico de vendas](../sales-marketing/sales-update-history-cleanup-performance-improvements.md). |
| Vendas e marketing | Melhorar o desempenho do relatório dos "100 melhores" clientes | Esse recurso melhora o desempenho do relatório dos **100 principais** clientes executando sempre o relatório em todos os clientes (o que é o uso pretendido) em vez de permitir consultas personalizadas. Quando esse recurso estiver habilitado, todas as configurações **Registros para inclusão** estarão desabilitadas no diálogo do relatório **100 principais**. |
| Gerenciamento de depósito | Suporte à unidade de escala para liberação para de ordens de saída para o depósito | Quando esse recurso estiver habilitado, as ordens de saída poderão ser liberadas do hub diretamente para a unidade de escala, de onde as ordens serão atendidas. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes tópicos de ajuda. Esses tópicos não estão necessariamente relacionados aos novos recursos que foram adicionados a essa versão, conforme listado na seção anterior. No entanto, eles podem ajudar você a aproveitar mais os recursos existentes.

| Área de recursos | Tópicos novos ou atualizados |
|---|---|
| Gerenciamento de alteração de engenharia | Agora, [Atributos de engenharia e pesquisa de atributos de engenharia](../engineering-change-management/engineering-attributes-and-search.md) descreve o funcionamento da herança de atributos de engenharia. |
| Planejamento Mestre | Agora, [Planejamento mestre com previsões de demanda](../master-planning/planning-optimization/demand-forecast.md) e [Chaves de redução de previsão](../master-planning/reduction-keys.md) fornecem mais informações sobre como trabalhar com chaves de redução. |
| Planejamento Mestre | Agora, [Cumprimento de estoque de segurança para itens](../master-planning/safety-stock-replenishment.md) fornece mais informações sobre como usar chaves de mínimo/máximo. |
| Planejamento Mestre | Agora, [Previsões de estoque](../master-planning/inventory-forecast.md) fornecem mais informações sobre a alocação de previsões. |
| Planejamento Mestre | [Plano de fornecimento](../master-planning/supply-schedule.md) |
| Gerenciamento de depósito | [Parâmetros de dispositivo móvel global](../warehousing/mobile-device-parameters.md) |
| Gerenciamento de depósito | [Ancoragem](../warehousing/anchoring.md) |
| Vendas e marketing | Agora, o comércio intercompanhia é descrito em detalhes, iniciando com a [Configuração de comércio intercompanhia](../sales-marketing/intercompany-trade-set-up.md) e os tópicos relacionados. |
| Gerenciamento de estoque | A documentação sobre Visibilidade de Estoque foi expandida e atualizada, começando pela [visão geral do suplemento Visibilidade do Estoque](../inventory/inventory-visibility.md) e os tópicos relacionados. |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.23 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.23 dos aplicativos Finanças e operações (novembro de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-23.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.23, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=627874&dbType=3&qc=9b7e01944eb8b43f9c3aac4be26811c27be205847d6d2a240424f34f7e722910).

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
