---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.27 (julho de 2022)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.27.
author: kamaybac
ms.date: 04/22/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: a50fcbe313901beab610400d8c59dd375f1af93e
ms.sourcegitcommit: d770f0e6a012675a3027641704be804beb99754b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2022
ms.locfileid: "9022611"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10027-july-2022"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.27 (julho de 2022)

[!include [banner](../includes/banner.md)]

Este artigo lista os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management, versão 10.0.27. Esta versão tem um número de compilação 10.0.1227 e está disponível na seguinte agenda:

- **Versão preliminar:** abril de 2022
- **Disponibilidade geral da versão (autoatualização):** junho de 2022
- **Disponibilidade geral da versão (atualização automática):** julho de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este artigo para incluir recursos que foram adicionados à compilação após a publicação inicial deste artigo.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Estoque e logística | [Alocação de estoque para o suplemento de visibilidade de estoque](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-allocation-inventory-visibility-add-in) | [Alocação de estoque de visibilidade do estoque](../inventory/inventory-visibility-allocation.md) | Habilitado por padrão |
| Fabricação | Exibição "Meu dia" da interface de execução de piso de produção | [Como os trabalhadores usam a interface de execução de piso de produção](../production-control/production-floor-execution-use.md) e [Mostrar saldos de férias na interface de execução de piso de produção](../production-control/production-floor-execution-payroll-stats.md) | Gerenciamento de recursos:<br>*Exibição "Meu dia" da interface de execução de piso de produção* |
| Planejamento | [Suporte para otimização de planejamento de subcontratação](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-subcontracting) | [Gerenciar trabalhos de subcontratação na produção](../production-control/manage-subcontract-work-production.md) | Habilitado por padrão |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um desses aprimoramentos fornece uma melhoria incremental para um recurso existente. Por serem apenas aprimoramentos, não estão listados no [plano de versão](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária).

Se quiser ativar ou desativar qualquer um desses recursos, você deverá fazer isso em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome do recurso no gerenciamento de recursos | Mais informações |
|---|---|---|
| Planejamento Mestre | Considerar o prazo de entrega do estoque ao criar uma ordem de transferência planejada | Quando uma ordem de transferência planejada é criada, esse recurso faz com que o sistema considere o prazo de entrega do estoque especificado nas configurações de ordem padrão do item ao calcular a data de recebimento da ordem de transferência planejada para a configuração do controle de data de entrega como prazo de entrega do tipo *Nenhum* ou *Vendas*. Quando o prazo de entrega da transferência for especificado, seu valor será usado para o cálculo da data de recebimento e os dias de transporte serão ignorados. |
| Compras | Informações de imposto do contrato do agente padrão nas linhas de fatura de fornecedor | Esse recurso introduz a lógica para definir valores padrão para os campos **Impostos** e **Imposto do item** nas linhas de fatura de fornecedor do contrato do agente. Essa lógica é aplicada somente quando o tipo de encargo na linha de contrato de agente é razão/razão. O grupo de impostos do item usará seu valor padrão da categoria de compras de corretagem (se estiver configurado) ou do tipo de encargo. O grupo de impostos pegará seu valor padrão da conta do fornecedor. |
| Compras | Limitar o número de linhas de ordem de compra por tarefa em lote | Esse recurso ajuda você a otimizar o desempenho do sistema quando são lançadas confirmações e recebimentos de produtos. Ele adiciona uma nova configuração chamada **Linhas por tarefa** à guia **Entrega** da página **Parâmetros de compras**. Essa nova configuração permite que você limite o número de linhas da ordem de compra processadas em cada tarefa em lotes. Portanto, ela pode ajudar a impedir que grandes tarefas em lote deixem o sistema lento. |
| Gerenciamento de informações sobre o produto | Preencher valores de atributo de produto | Esse recurso adiciona uma tarefa periódica chamada *Preencher valores de atributo de produto*. Essa nova tarefa periódica criar os registros de valor de atributo de produto ausentes para os atributos associados aos produtos por meio de uma categoria de produto. |
| Controle de produção | Configuração adicional na interface de execução de piso de produção | <p>Esse recurso adiciona as seguintes opções à página **Configurar execução de piso de produção**:</p><ul><li>**Abrir automaticamente a caixa de diálogo inicial ao preencher a pesquisa** – quando essa opção está habilitada, a caixa de diálogo **Iniciar trabalho** é automaticamente aberta quando os trabalhadores usam a barra de pesquisa para encontrar o trabalho.</li><li>**Abrir automaticamente a caixa de diálogo de andamento do relatório ao preencher a pesquisa** – quando essa opção está habilitada, a caixa de diálogo **Progresso do relatório** para o trabalho é automaticamente aberta quando os trabalhadores usam a barra de pesquisa para encontrar o trabalho.</li><li>**Quantidade restante padrão na caixa de diálogo de andamento do relatório** – quando essa opção está habilitada, a caixa de diálogo **Progresso do relatório** mostra a quantidade restante a ser reportada em um trabalho de produção.</li></ul><p>Para obter mais informações, consulte [Configurar a interface de execução de piso de produção](../production-control/production-floor-execution-configure.md).</p> |
| Controle de produção | Equipes de produção na interface de execução de piso de produção | <p>Quando vários trabalhadores são atribuídos ao mesmo trabalho de produção, agora eles podem indicar um trabalhador como coordenador. Os trabalhadores restantes se tornarão automaticamente assistentes desse coordenador. Para a equipe resultante, somente o coordenador deve registrar o status do trabalho, enquanto os registros de hora se aplicam a todos os membros da equipe. Esse recurso também oferece suporte a um cenário chamado *Auxiliar recurso*. Neste cenário, um trabalhador pode registrar-se como um assistente de outro trabalhador, que se tornará o coordenador do grupo recém-formado.</p><p>Para obter mais informações, consulte [Como os trabalhadores usam a interface de execução de piso de produção](../production-control/production-floor-execution-use.md).</p> |
| Controle de produção | Relatório sobre itens de planejamento na interface de execução de piso de produção | Esse recurso simplifica o processo de relatório das ordens de lote para itens de planejamento na interface de execução de piso de produção. Quando uma ordem de lote é criada para um produto que tenha um tipo de produção de *Item de planejamento*, o relatório de conclusão pode ser feito somente nos coprodutos e subprodutos dessa ordem de lote. As ordens de lote para itens de planejamento são normalmente usadas para oferecer suporte a processos de desmembramento, em que um produto de matéria-prima é desmembrado em vários produtos distintos. Quando um trabalhador relata uma ordem de lote para um item de planejamento como concluída, a caixa de diálogo **Progresso do relatório** exibirá somente os coprodutos e subprodutos. Anteriormente, ela também exibia o item de planejamento, e esse comportamento podia confundir os trabalhadores. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes artigos de ajuda: Esses artigos não estão necessariamente relacionados aos novos recursos que foram adicionados a essa versão, conforme listado em seções anteriores. No entanto, eles podem ajudar você a aproveitar mais os recursos existentes.

| Área de recursos | Artigos novos ou atualizados |
|---|---|
| Gerenciamento de custo | [Data da média ponderada com Incluir valor físico e marcação](../cost-management/weighted-average-date.md) |
| Topologia híbrida distribuída | [Experimentar unidades de escala em uma topologia híbrida distribuída](../cloud-edge/cloud-edge-try-out.md) |
| Gravação dupla | [Sincronizar sob demanda com o mecanismo de preços do Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/pricing-engine.md) |
| Gerenciamento de depósito | [Liberar para o depósito](../warehousing/release-to-warehouse-process.md) |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.27 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.27 de aplicativos de finanças e operações (Junho de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-27.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.27, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=673271).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 e nuvens do setor: plano 1 do ciclo de lançamentos de 2022

Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira [Dynamics 365 e nuvens do setor: plano 1 do ciclo de lançamentos de 2022](/dynamics365-release-plan/2022wave1/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Recursos removidos e preteridos do Supply Chain Management

O artigo [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descreve os recursos que foram ou serão removidos ou preteridos do Supply Chain Management.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no artigo [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes da remoção.

Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
