---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.24 (Fevereiro de 2022)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.24.
author: kamaybac
ms.date: 12/03/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: a254e20dd7fcc29ca520282b4bf9fcd903e4de58
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087541"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10024-february-2022"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.24 (Fevereiro de 2022)

[!include [banner](../includes/banner.md)]

Este tópico lista os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management, versão 10.0.24. Esta versão tem um número de compilação de 10.0.1084 e está disponível da seguinte maneira:

- **Versão preliminar**: dezembro de 2021
- **Disponibilidade geral da versão (atualização automática):** janeiro de 2022
- **Disponibilidade geral da versão (atualização automática):** fevereiro de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este tópico para incluir recursos inseridos no build após a publicação inicial deste tópico.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Topologia híbrida distribuída | [Cargas de trabalho de execução de depósito aprimoradas nas unidades de escala](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e borda](../cloud-edge/cloud-edge-workload-warehousing.md) | Habilitado por padrão. |
| Topologia híbrida distribuída | [Iniciar a ordem de produção na carga de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-manufacturing-execution-workloads-scale-units) | [Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e borda](../cloud-edge/cloud-edge-workload-manufacturing.md) | Gerenciamento de recursos (*Iniciar a ordem de produção na carga de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda*)  |
| Planejamento | [Suporte da Otimização de Planejamento à margem de segurança e à margem de saída](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [Margens de segurança](../master-planning/planning-optimization/safety-margins.md) | Habilitado por padrão. |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um desses aprimoramentos fornece uma melhoria incremental para um recurso existente. Por serem apenas aprimoramentos, não estão listados no [plano de versão](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária).

Se quiser ativar o desativar qualquer um desses recursos, você deverá fazer isso no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome do recurso no gerenciamento de recursos | Mais informações |
|---|---|---|
| Controle de produção | Verificação de disponibilidade de material sob demanda para ordens de produção | Esse recurso facilita a abertura da página **Ordens de produção a liberar**, que está disponível no espaço de trabalho **Gerenciamento de piso de produção**. Sem esse recurso, o sistema verifica automaticamente se há materiais disponíveis para todas as ordens de produção listadas assim que você abre a página, o que pode levar um tempo significativo se você tiver um grande número de ordens. Quando o recurso está habilitado, o sistema fornece um botão de barra de ferramentas, que pode ser usado para iniciar a verificação de materiais somente para ordens selecionadas e quando for necessário. |
| Controle de produção | (Versão preliminar) Registrar consumo de material na interface de execução do piso de produção (não WMS) | Esse recurso permite que os trabalhadores usem a interface de execução do piso de produção para registrar o consumo de materiais, os números de lote e os números de série. Esse recurso só oferece suporte a itens que não estão habilitados para usar processos avançados de depósito (WMS). O suporte a itens habilitados para WMS está agendado para uma versão futura.<p>Alguns fabricantes, especialmente aqueles nas indústrias de processamento, devem registrar explicitamente a quantidade de material consumido para cada ordem de produção ou lote. Por exemplo, os trabalhadores podem usar uma escala para avaliar a quantidade de material consumido conforme trabalham. Para garantir a rastreabilidade total do material, essas organizações também devem registrar os números de lote que foram consumidos durante a produção de cada produto. |
| Controle de produção | Relatar como concluído na carga de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda | Esse recurso permite que os funcionários usem o aplicativo móvel Warehouse Management para relatar uma ordem de produção ou de lotes como concluída quando o aplicativo é executado em uma carga de trabalho de gerenciamento de depósito em uma unidade de escala de nuvem ou de borda. Para obter mais informações, consulte [Relatar como finalizado e armazenado em uma unidade de escala](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF). |
| Gerenciamento de depósito | Novas páginas da bancada de planejamento de carga | Habilita duas novas páginas de bancada de planejamento de carga: **Workbench de planejamento de carga de entrada** e **Workbench de planejamento de carga de saída**. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes tópicos de ajuda. Esses tópicos não estão necessariamente relacionados aos novos recursos que foram adicionados a essa versão, conforme listado na seção anterior. No entanto, eles podem ajudar você a aproveitar mais os recursos existentes.

| Área de recursos | Tópicos novos ou atualizados |
|---|---|
| Gerenciamento de custo | [Relatórios de valor de estoque](../cost-management/inventory-value-report-storage.md) |
| Gerenciamento de custo | [Exemplos e lógica de relatório de valor de estoque](../cost-management/inventory-value-report-examples.md) |
| Planejamento Mestre | [Parâmetros de data e hora usados pela Otimização de Planejamento](../master-planning/planning-optimization/date-time-used.md) |
| Planejamento Mestre | [Configuração da previsão de demanda](../master-planning/demand-forecasting-setup.md) |
| Planejamento Mestre | [Usar o diário de estoque de segurança para atualizar a cobertura mínima para os itens](../master-planning/safety-stock-journal.md) |
| Controle de produção | [Personalizar a interface de execução de piso de produção](../production-control/production-floor-execution-customize.md) |
| Controle de produção | [Estilizar a interface de execução de piso de produção](../production-control/production-floor-execution-styles.md) |
| Vendas e marketing | [Melhorias no desempenho de limpeza do histórico de vendas](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Gerenciamento de depósito | [Contas de usuário do dispositivo móvel](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.24 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.24 dos aplicativos de Finanças e Operações (fevereiro de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.24, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=641306&dbType=3&qc=5b1d5e49c96b8a5cfb5601889a413e6f3773ba6500f9bc47310dcc5c54fff42f).

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
