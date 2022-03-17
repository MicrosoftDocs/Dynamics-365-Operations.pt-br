---
title: Versão preliminar do Dynamics 365 Supply Chain Management 10.0.25 (abril de 2022)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.25.
author: kamaybac
ms.date: 02/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 068e65d0bd76d7a9af36c6c3539d0c813efd528a
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384529"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10025-april-2022"></a>Versão preliminar do Dynamics 365 Supply Chain Management 10.0.25 (abril de 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico lista os recursos novos ou alterados na versão preliminar da versão 10.0.25 do Microsoft Dynamics 365 Supply Chain Management. Esta versão tem um número de compilação de 10.0.1149 e está disponível da seguinte maneira:

- **Versão preliminar:** fevereiro de 2022
- **Disponibilidade geral da versão (autoatualização):** março de 2022
- **Disponibilidade geral da versão (atualização automática):** abril de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este tópico para incluir recursos inseridos no build após a publicação inicial deste tópico.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Estoque&nbsp;e&nbsp;logística | [Aprimoramentos nos materiais perigosos](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/hazardous-materials-enhancements) | Em breve | Gerenciamento de recursos:<br>*Aprimoramentos nos materiais perigosos* |
| Estoque&nbsp;e&nbsp;logística | [Trabalho de embalagem para estações de embalagem](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/packing-work-packing-stations) | Em breve | Gerenciamento de recursos:<br>*Trabalho de embalagem para estações de embalagem* |
| Estoque&nbsp;e&nbsp;logística | [Digitalizar códigos de barras no depósito usando padrões de formato GS1](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [Códigos de barras de GS1 e códigos QR](../warehousing/gs1-barcodes.md) | Gerenciamento de recursos:<br>*Digitalizar códigos de barras GS1* |
| Fabricação | [Reservas e consumo de material na interface de execução do piso de produção](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [Como os trabalhadores usam a interface de execução de piso de produção](../production-control/production-floor-execution-use.md) | Gerenciamento de recursos:<br>*(Versão preliminar) Registrar consumo de material na interface de execução do piso de produção (não WMS)*<br><br>E/ou:<br><br>Gerenciamento de recursos:<br>*(Versão preliminar) Registrar consumo de materiais na interface de execução de piso de produção (habilitado para WMS)* |
| Fabricação | [Registrar consumo de materiais em unidades de escala](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/register-material-consumption-scale-units) | [Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e borda](../cloud-edge/cloud-edge-workload-manufacturing.md) | Gerenciamento de recursos:<br>*Registrar consumo de materiais no aplicativo móvel em uma unidade de escala* |
| Planejamento | [Planejando sugestões de otimização para otimizar fornecimento existente](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [Mensagens de ação](../master-planning/action-messages.md) | Habilitado por padrão |
| Planejamento | Ordens planejadas simplificadas | [Ordens planejadas simplificadas](../master-planning/planning-optimization/planned-orders-simplified.md ) | Gerenciamento de recursos:<br>*Ordens planejadas simplificadas* |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um desses aprimoramentos fornece uma melhoria incremental para um recurso existente. Por serem apenas aprimoramentos, não estão listados no [plano de versão](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária).

Se quiser ativar o desativar qualquer um desses recursos, você deverá fazer isso no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome do recurso no gerenciamento de recursos | Mais informações |
|---|---|---|
| Gerenciamento de estoque e depósito | (Polônia) Permitir o vínculo de várias faturas SAD a uma Linha da ordem de compra em um SAD | Esse recurso permite dividir linhas de ordem de compra e vinculá-las a um único documento administrativo (SAD) quando essas linhas de ordem de compra foram lançadas para várias faturas diferentes (como remessas diferentes). |
| Compras | Consolidar várias requisições de compra em uma única ordem de compra por data contábil | Esse recurso permite que várias requisições de compra sejam consolidadas em uma única ordem de compra, se as diferentes requisições de compra tiverem datas contábeis diferentes. A criação da ordem de compra e as regras de política de compras de consolidação podem ser configuradas para automatizar a decisão de agrupar linhas de requisição por data contábil no nível da ordem de compra. A consolidação da ordem de compra por data contábil não será suportada, se o controle de orçamento estiver habilitado porque a data contábil é usada para reservas e ônus de orçamento. Portanto, ela deve ser mantida durante a transição da requisição de compra para a ordem de compra. |
| Compras | Exibir configurações de campo de resposta RFQ padrão herdado | Este recurso reintroduz as configurações de campo de resposta da solicitação de cotação (RFQ) padrão herdadas, que foram previamente removidas da interface do usuário. Essas configurações não fornecem qualquer funcionalidade pronta para uso, mas podem ser personalizadas para fornecê-las. Habilite este recurso se a sua organização já tiver adicionado funcionalidades para as configurações de campo de resposta de RFQ padrão ou se estiver planejando. Quando este recurso está habilitado, você pode acessar as configurações, indo para a página **Página de compras**, abrindo a guia **Solicitação de cotação** e selecionando **Campos de resposta de solicitação de cotação padrão**. |
| Compras | Mesclar as dimensões financeiras do fornecedor com a dimensão financeira do link de dimensão ativo na ordem de compra | Esse recurso permite mesclar dimensões financeiras de fornecedores com dimensões financeiras de link de dimensão ativo após a aprovação da requisição de compra, se você configurar um link entre uma dimensão financeira e a dimensão de estoque do site. As regras de política de compra de criação de ordem de compra e consolidação de demanda podem ser configuradas para orientar a decisão de mesclar dimensões financeiras de fornecedores com dimensão financeira de link de dimensão ativa no nível do cabeçalho da ordem de compra. |
| Controle de produção | (Rússia) Habilitar configuração de localização padrão para fórmula/BOM de produção e reserva/consumo automático de GTD em produção | O recurso permite opções adicionais para a produção de matérias-primas importadas (somente localização em Russo):<ul><li>Opção para definir o local padrão automático para fórmulas de produção e listas de materiais em grupos de recursos e depósitos.</li><li>Reserva automática de matérias-primas pela dimensão de *número GTD* em depósitos ativados pelo WMS, de acordo com o algoritmo de reserva não WMS. Isso se aplica a casos em que exista uma diretiva de trabalho para a *Separação de matéria-prima* com **Método de criação de trabalho** definido como *Nunca* e o depósito, local e a configuração do número do item corresponde as transações de estoque da ordem (lote) de produção.</li><li>Consumo automático de matérias-primas por dimensão de *Número de GTD* no lançamento da lista de separação, de acordo com a reserva obtida descrita anteriormente.</li></ul> |
| Gerenciamento de depósito | (Versão preliminar) Suporte da unidade de escala para ordens de depósito de entrada e saída | Esse recurso faz com que o sistema crie ordens de depósito de saída durante o processo de liberação para depósito e crie ordens de depósito de entrada quando as ordens de transferência são lançadas como remetidas. O sistema sincroniza cada ordem de depósito de entrada ou saída com a unidade de escala responsável pela remessa ou pelo recebimento da ordem. Observe que depois de habilitar esse recurso, as cargas de trabalho de execução do depósito devem ser atualizadas. Para obter mais informações, consulte [Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda](../cloud-edge/cloud-edge-workload-warehousing.md).<br><br>Este recurso requer o recurso *Dissociar o trabalho de armazenamento de ASNs* e habilitará o recurso de recebimento de ordens de transferência usando o processo de recebimento da placa de licença no aplicativo móvel Warehouse Management. |

## <a name="feature-state-changes-in-this-release"></a>Alterações do estado do recurso nesta versão

A tabela a seguir lista os recursos que se tornaram obrigatórios ou ativados por padrão a partir da versão 10.0.25. Todos esses recursos serão automaticamente ativados para o seu sistema assim que você atualizar para a versão 10.0.25. Não é possível desativar os recursos obrigatórios, mas os recursos ativados por padrão ainda podem ser desativados usando o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

A tabela também lista recursos que anteriormente estavam na versão preliminar pública, mas que foram alterados para se tornarem disponíveis na 10.0.25, o que significa que agora eles são recomendados para uso em ambientes de produção. Esses recursos são desativados por padrão, a menos que seja indicado de outra forma, portanto, você deve usar o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitá-los se quiser usá-los.

| Módulo | Nome do recurso | Estado do recurso |
| --- | --- | --- |
| Gerenciamento de ativos | [Aplicar regras para agrupar ordens de serviço ao executar um plano de manutenção](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md) | Geralmente disponível |
| Gerenciamento de ativos | [Aprimoramentos na manutenção com base no contador](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md) | Geralmente disponível |
| Gerenciamento de custo | [Nível de cálculo de custo](../cost-management/cost-calculation-level.md) | Geralmente disponível |
| Gerenciamento de custo | Habilitar a configuração do número de lote definida pelo usuário para estorno do fechamento de estoque | Geralmente disponível |
| Gerenciamento de custo | [Detalhes do andamento de fechamento de estoque](whats-new-scm-10-0-21.md) | Geralmente disponível |
| Gerenciamento de custo | [Opções de dimensões financeiras padrão para reavaliação de custos padrão de estoque](../cost-management/manage-standard-cost-updates.md) | Geralmente disponível |
| Gerenciamento de custo | Limpeza de dados do relatório de valor de estoque | Ativado por padrão |
| Gerenciamento de custo | [Armazenamento de relatórios de valor de estoque](../cost-management/inventory-value-report-storage.md) | Ativado por padrão |
| Gerenciamento de custo | Mostrar log de fechamento/recálculo de estoque na grade | Ativado por padrão |
| Gerenciamento de alteração de engenharia | [Habilitar gerenciamento de modificações em produtos existentes](../engineering-change-management/change-management-existing-products.md) | Ativado por padrão |
| Gerenciamento de alteração de engenharia | [Gerenciamento de Alterações de Engenharia](../engineering-change-management/product-engineering-overview.md) | Ativado por padrão |
| Gerenciamento de alteração de engenharia | [Notificações de engenharia para produção](../engineering-change-management/engineering-change-management.md) | Ativado por padrão |
| Gerenciamento de alteração de engenharia | [Herança de atributo aprimorada para Gerenciamento de Modificações de Engenharia](../engineering-change-management/engineering-attributes-and-search.md) | Ativado por padrão |
| Gerenciamento de alteração de engenharia | [Gerenciar modificações em fórmulas e seus ingredientes](../engineering-change-management/manage-formula-changes.md) | Ativado por padrão |
| Gerenciamento de alteração de engenharia | [Verificações de preparação do produto](../engineering-change-management/product-readiness.md) | Ativado por padrão |
| Gerenciamento de alteração de engenharia | [Geração de grades para produtos de engenharia](../engineering-change-management/engineering-variants.md) | Ativado por padrão |
| Gerenciamento de estoque e depósito | Navegação para a versão da BOM a partir de linhas da BOM | Obrigatório |
| Planejamento Mestre | [Consolidação executável em lote e consolidação para ordens planejadas em massa e em lote](whats-new-scm-10-0-20.md) | Geralmente disponível |
| Planejamento Mestre | Planejamento de recursos com manutenção | Geralmente disponível |
| Planejamento Mestre | Habilitar recursos do assistente de configuração do plano mestre | Obrigatório |
| Planejamento Mestre | [Seleção de modelo de previsão nos detalhes de Previsão de demanda](../master-planning/manual-adjustments-baseline-forecast.md) | Obrigatório |
| Planejamento Mestre | [Visualização do progresso do planejamento mestre](../master-planning/tasks/monitor-master-planning-run.md) | Obrigatório |
| Planejamento Mestre | [Confirmação paralela das ordens planejadas](../master-planning/planning-optimization/planned-order-firming.md) | Obrigatório |
| Planejamento Mestre | [Confirmação de ordem planejada com filtros](../master-planning/planning-optimization/planned-order-firming.md) | Ativado por padrão |
| Planejamento Mestre | [Exibições salvas para ordens planejadas](saved-views-scm.md) | Ativado por padrão |
| Compras | Desabilitar botão de redefinição de distribuição de requisição de compra | Geralmente disponível |
| Compras | [Habilitar redefinição de fluxos de trabalho relacionados a compras](whats-new-scm-10-0-20.md) | Geralmente disponível |
| Compras | Capacidade de confirmar ordens de compra aceitas da colaboração do fornecedor em lote | Obrigatório |
| Compras | Status Fechado do contrato de compra | Obrigatório |
| Compras | Adicionar linhas às faturas da OC associadas a um contrato de compra | Ativado por padrão |
| Compras | Adicionar campo Quantidade encomendada à página Lançamento de recebimento de produtos | Ativado por padrão |
| Compras | [Permitir que os fornecedores solicitem categorias de compras por meio da colaboração do fornecedor](../procurement/category-requests-from-vendors.md) | Ativado por padrão |
| Compras | Encargos de valores de/até em Ordens de compra | Ativado por padrão |
| Compras | Configuração de encargos com site e depósito | Ativado por padrão |
| Compras | Habilitar o cálculo do imposto de compra com base na tarifa anual | Ativado por padrão |
| Compras | [Participante responsável pelo Contrato de compra](../procurement/purchase-agreements.md) | Ativado por padrão |
| Compras | [Exibições salvas para ordens de compra](saved-views-scm.md) | Ativado por padrão |
| Gerenciamento de informações sobre o produto | [Validação estrita em quantidades de ordem padrão](../production-control/default-order-settings.md) | Obrigatório |
| Gerenciamento de informações sobre o produto | Pré-processamento do relatório de lista de materiais para evitar tempo de inatividade | Ativado por padrão |
| Gerenciamento de informações sobre o produto | Dimensões financeiras padrão separadamente ao usar modelos de item | Ativado por padrão |
| Gerenciamento de informações sobre o produto | Habilitar grupos de dimensão do produto para modelos de item | Ativado por padrão |
| Gerenciamento de informações sobre o produto | Regenerar nomes de grade de produto com base em nomenclatura | Ativado por padrão |
| Gerenciamento de informações sobre o produto | [Aprimoramentos na página de sugestões de grade](../pim/tasks/create-predefined-product-variants.md) | Ativado por padrão |
| Controle de produção | Separação aprimorada da quantidade do peso variável da produção | Geralmente disponível |
| Controle de produção | Um novo botão Parar intervalo foi adicionado à página Terminal de Ficha de Trabalho | Obrigatório |
| Controle de produção | [Habilitar a geração automática do número da placa de licença ao concluir o relatório de conclusão no dispositivo de ficha de trabalho](../production-control/production-floor-execution-configure.md) | Obrigatório |
| Controle de produção | Habilitar o recebimento parcial de itens subcontratados e corrija um problema com o cálculo de sucata das linhas de BOM do tipo Fornecedor | Obrigatório |
| Controle de produção | [Recurso para bloqueio de dispositivo de ficha de trabalho e terminal de ficha de trabalho para que eles possam ser limpos](../production-control/production-floor-execution-configure.md) | Obrigatório |
| Controle de produção | Aprimoramentos nas caixas de diálogo Aprovar e Transferir trabalhos | Obrigatório |
| Controle de produção | [Placa de licença para relatório de conclusão adicionada ao Dispositivo de ficha de trabalho](../production-control/production-floor-execution-configure.md) | Obrigatório |
| Controle de produção | [Imprimir etiqueta do Dispositivo de Ficha de Trabalho](../production-control/production-floor-execution-configure.md) | Obrigatório |
| Controle de produção | [Execução do piso de produção](../production-control/production-floor-execution-configure.md) | Obrigatório |
| Controle de produção | [Funcionalidade de gerenciamento de ativos para a interface de execução de piso de produção](../production-control/production-floor-execution-configure.md) | Ativado por padrão |
| Controle de produção | [Pesquisa de trabalho para a interface de execução do piso de produção](../production-control/production-floor-execution-configure.md) | Ativado por padrão |
| Controle de produção | [Substituir reserva de produção padrão](../production-control/override-default-reservation-principle.md) | Ativado por padrão |
| Controle de produção | [Mostrar números de série, de lote e da placa de licença completos na interface de execução da área de produção](whats-new-scm-10-0-21.md) | Ativado por padrão |
| Vendas e marketing | [Aprimoramento de desempenho dos detalhes da ordem de venda](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Geralmente disponível |
| Vendas e marketing | Aprimoramento de desempenho dos detalhes da cotação de venda | Geralmente disponível |
| Vendas e marketing | Política de exportação de dados referenciada de ordem de venda | Obrigatório |
| Vendas e marketing | [Ordem de venda para a política de exclusão de linha de ordem de compra](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy) | Obrigatório |
| Vendas e marketing | [Política de exportação de dados referenciada de cotação de venda](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy)| Obrigatório |
| Vendas e marketing | [Otimização de exportação de entidade de dados da pessoa de contato](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Ativado por padrão |
| Vendas e marketing | Habilitar a busca para os campos de introdução do documento de cotação de venda e de conclusão do documento | Ativado por padrão |
| Vendas e marketing | [Melhorar o desempenho do relatório dos "100 melhores" clientes](whats-new-scm-10-0-23.md) | Ativado por padrão |
| Vendas e marketing | Recalcular saldo estimado do cliente | Ativado por padrão |
| Vendas e marketing | [Registro de linha da ordem de devolução de venda com precisão decimal com e sem peso variável](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Ativado por padrão |
| Vendas e marketing | [Exibições Salvas de Vendas e Marketing](saved-views-scm.md) | Ativado por padrão |
| Vendas e marketing | Confirmação de ordem de venda com um único clique | Ativado por padrão |
| Gerenciamento de depósito | [Modelos de distribuição integrada com diretivas de localização](../warehousing/planned-cross-docking.md) | Geralmente disponível |
| Gerenciamento de depósito | [Desabilitar os recebimentos esperados das ordens de qualidade que bloquearam o estoque de exemplo](../inventory/inventory-blocking.md) | Geralmente disponível |
| Gerenciamento de depósito | Histórico de recebimentos da placa de licença | Geralmente disponível |
| Gerenciamento de depósito | [Interface de equipamento de manuseio de materiais](../warehousing/mhax.md) | Geralmente disponível |
| Gerenciamento de depósito | [Arredondar quantidades para baixo para a unidade de vendas mais próxima na liberação para o depósito](whats-new-scm-10-0-19.md) | Geralmente disponível |
| Gerenciamento de depósito | Suporte à unidade de escala para listas de trabalho do aplicativos de depósito | Geralmente disponível |
| Gerenciamento de depósito | Detalhes da etiqueta do ciclo de remessa | Geralmente disponível |
| Gerenciamento de depósito | [Usar API mais rápida para fechamento/reabertura de contêineres na estação de embalagem](whats-new-scm-10-0-21.md) | Geralmente disponível |
| Gerenciamento de depósito | [Validar modelos selecionados para trabalhos de reabastecimento](whats-new-scm-10-0-20.md) | Geralmente disponível |
| Gerenciamento de depósito | Permitir que o modelo de reabastecimento use o trabalho de reabastecimento imediato (entre unidades) | Obrigatório |
| Gerenciamento de depósito | Atribuição automática dos GUIDs na criação de usuários do WHS | Obrigatório |
| Gerenciamento de depósito | Capturar grades de produtos e dimensões de rastreamento no aplicativo de depósito durante o recebimento do item de carga | Obrigatório |
| Gerenciamento de depósito | [Alterar o status de estoque de itens controlados por dimensões de rastreamento](../inventory/inventory-statuses.md) | Obrigatório |
| Gerenciamento de depósito | [Alterar pool de trabalho no trabalho](../warehousing/change-work-pool-on-work.md) | Obrigatório |
| Gerenciamento de depósito | [Posição de cluster completa](../warehousing/cluster-position-full.md) | Obrigatório |
| Gerenciamento de depósito | [Recurso de armazenamento de cluster](../warehousing/putaway-clusters.md) | Obrigatório |
| Gerenciamento de depósito | [Confirmar e transferir](../warehousing/confirm-and-transfer.md) | Obrigatório |
| Gerenciamento de depósito | [Confirmar remessas de saída de trabalhos em lote](../warehousing/confirm-outbound-shipments-from-batch-jobs.md) | Obrigatório |
| Gerenciamento de depósito | [Controlar se uma página de resumo do recebimento deve ser exibida em dispositivos móveis](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obrigatório |
| Gerenciamento de depósito | [Processamento adiado da operação de movimentação de estoque manual](../warehousing/deferred-processing-manual-inventory-movement.md) | Obrigatório |
| Gerenciamento de depósito | Não permitir a criação de cargas que não atendam aos requisitos do modelo de criação de carga de ciclo | Obrigatório |
| Gerenciamento de depósito | [Layouts aprimorados da etiqueta da placa de licença](../warehousing/document-routing-layout-for-license-plates.md) | Obrigatório |
| Gerenciamento de depósito | [Avaliar todas as ações para diretivas de localização de várias SKUs](../troubleshooting/warehousing/evaluate-multiple-location-directive-actions.md) | Obrigatório |
| Gerenciamento de depósito | Ocultar o campo Valor Total nas páginas "Todas as Cargas" e "Detalhes da Carga" | Obrigatório |
| Gerenciamento de depósito | Configuração de criação de etiqueta de placa de licença | Obrigatório |
| Gerenciamento de depósito | Correção manual da linha de carga para administrador ou usuários confiáveis de cargo semelhante | Obrigatório |
| Gerenciamento de depósito | [Posicionamento da placa de licença de localização](../warehousing/location-license-plate-positioning.md) | Obrigatório |
| Gerenciamento de depósito | [Combinação de dimensões do produto de localização](../warehousing/location-product-dimension-mixing.md) | Obrigatório |
| Gerenciamento de depósito | Tornar editável o campo de status do estoque de movimento do dispositivo móvel | Obrigatório |
| Gerenciamento de depósito | Serviço de separação manual de linha de venda para administrador ou usuários confiáveis semelhantes | Obrigatório |
| Gerenciamento de depósito | [Impedir que as placas de licença enviadas de ordem de transferência sejam usadas em depósitos que não sejam o depósito de destino](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obrigatório |
| Gerenciamento de depósito | Aviso para resolver nomes de "Localização/Placa de licença" ambíguos | Obrigatório |
| Gerenciamento de depósito | [Verificação de qualidade](../warehousing/quality-check.md) | Obrigatório |
| Gerenciamento de depósito | [Configurações de usuário, ícones e títulos de etapas para o novo aplicativo de depósito](../warehousing/install-configure-warehouse-management-app.md) | Obrigatório |
| Gerenciamento de depósito | [Zona de localização adicional](../warehousing/additional-location-zones.md) | Ativado por padrão |
| Gerenciamento de depósito | [Criar e processar ordens de transferência do aplicativo de depósito](../warehousing/create-transfer-order-from-warehouse-app.md) | Ativado por padrão |
| Gerenciamento de depósito | Habilitar a validação rápida para dispositivos móveis de depósito | Ativado por padrão |
| Gerenciamento de depósito | [Tempo de execução máximo para o trabalho de limpeza de entradas disponíveis no gerenciamento de depósito](../warehousing/onhand-cleanup.md) | Ativado por padrão |
| Gerenciamento de depósito | [Visualização da carga de trabalho de saída](../warehousing/outbound-workload-visualization.md) | Ativado por padrão |
| Gerenciamento de depósito | [Processar eventos do aplicativo de depósito](../warehousing/warehouse-app-events.md) | Ativado por padrão |
| Gerenciamento de depósito | [Exibição salva da bancada de planejamento da carga](saved-views-scm.md) | Ativado por padrão |
| Gerenciamento de depósito | [Exibição salva da página de detalhes do trabalho](saved-views-scm.md) | Ativado por padrão |
| Gerenciamento de depósito | [Exibição salva para o processamento de ciclo](saved-views-scm.md) | Ativado por padrão |
| Gerenciamento de depósito | [Exibições salvas para o processamento de carga](saved-views-scm.md) | Ativado por padrão |
| Gerenciamento de depósito | [Exibições salvas para o processamento de remessa](saved-views-scm.md) | Ativado por padrão |
| Gerenciamento de depósito | [Detalhes do trabalho em lotes do ciclo](../warehousing/wave-processing.md) | Ativado por padrão |
| Gerenciamento de depósito | [Notificações de execução do ciclo](../warehousing/wave-execution-notifications.md) | Ativado por padrão |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.25 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.25 dos aplicativos de Finanças e Operações (abril de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.25, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 e nuvens do setor: plano 1 do ciclo de lançamentos de 2022

Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira [Dynamics 365 e nuvens do setor: plano 1 do ciclo de lançamentos de 2022](/dynamics365-release-plan/2022wave1/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Recursos removidos e preteridos do Supply Chain Management

O tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descreve os recursos que foram ou serão removidos ou preteridos do Supply Chain Management.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes da remoção.

Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
