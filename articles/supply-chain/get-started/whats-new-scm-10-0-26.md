---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.26 (maio de 2022)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.26.
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: dd98b22a2dfcd8cad62bdef2d31ac2880b3422f8
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334705"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10026-may-2022"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.26 (maio de 2022)

[!include [banner](../includes/banner.md)]

Este artigo lista os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management, versão 10.0.26. Esta versão tem um número de compilação de 10.0.1192 e está disponível da seguinte maneira:

- **Versão preliminar:** março de 2022
- **Disponibilidade geral da versão (autoatualização):** abril de 2022
- **Disponibilidade geral da versão (atualização automática):** maio de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este artigo para incluir recursos inseridos no build após a publicação inicial deste artigo.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Estoque e logística | [Consulta disponível de visibilidade de estoque para suporte a itens de gerenciamento de depósito avançado](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | [Suporte à visibilidade de estoque para itens de WMS](../inventory/inventory-visibility-whs-support.md) | Gerenciamento de recursos:<br>*Habilitar itens de depósito em Visibilidade de Estoque* |
| Estoque e logística | [Disponível para promessa do suplemento de visibilidade de estoque](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | [Agendas de alterações disponíveis e disponível para promessa de Visibilidade de Estoque](../inventory/inventory-visibility-available-to-promise.md) | Habilitado por configuração de serviço |
| Fabricação | [Itens de peso variável para a interface de execução do piso de produção](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [Como os trabalhadores usam a interface de execução de piso de produção](../production-control/production-floor-execution-use.md) | Gerenciamento de recursos:<br>*Relatório de itens de peso variável da interface de execução do piso de produção* |
| Fabricação | Guia Meus trabalhos na interface de execução de piso de produção <!-- KFM: Add link to release plan when available --> | [Como os trabalhadores usam a interface de execução de piso de produção](../production-control/production-floor-execution-use.md) | Gerenciamento de recursos:<br>*Guia Meus trabalhos na interface de execução de piso de produção* |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um desses aprimoramentos fornece uma melhoria incremental para um recurso existente. Por serem apenas aprimoramentos, não estão listados no [plano de versão](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária).

Se quiser ativar o desativar qualquer um desses recursos, você deverá fazer isso no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome do recurso no gerenciamento de recursos | Mais informações |
|---|---|---|
| Compras | Lançar quantidades registradas de produtos em estoque e restantes de produtos sem estoque para recebimentos e faturas de fornecedor | Esse recurso altera a forma como quantidades de produtos não estocados (como serviços) são lançadas ao processar faturas de fornecedor e remessas de entrada em ordens de compra. O recurso modifica o comportamento da opção de quantidade *Quantidade registrada e serviços* para lançar recebimentos e faturas do fornecedor, alterando-o para corresponder ao comportamento da opção *Quantidade registrada e produtos não estocados* já fornecido ao lançar quantidades para guias de remessa de venda.<br><br>Quando você lança um recebimento de produtos ou uma fatura de fornecedor usando a opção de quantidade *Quantidade registrada e serviços*, o sistema lança a quantidade registrada de produtos em estoque e lança a quantidade pendente de produtos não estocados (incluindo serviços e não serviços). Sem esse recurso, o sistema ainda lança a quantidade registrada de produtos em estoque (incluindo serviços configurados como itens em estoque), mas sempre lança toda a quantidade solicitada de produtos e serviços não estocados (e ignora produtos não estocados que não são do tipo *Serviço*). |
| Compras | Sincronizar dimensões de rastreamento em linhas de ordem de compra e venda intercompanhia | Esse recurso permite controlar se as dimensões de controle de série e de número de lote são sincronizadas entre as linhas da ordem de compra e de venda intercompanhia. Ele adiciona novas configurações às guias **Políticas de ordem de compra** e **Políticas de ordem de venda** da página de configuração **Intercompanhia** para clientes e fornecedores. Ele também atualiza os nomes de algumas configurações relacionadas e próximas para clareza.<br><br>Se você estiver usando os processos de gerenciamento de depósito (WMS), lembre-se de que esse recurso só sincronizará números de lote e de série quando essas dimensões estiverem acima do local na hierarquia de reservas de destino. |
| Gerenciamento de informações sobre o produto | Limpar valores de atributo de produto | Esse recurso adiciona uma tarefa periódica chamada **Limpar valores de atributo de produto**, que limpa os registros de valor de atributo de produto que não estão mais associados a produtos por meio de uma categoria de produto. |
| Gerenciamento de estoque e depósito | (Rússia) Evitar discrepâncias ao emitir GTDs para ordens de compra que incluam itens habilitados para o serviço Gerenciamento de Fluxo de Trabalho | Esse recurso se destina apenas a localizações em russo. Ele impede discrepâncias que ocorrem durante a emissão de GTDs (números da declaração alfandegária) russos para importar ordens de compra que incluem itens habilitados para processos de gerenciamento de depósito (WMS). O processo de emissão de GTD altera alguns valores de dimensão de estoque nas transações de estoque relacionadas para faturas incluídas no diário personalizado, que leva a discrepâncias entre os registros de trabalho para a ordem de compra e as transações de estoque para a compra. Quando esse recurso é habilitado, o processo de emissão de GTD gera um trabalho de ajuste que elimina essas discrepâncias. |
| Gerenciamento de depósito | Analisador aprimorado de códigos de barra GS1 | Este recurso adiciona um analisador aprimorado para dados de símbolo de GS1. O novo analisador implementa o algoritmo de especificação geral de GS1 para analisar símbolos de GS1 e fornece validação de dados mais forte. Para obter mais informações, consulte [Digitalização do código de barras GS1](../warehousing/gs1-barcodes.md). |
| Gerenciamento de depósito | Aplicativo Warehouse Management – GTD em branco | Esse recurso se destina apenas a localizações em russo. Ele permite que os trabalhadores que usam o aplicativo móvel Warehouse Management deixem GTDs (números de declaração alfandegária) em branco quando necessário. Se a dimensão de rastreamento GTD estiver configurada para permitir valores em branco, o sistema aceitará valores em branco para GTD para que as operações de estoque fornecidas no estoque disponível estejam disponíveis. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes artigos de ajuda: Esses artigos não estão necessariamente relacionados aos novos recursos que foram adicionados a essa versão, conforme listado em seções anteriores. No entanto, eles podem ajudar você a aproveitar mais os recursos existentes.

| Área de recursos | Artigos novos ou atualizados |
|---|---|
| Gerenciamento de custo | Os exemplos e diagramas atualizados foram adicionados a cada um dos seguintes artigos:<ul><li>[PEPS com marcação e valor físico](../cost-management/fifo-physical-value-marking.md)</li><li>[UEPS com marcação e valor físico](../cost-management/lifo-physical-value-marking.md)</li><li>[Data UEPS com marcação e valor físico](../cost-management/lifo-date-physical-value-marking.md)</li><li>[Preço de custo médio](../cost-management/running-average-cost-price.md)</li><li>[Média ponderada com valor físico e marcação](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos de finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.26 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações da plataforma para a versão 10.0.26 de aplicativos de finanças e operações (maio de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.26, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).

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

