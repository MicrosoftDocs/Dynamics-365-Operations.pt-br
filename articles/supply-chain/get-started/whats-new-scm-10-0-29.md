---
title: 'Versão preliminar do Dynamics 365 Supply Chain Management 10.0.29: (October 2022)'
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.29.
author: kamaybac
ms.date: 08/12/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d95cd9b55f473bed2e3fe69e63837040385f03ac
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334735"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10029-october-2022"></a>Versão preliminar do Dynamics 365 Supply Chain Management 10.0.29: (October 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo lista recursos novos ou alterados na versão preliminar do Microsoft Dynamics 365 Supply Chain Management 10.0.29. Esta versão tem um número de compilação 10.0.1326 e está disponível na seguinte agenda:

- **Versão preliminar de teste:** agosto de 2022
- **Disponibilidade geral da versão (atualização automática):** setembro de 2022
- **Disponibilidade geral da versão (atualização automática):** outubro de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este artigo para incluir recursos que foram adicionados à compilação após a publicação inicial deste artigo.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Estoque e logística | [Alocar e reservar itens de WMS na visibilidade de estoque](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/allocate-reserve-whs-items-inventory-visibility) | Em breve | Habilitado por padrão |
| Estoque e logística | [Pré-carregar listas de estoque disponível otimizadas](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/query-inventory-visibility-summary-entity) | Em breve | Habilitado por padrão |
| Automação de fornecimento sob encomenda | [Automação de fornecimento sob encomenda](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-to-order-supply-automation) | [Automação de fornecimento sob encomenda](../master-planning/make-to-order-supply-automation.md) | Gerenciamento de recursos:<br>*Automação de fornecimento sob encomenda* |
| Planejamento | [Exibir e aplicar informações detalhadas para DDMRP](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/view-apply-detailed-insights-ddmrp) | [Visão geral do Planejamento de Requisitos de Material Orientado por Demanda](../master-planning/planning-optimization/ddmrp-overview.md) | Gerenciamento de recursos:<br>*(Versão preliminar) DDMRP para Otimização de Planejamento* |
| Controle de produção | [Disponibilizar fisicamente as mercadorias acabadas antes de lançá-las em diários](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-finished-goods-physically-before-posting) | [Disponibilizar fisicamente as mercadorias acabadas antes de lançá-las em diários](../production-control/deferred-posting.md) | Gerenciamento de recursos:<br>*(Versão preliminar) Disponibilizar fisicamente as mercadorias concluídas antes de lançá-las nos diários* |
| Gerenciamento de depósito | [Pesquisar dados relevantes no warehouse mobile app](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/look-up-relevant-data-within-warehouse-mobile-app) | [Consultar dados usando desvios do aplicativo móvel do Warehouse Management](../warehousing/warehouse-app-data-inquiry.md) | Gerenciamento de recursos:<br>*Fluxo de consulta de dados do aplicativo Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um desses aprimoramentos fornece uma melhoria incremental para um recurso existente. Por serem apenas aprimoramentos, não estão listados no [plano de versão](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária).

Se quiser ativar ou desativar qualquer um desses recursos, você deverá fazer isso em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome do recurso no gerenciamento de recursos | Mais informações |
|---|---|---|
| Gerenciamento de custo | Otimização do cálculo de preço pendente do coproduto | Esse recurso corrige um conflito que às vezes pode ocorrer quando os preços de coprodutos são calculados usando vários threads. Ele faz com que o sistema verifique se cada preço de coproduto é calculado apenas uma vez. O resultado desse cálculo é usado como a entrada para todos os outros cálculos. Se já existir um preço pendente, esse preço será usado. |
| Planejamento Mestre | Transações de grupo em Otimização do Planejamento | Esse recurso pode ajudar a reduzir o número de ordens planejadas que são geradas para fornecer uma única linha de ordem de venda quando você estiver usando a Otimização do Planejamento. Quando esse recurso está ativado, a Otimização do Planejamento agrupará todas as transações de estoque de uma linha da ordem em um único requisito para a quantidade total. (Esse comportamento corresponde ao comportamento interno do mecanismo de planejamento.) O fornecimento e a demanda são agrupados separadamente. Portanto, o recurso ajuda a reduzir o volume da transação quando você tem transações divididas e quando usa dimensões (como números de lote ou números de série) que não são dimensões de cobertura. |
| Compras | Colocar fornecedor em espera para ordens de compra | Esse recurso permite colocar um fornecedor em espera para ordens de compra. Ele adiciona um novo tipo de retenção de *Ordem de compra* que marca um fornecedor como em espera para ordens de compra. Você não poderá criar novas ordens de compra para fornecedores que estão em espera para ordens de compra, mas ainda poderá continuar com qualquer fatura ou pagamento em aberto para esses fornecedores. |
| Vendas e marketing | Calcular valor líquido de linha mediante importação | Esse recurso permite controlar se o sistema deve recalcular totais de linha ao importar dados pela entidade *Linhas da ordem de venda*, *Linhas de cotação de venda* ou *Linhas da ordem de devolução* usando OData ou gravação dupla. Ele somente entra em vigor quando você também tiver políticas de avaliação do contrato comercial que restrinjam alterações ao campo **Valor líquido** para linhas da ordem de venda, linhas da cotação de venda e/ou linhas da ordem de devolução. Ele adiciona uma configuração chamada **Calcular valor líquido de linha** à página **Contas a receber > Configuração > Parâmetros de contas a receber**. Quando essa configuração é definida como *Sim*, o sistema sempre recalculará os valores da linha quando necessário (ignorando assim qualquer diretiva de avaliação do contrato comercial para o valor líquido da linha). Quando a configuração for definida como *Não*, o sistema nunca calculará automaticamente o valor líquido da linha, mesmo quando as alterações de entrada no preço da linha, na quantidade e/ou no desconto informarem que o valor líquido da linha deve ser recalculado. Este recurso é habilitado por padrão e define **Calcular valor líquido de linha** como *Sim*. A configuração *Não* corresponde ao comportamento do sistema antes da versão 10.0.23 e é fornecida principalmente para dar suporte a cenários de integração herdados.<br><br>Para obter mais informações, consulte [Recalcular valores líquidos de linha ao importar ordens de venda, cotações e devoluções](../sales-marketing/calc-line-net-amounts-import.md). |
| Vendas e marketing | Calcular totais de vendas usando vários threads | Esse recurso ajuda a melhorar o desempenho habilitando o sistema a usar o processamento paralelo ao calcular totais de vendas em um lote. O recurso adiciona um novo campo **Número de threads** à caixa de diálogo **Calcular totais de vendas**. Se você optar por executar o cálculo em um lote, poderá usar este campo para definir o número máximo de threads. Se você definir o valor como *0* (zero) ou *1*, um único thread será usado. Os valores acima de 1 habilitam multithreading. |
| Vendas e marketing | Atualizar os preços e descontos inseridos manualmente para intercompanhia | Este recurso adiciona suporte para políticas de alteração manual para ordens intercompanhia. Ele inclui suporte para transferir políticas de alteração manual entre ordens de compra e de venda intercompanhia. Anteriormente, só havia suporte para políticas de alteração manual em ordens de não-intercompanhia. Quando este recurso é habilitado, o sistema oferece a opção de atualizar preços e descontos depois que você salva as alterações em uma ordem intercompanhia. Esta opção permite que você escolha se deseja aplicar os novos preços e os detalhes dos descontos à ordem Intercompanhia ou deixar a ordem inalterada. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes artigos de ajuda: Esses artigos não estão necessariamente relacionados aos novos recursos que foram adicionados a essa versão, conforme listado em seções anteriores. No entanto, eles podem ajudar você a aproveitar mais os recursos existentes.

| Área de recursos | Artigos novos ou atualizados |
|---|---|
| Planejamento mestre, CTP | [Calcular datas de entrega da ordem de venda usando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md) |
| Planejamento mestre, DDMRP | [Visão geral do Planejamento de Requisitos de Material Orientado por Demanda](../master-planning/planning-optimization/ddmrp-overview.md)<br>[Ativar o recurso de DDMRP para seu sistema](../master-planning/planning-optimization/ddmrp-enable.md)<br>[Posicionamento de estoque](../master-planning/planning-optimization/ddmrp-inventory-positioning.md)<br>[Perfil e níveis de buffer](../master-planning/planning-optimization/ddmrp-buffer-profile-and-levels.md)<br>[Planejamento orientado por demanda](../master-planning/planning-optimization/ddmrp-planning.md)<br>[Execução visual e colaborativa](../master-planning/planning-optimization/ddmrp-visual-and-collaborative-execution.md) |
| Gerenciamento de depósito | [Embalar contêineres para remessa](../warehousing/packing-containers.md)<br>[Trabalho de embalagem para empacotar contêineres de saída e processar remessas](../warehousing/packing-work.md) |

## <a name="feature-state-changes-in-this-release"></a>Alterações do estado do recurso nesta versão

A tabela a seguir lista os recursos que se tornaram obrigatórios ou ativados por padrão na versão 10.0.29. Todos esses recursos serão automaticamente ativados para o seu sistema assim que você atualizar para a versão 10.0.29. Não é possível desativar os recursos obrigatórios, mas os recursos ativados por padrão ainda podem ser desativados usando o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

A tabela também lista recursos que anteriormente estavam na versão preliminar pública, mas que foram alterados para se tornarem disponíveis na versão 10.0.29. Essa alteração indica que agora os recursos são recomendados para uso em ambientes de produção. Esses recursos são desativados por padrão, salvo indicação em contrário. Portanto, você deve usar o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativá-los, caso queira usá-los.

| Módulo | Nome do recurso | Novo estado do recurso |
| --- | --- | --- |
| Gerenciamento de ativos | [Funcionalidade de gerenciamento de ativos para a interface de execução de piso de produção](../production-control/production-floor-execution-configure.md) | Obrigatório |
| Gerenciamento de custo | [Alterar o rótulo de cancelamento no fechamento e o ajuste para Reverter](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/change-terminology-inventory-closing-cancellation-inventory-closing-reverse) | Obrigatório |
| Gerenciamento de custo | Limpar versões de avaliações de custos cruzadas dos detalhes de cálculo da BOM | Obrigatório |
| Gerenciamento de custo | [Armazenamento de comparação de preços de item](../cost-management/compare-item-price.md) | Obrigatório |
| Gerenciamento de custo | [Nível de cálculo de custo](../cost-management/cost-calculation-level.md) | Ativado por padrão |
| Gerenciamento de custo | Habilitar a configuração do número de lote definida pelo usuário para estorno do fechamento de estoque | Ativado por padrão |
| Gerenciamento de custo | [Detalhes do andamento de fechamento de estoque](whats-new-scm-10-0-21.md) | Ativado por padrão |
| Gerenciamento de custo | [Armazenamento de relatórios de valor de estoque](../cost-management/inventory-value-report-storage.md) | Obrigatório |
| Gerenciamento de custo | Limpeza de dados do relatório de valor de estoque | Obrigatório |
| Gerenciamento de custo | Sequência de custos de fallback, média móvel | Obrigatório |
| Gerenciamento de custo | Mostrar log de fechamento/recálculo de estoque na grade | Obrigatório |
| Gerenciamento de custo | Mostrar os itens com transações que não estão totalmente liquidadas no formato de resumo | Obrigatório |
| Gerenciamento de estoque e depósito | Permitir valores de atributos de lote vazios | Obrigatório |
| Gerenciamento de estoque e depósito | Incrementar automaticamente os números de linha das linhas de ordens de transferência de estoque | Obrigatório |
| Gerenciamento de estoque e depósito | Criar ordem de transferência a partir da linha de venda | Obrigatório |
| Gerenciamento de estoque e depósito | Desabilitar campo de linha do diário de estoque no fluxo de trabalho | Obrigatório |
| Gerenciamento de estoque e depósito | Habilitar o recurso de aviso de parâmetros de gerenciamento de qualidade de estoque | Obrigatório |
| Gerenciamento de estoque e depósito | (China) Excluir do custo médio mensal os custos de recebimento e envio físico | Ativado por padrão |
| Gerenciamento de estoque e depósito | [Fluxo de trabalho de aprovação do diário de estoque](../inventory/inventory-journal-workflow.md) | Obrigatório |
| Gerenciamento de estoque e depósito | [Armazenamento de relatório de estoque disponível](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/inventory-on-hand-report-storage) | Obrigatório |
| Gerenciamento de estoque e depósito | [Exibições salvas do gerenciamento de estoque](saved-views-scm.md) | Obrigatório |
| Gerenciamento de estoque e depósito | Cancelamento da ordem de transferência | Obrigatório |
| Gerenciamento de estoque e depósito | Usando unidade de medida e quantidade de unidades em diários de estoque | Obrigatório |
| Gerenciamento de estoque e depósito | Desbloquear diário de estoque | Obrigatório |
| Fabricação | [Separação automática de materiais habilitados de depósito para listas de separação lançadas automaticamente](whats-new-scm-10-0-23.md) | Geralmente disponível |
| Fabricação | Habilitar a exibição de dimensões de estoque na lista de materiais para operações de roteiro de produção | Obrigatório |
| Fabricação | [Habilite para inserir números de lote e de série ao relatar como concluído no Dispositivo de Ficha de Trabalho](../production-control/report-finished-job-device.md) | Ativado por padrão |
| Fabricação | Separação aprimorada da quantidade do peso variável da produção | Ativado por padrão |
| Fabricação | [Pesquisa de trabalho para a interface de execução do piso de produção](../production-control/production-floor-execution-configure.md) | Obrigatório |
| Fabricação | [Integração do sistema de execução de manufatura](../production-control/mes-integration.md) | Ativado por padrão |
| Fabricação | [Exibição "Meu dia" da interface de execução de piso de produção](../production-control/production-floor-execution-configure.md) | Ativado por padrão |
| Fabricação | [Verificação de disponibilidade de material sob demanda para ordens de produção](whats-new-scm-10-0-24.md) | Ativado por padrão |
| Fabricação | [Substituir reserva de produção padrão](../production-control/override-default-reservation-principle.md) | Obrigatório |
| Fabricação | [Registrar consumo de material na interface de execução do piso de produção (não WMS)](../production-control/production-floor-execution-configure.md) | Geralmente disponível |
| Fabricação | [Relatório de itens de peso variável da interface de execução do piso de produção](../production-control/production-floor-execution-configure.md) | Geralmente disponível |
| Fabricação | [Relatório sobre coprodutos e subprodutos da interface de execução do piso de produção](../production-control/production-floor-execution-configure.md) | Ativado por padrão |
| Fabricação | [Relatório sobre itens de planejamento na interface de execução de piso de produção](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | Ativado por padrão |
| Fabricação | [Exibições salvas para controle de produção](saved-views-scm.md) | Obrigatório |
| Fabricação | [Mostrar números de série, de lote e da placa de licença completos na interface de execução da área de produção](../production-control/production-floor-execution-configure.md) | Obrigatório |
| Fabricação | [Validar vencimento de matérias-primas em relação à data de consumo planejada](whats-new-scm-10-0-23.md) | Ativado por padrão |
| Planejamento Mestre | [Confirmação automática da Otimização de Planejamento](../master-planning/planning-optimization/planned-order-firming.md) | Obrigatório |
| Planejamento Mestre | [Consolidação executável em lote e consolidação para ordens planejadas em massa e em lote](whats-new-scm-10-0-20.md) | Ativado por padrão |
| Planejamento Mestre | [Incluir itens com disponibilidade quando os filtros de pré-processamento estiverem habilitados](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/master-planning-include-items-on-hand-when-pre-processing-filters-are-enabled) | Ativado por padrão |
| Planejamento Mestre | [Agendamento da capacidade infinita para a Otimização do Planejamento](../master-planning/planning-optimization/infinite-capacity-planning.md) | Ativado por padrão |
| Planejamento Mestre | [Margens para Otimização de planejamento](../master-planning/planning-optimization/safety-margins.md) | Obrigatório |
| Planejamento Mestre | [Dias negativos para Otimização do Planejamento](../master-planning/planning-optimization/delay-tolerance.md) | Obrigatório |
| Planejamento Mestre | [Autorização paralela da previsão de demanda ajustada](whats-new-scm-10-0-20.md) | Obrigatório |
| Planejamento Mestre | [Confirmação de ordem planejada com filtros](../master-planning/planning-optimization/planned-order-firming.md) | Obrigatório |
| Planejamento Mestre | [Ordens de produção planejada para Otimização de Planejamento](../master-planning/planning-optimization/production-planning.md) | Obrigatório |
| Planejamento Mestre | [Contratos comerciais de compra para Otimização de Planejamento](../master-planning/planning-optimization/purchase-trade-agreement.md) | Obrigatório |
| Planejamento Mestre | [Exibições salvas para ordens planejadas](saved-views-scm.md) | Obrigatório |
| Compras | Encargos de valores de/até em ordens de compra | Obrigatório |
| Compras | Desabilitar botão de redefinição de distribuição de requisição de compra | Ativado por padrão |
| Compras | [Habilitar redefinição de fluxos de trabalho relacionados a compras](whats-new-scm-10-0-20.md) | Ativado por padrão |
| Compras | [Limitar o número de linhas de ordem de compra por tarefa em lote](whats-new-scm-10-0-27.md) | Ativado por padrão |
| Compras | [Mesclar as dimensões financeiras do fornecedor com a dimensão financeira do link de dimensão ativo na ordem de compra](whats-new-scm-10-0-25.md) | Obrigatório |
| Compras | [Lançar quantidades registradas de produtos em estoque e restantes de produtos sem estoque para recebimentos e faturas de fornecedor](whats-new-scm-10-0-26.md) | Geralmente disponível |
| Compras | [Impedir consumo excessivo de reservas de orçamento geral quando várias requisições de compra estão no fluxo de trabalho](whats-new-scm-10-0-21.md) | Ativado por padrão |
| Compras | [Participante responsável pelo Contrato de compra](../procurement/purchase-agreements.md) | Obrigatório |
| Compras | [Exibições salvas para ordens de compra](saved-views-scm.md) | Obrigatório |
| Gerenciamento de informações sobre o produto | Pré-processamento do relatório de lista de materiais para evitar tempo de inatividade | Obrigatório |
| Gerenciamento de informações sobre o produto | Dimensões financeiras padrão separadamente ao usar modelos de item | Obrigatório |
| Gerenciamento de informações sobre o produto | Habilitar grupos de dimensão do produto para modelos de item | Obrigatório |
| Gerenciamento de informações sobre o produto | Aprimoramentos de entidade item – código de barras | Obrigatório |
| Gerenciamento de informações sobre o produto | Regenerar nomes de grade de produto com base em nomenclatura | Obrigatório |
| Gerenciamento de informações sobre o produto | [Exibições salvas para produtos liberados](saved-views-scm.md) | Obrigatório |
| Gerenciamento de informações sobre o produto | [Aprimoramentos na página de sugestões de grade](../pim/tasks/create-predefined-product-variants.md) | Obrigatório |
| Vendas e marketing | [Alocação de encargos em uma ordem de venda](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/miscellaneous-charges-enhancements) | Obrigatório |
| Vendas e marketing | Limpar histórico de atualizações de ordens de venda | Obrigatório |
| Vendas e marketing | [Limpar histórico de atualizações de vendas com base na idade](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) | Obrigatório |
| Vendas e marketing | [Otimização de exportação de entidade de dados da pessoa de contato](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Obrigatório |
| Vendas e marketing | Copiar grupo de descontos totais para nota de crédito de venda | Obrigatório |
| Vendas e marketing | [Habilitar a busca para os campos de introdução do documento de cotação de venda e de conclusão do documento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Obrigatório |
| Vendas e marketing | [Melhorar o desempenho do relatório dos "100 melhores" clientes](whats-new-scm-10-0-23.md) | Obrigatório |
| Vendas e marketing | Incluir registros em espera nas tarefas de limpeza do histórico | Obrigatório |
| Vendas e marketing | Limitar o número de linhas de ordem de venda por tarefa em lote | Ativado por padrão |
| Vendas e marketing | [Limitar o número de ordens de venda que podem ser selecionadas para lançamento](whats-new-scm-10-0-21.md) | Obrigatório |
| Vendas e marketing | Recalcular saldo estimado do cliente | Obrigatório |
| Vendas e marketing | [Registro de linha da ordem de devolução de venda com precisão decimal com e sem peso variável](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Obrigatório |
| Vendas e marketing | [Exibições salvas para vendas e marketing](saved-views-scm.md) | Obrigatório |
| Vendas e marketing | [Confirmação de ordem de venda com um único clique](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/single-click-sales-order-confirmation) | Obrigatório |
| Gerenciamento de transporte | Permitir a não correspondência de guias de frete em linhas de fatura de frete sem um diário de fatura de fornecedor lançado | Ativado por padrão |
| Gerenciamento de transporte | [Habilitar a criação de um diário de faturas de fornecedor ao descartar uma nota de frete](whats-new-scm-10-0-20.md) | Ativado por padrão |
| Gerenciamento de transporte | [Remessa de mercadorias pequenas](../warehousing/small-parcel-shipping.md) | Obrigatório |
| Gerenciamento de transporte | [Certificação do USMCA do documento de origem](../transportation/usmca-certification-of-origin.md) | Ativado por padrão |
| Gerenciamento de depósito | [Zona de localização adicional](../warehousing/additional-location-zones.md) | Obrigatório |
| Gerenciamento de depósito | [Cancelar trabalho](../warehousing/cancel-warehouse-work.md) | Obrigatório |
| Gerenciamento de depósito | [Consolidar remessa](../warehousing/configure-shipment-consolidation-policies.md) | Obrigatório |
| Gerenciamento de depósito | [Criar e processar ordens de transferência do aplicativo de depósito](../warehousing/create-transfer-order-from-warehouse-app.md) | Obrigatório |
| Gerenciamento de depósito | Modelos de distribuição integrada com diretivas de localização | Ativado por padrão |
| Gerenciamento de depósito | [Dissocie o trabalho de armazenamento de ASNs](whats-new-scm-10-0-21.md) | Obrigatório |
| Gerenciamento de depósito | [Operações put diferidas](../warehousing/deferred-processing-manual-inventory-movement.md) | Obrigatório |
| Gerenciamento de depósito | Operação Put diferida - contêiner | Ativado por padrão |
| Gerenciamento de depósito | Processamento PUT adiado – habilitado para o recurso de modelo de auditoria com o evento de gatilho definido como Anterior | Obrigatório |
| Gerenciamento de depósito | [Desabilitar os recebimentos esperados das ordens de qualidade que bloquearam o estoque de exemplo](../inventory/inventory-blocking.md) | Ativado por padrão |
| Gerenciamento de depósito | Habilitar a validação rápida para dispositivos móveis de depósito | Obrigatório |
| Gerenciamento de depósito | [Analisador aprimorado de códigos de barra GS1](../warehousing/gs1-barcodes.md) | Geralmente disponível |
| Gerenciamento de depósito | [Reserva flexível da placa de licença comprometida na ordem](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obrigatório |
| Gerenciamento de depósito | [Reserva flexível de dimensão em nível de depósito](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obrigatório |
| Gerenciamento de depósito | [Utilização do local de consolidação do item](../warehousing/item-consolidation-location-utilization.md) | Ativado por padrão |
| Gerenciamento de depósito | Histórico de recebimentos da placa de licença | Ativado por padrão |
| Gerenciamento de depósito | [Consolidação da remessa manual](../warehousing/consolidate-shipments-manual-workbench.md) | Ativado por padrão |
| Gerenciamento de depósito | [Serviço de separação manual de linha de transferência para administradores ou usuários confiáveis semelhantes](whats-new-scm-10-0-28.md) | Geralmente disponível |
| Gerenciamento de depósito | [Interface de equipamento de manuseio de materiais](../warehousing/mhax.md) | Obrigatório |
| Gerenciamento de depósito | [Novas páginas da bancada de planejamento de carga](whats-new-scm-10-0-24.md) | Geralmente disponível |
| Gerenciamento de depósito | [Visualização da carga de trabalho de saída](../warehousing/outbound-workload-visualization.md) | Obrigatório |
| Gerenciamento de depósito | [Distribuição integrada planejada](../warehousing/planned-cross-docking.md) | Obrigatório |
| Gerenciamento de depósito | [Processar eventos do aplicativo de depósito](../warehousing/warehouse-app-events.md) | Obrigatório |
| Gerenciamento de depósito | Aprimoramento da consulta para o modelo de trabalho de armazenamento de coproduto e subproduto | Obrigatório |
| Gerenciamento de depósito | [Arredondar quantidades para baixo para a unidade de vendas mais próxima na liberação para o depósito](whats-new-scm-10-0-19.md) | Obrigatório |
| Gerenciamento de depósito | [Exibição salva da bancada de planejamento da carga](saved-views-scm.md) | Obrigatório |
| Gerenciamento de depósito | [Exibição salva da página de detalhes do trabalho](saved-views-scm.md) | Obrigatório |
| Gerenciamento de depósito | [Exibição salva para o processamento de ciclo](saved-views-scm.md) | Obrigatório |
| Gerenciamento de depósito | [Exibições salvas para o processamento de carga](saved-views-scm.md) | Obrigatório |
| Gerenciamento de depósito | [Exibições salvas para o processamento de remessa](saved-views-scm.md) | Obrigatório |
| Gerenciamento de depósito | [Digitalizar códigos de barras GS1](../warehousing/gs1-barcodes.md) | Geralmente disponível |
| Gerenciamento de depósito | Detalhes da etiqueta do ciclo de remessa | Obrigatório |
| Gerenciamento de depósito | [Unidades mistas de slots](whats-new-scm-10-0-21.md) | Obrigatório |
| Gerenciamento de depósito | [Usar API mais rápida para fechamento/reabertura de contêineres na estação de embalagem](whats-new-scm-10-0-21.md) | Ativado por padrão |
| Gerenciamento de depósito | [Validar modelos selecionados para trabalhos de reabastecimento](whats-new-scm-10-0-20.md) | Ativado por padrão |
| Gerenciamento de depósito | [Campos promovidos do aplicativo de depósito](../warehousing/warehouse-app-promoted-fields.md) | Obrigatório |
| Gerenciamento de depósito | [Instruções da etapa do aplicativo de depósito](../warehousing/mobile-app-titles-instructions.md) | Obrigatório |
| Gerenciamento de depósito | [Status da localização do depósito](../warehousing/warehouse-location-status.md) | Obrigatório |
| Gerenciamento de depósito | [Desvio do aplicativo Warehouse Management](../warehousing/warehouse-app-detours.md) | Ativado por padrão |
| Gerenciamento de depósito | [Detalhes do trabalho em lotes do ciclo](../warehousing/wave-processing.md) | Obrigatório |
| Gerenciamento de depósito | [Notificações de execução do ciclo](../warehousing/wave-execution-notifications.md) | Obrigatório |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.29 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.29 de aplicativos de finanças e operações (Junho de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md). <!--KFM: Confirm link -->

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte da versão 10.0.29, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 e nuvens do setor: plano 1 do ciclo de lançamentos de 2022

Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira [Dynamics 365 e nuvens do setor: plano 2 do ciclo de lançamentos de 2022](/dynamics365-release-plan/2022wave2/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Recursos removidos e preteridos do Supply Chain Management

O artigo [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descreve os recursos que foram ou serão removidos ou preteridos do Supply Chain Management.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no artigo [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes da remoção.

Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
