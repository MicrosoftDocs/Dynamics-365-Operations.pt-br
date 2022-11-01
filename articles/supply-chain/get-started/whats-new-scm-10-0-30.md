---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.30 (Novembro de 2022)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.30.
author: kamaybac
ms.date: 09/08/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-09-08
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2983c113487934fd0751efcef9129e1f28d8dce8
ms.sourcegitcommit: 86c0562ce1ecdf7937125c0f5a6771f178b459e7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714789"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10030-november-2022"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.30 (Novembro de 2022)

[!include [banner](../includes/banner.md)]

Este artigo lista os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management, versão 10.0.30. Esta versão tem um número de compilação 10.0.1362 e está disponível na seguinte agenda:

- **Versão preliminar:** setembro de 2022
- **Disponibilidade geral da versão (autoatualização):** outubro de 2022
- **Disponibilidade geral da versão (autoatualização):** novembro de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este artigo para incluir recursos que foram adicionados à compilação após a publicação inicial deste artigo.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Fabricação | [Monitorar equipamento com o Sensor Data Intelligence](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/monitor-equipment-sensor-data-intelligence) | [Página inicial do Sensor Data Intelligence](../sensor-data-intelligence/sdi-home-page.md) | Gerenciamento de recursos:<br>*(Versão Preliminar) Sensor Data Intelligence* |
| Gerenciamento de depósito | [Desvios de vários níveis para o aplicativo móvel Warehouse Management](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/multi-level-detours-warehouse-management-mobile-app) | [Configurar desvios para as etapas nos itens de menu do dispositivo móvel](../warehousing/warehouse-app-detours.md) | Gerenciamento de recursos:<br>*Desvios de vários níveis para o aplicativo móvel Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um desses aprimoramentos fornece uma melhoria incremental para um recurso existente. Por serem apenas aprimoramentos, não estão listados no [plano de versão](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária).

Se quiser ativar ou desativar qualquer um desses recursos, você deverá fazer isso em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome do recurso no gerenciamento de recursos | Mais informações |
|---|---|---|
| Controle de produção | Informações disponíveis nas ordens de produção para liberar página | Adiciona uma coluna para a quantidade em estoque disponível para o item de linha na seção de linhas na página **Ordens de produção para liberar**. |
| Gerenciamento de transporte | Atribuir remessas a segmentos de roteiro relacionados | Este recurso permite que o sistema alcance os custos de frete de remessa de forma mais precisa, incluindo as cargas com várias remessas entregues a vários destinos de segmento ao longo de um único roteiro. Ele atribui cada remessa ao segmento de rota mais adequado com base nos endereços de destino da remessa e do segmento. Em seguida, o recurso calcula o custo de frete de cada remessa como uma proporção do custo total de frete do carregamento, com base no peso relativo da remessa, no volume, na quantidade e na distância percorrida. Este recurso só se aplica a remessas gerenciadas usando o módulo Transport Management (TMS). |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.30 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.30 dos aplicativos Finanças e operações (novembro de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte da versão 10.0.30, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).

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
