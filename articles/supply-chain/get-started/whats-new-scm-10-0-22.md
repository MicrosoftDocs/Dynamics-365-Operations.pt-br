---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.22 (Novembro de 2021)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.22.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: a4f9e5a4a318ceaa45b6919e394e1ff335bfb193
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678826"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10022-november-2021"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.22 (Novembro de 2021)

[!include [banner](../includes/banner.md)]

Este tópico lista os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management, versão 10.0.22. Esta versão tem um número de compilação de 10.0.995 e está disponível da seguinte maneira:

- **Versão preliminar:** setembro de 2021
- **Disponibilidade geral da versão (autoatualização):** outubro de 2021
- **Disponibilidade geral da versão (autoatualização):** novembro de 2021

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. A coluna *Recurso* fornece links para o [plano de lançamento](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), no qual é possível ver as datas de lançamento oficiais de cada recurso. A coluna *Mais informações* fornece mais detalhes e/ou links para documentação relacionada. Para determinar como ativar um recurso, consulte a coluna *Habilitado por*. Para obter mais informações sobre como usar o gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Podemos atualizar este tópico para incluir recursos inseridos no build após a publicação inicial deste tópico.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Planejamento | [Suporte à Otimização de Planejamento para alocação de recursos baseada em recursos](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [Agendamento com seleção de recursos com base na capacidade](../master-planning/planning-optimization/capability-based-scheduling.md) | Gerenciamento de recursos (*Agendamento da capacidade infinita para a Otimização de Planejamento*) |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um desses aprimoramentos fornece uma melhoria incremental para um recurso existente. Por serem apenas aprimoramentos, não estão listados no [plano de versão](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária). Se você quiser usar qualquer um desses recursos, deve habilitá-los explicitamente em [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome do recurso no gerenciamento de recursos | Mais informações |
|---|---|---|
| Gerenciamento de custo | Criar comprovantes relacionados para reavaliações de arredondamento de custo padrão | <p>Quando um lançamento financeiro de estoque (como uma fatura de ordem de venda ou transação de estoque) é feito, esse recurso faz com que o sistema crie um comprovante separado para quaisquer reavaliações de arredondamento de custo padrão relacionadas e o anexa ao comprovante de lançamento financeiro como um comprovante relacionado.</p><p>Sem esse recurso, o sistema registra reavaliações de arredondamento de custo padrão no mesmo lançamento do comprovante. Esse comportamento às vezes pode causar informações conflitantes da data, porque as reavaliações usam a sessão ou a data do sistema, enquanto as postagens financeiras usam a data de lançamento.</p> |
| Topologia híbrida distribuída | *(O gerenciamento de recursos não é necessário).* | <p>Esta versão expande os recursos de planejamento de carga de saída da carga de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda.</p><p>Para obter mais informações, consulte [Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda](../cloud-edge/cloud-edge-workload-warehousing.md).</p> |
| Gerenciamento de alteração de engenharia | Geração de grades para produtos de engenharia | <p>Esse recurso permite gerar várias variantes para um produto de engenharia, com base na cor, no tamanho, no estilo ou nas dimensões de configuração.</p><p>Para obter mais informações, consulte [Gerar variantes para produtos de engenharia](../engineering-change-management/engineering-variants.md).</p> |
| Gerenciamento de depósito e estoque | Integração da Visibilidade de Estoque com compensação da reserva | <p>Esse recurso só poderá ser habilitado após a habilitação do recurso *Integração da Visibilidade do Estoque*. Ele fornece funcionalidade para reservas compensadas criadas na Visibilidade do Estoque.</p><p>Para obter mais informações, consulte [Reservas de Visibilidade de Estoque](../inventory/inventory-visibility-reservations.md).</p> |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes tópicos de ajuda. Esses tópicos não estão necessariamente relacionados aos novos recursos que foram adicionados a essa versão, conforme listado na seção anterior. No entanto, eles podem ajudar você a aproveitar mais os recursos existentes.

| Área de recursos | Tópicos novos ou atualizados |
|---|---|
| Gerenciamento de alteração de engenharia | [Visão geral do gerenciamento de alterações de engenharia](../engineering-change-management/product-engineering-overview.md) agora lista todos os recursos opcionais relacionados disponíveis no gerenciamento de recursos |
| Planejamento Mestre | [Configuração da previsão de demanda](../master-planning/demand-forecasting-setup.md) |
| Planejamento Mestre | [Requisitos líquidos e informações de vinculação com a Otimização de Planejamento](../master-planning/planning-optimization/net-requirements.md) |
| Gerenciamento de depósito | [Liberar para o depósito](../warehousing/release-to-warehouse-process.md) fornece uma visão geral detalhada do processo de liberação completa para o depósito |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para os aplicativos do Finance and Operations

O Microsoft Dynamics 365 Supply Chain Management 10.0.22 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.22 dos aplicativos do Finance and Operations (novembro de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.22, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299).

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
