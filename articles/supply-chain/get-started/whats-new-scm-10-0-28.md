---
title: Versão prévia do Dynamics 365 Supply Chain Management 10.0.28 (agosto de 2022)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.28.
author: kamaybac
ms.date: 05/27/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 306ff9be80c7a7a947b9132e3c9b4b9ec799b265
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813032"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10028-august-2022"></a>Versão prévia do Dynamics 365 Supply Chain Management 10.0.28 (agosto de 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico lista recursos novos ou alterados na versão prévia do Microsoft Dynamics 365 Supply Chain Management 10.0.28. Esta versão tem um número de compilação 10.0.1264 e está disponível na seguinte agenda:

- **Versão preliminar:** maio de 2022
- **Disponibilidade geral da versão (autoatualização):** julho de 2022
- **Disponibilidade geral da versão (atualização automática):** julho de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este tópico para incluir recursos que foram adicionados à compilação após a publicação inicial deste tópico.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Estoque e logística | [Entidades de integração de custo de entrega para controladores de frete terceirizados](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/landed-cost-integration-third-party-freight-forwarders) | [Visão geral das entidades de custo de entrega](../landed-cost/landed-cost-entities-overview.md) | Habilitado por padrão |
| Planejamento | [Suporte para otimização de planejamento de validade](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-shelf-life) | Em breve <!-- KFM: Vendor is preparing this. Expected May 20. --> | Habilitado por padrão |

<!-- KFM: Confirm status of this feature:
| Planning | [Demand Driven Material Requirements Planning (DDMRP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/demand-driven-material-requirements-planning-ddmrp) | Coming soon | Feature management:<br>*(Preview) DDMRP for Planning Optimization* | -->

## <a name="feature-enhancements-included-in-this-release"></a>Aprimoramentos de recursos incluídos nesta versão

A tabela a seguir lista os aprimoramentos de recursos incluídos nesta versão. Cada um desses aprimoramentos fornece uma melhoria incremental para um recurso existente. Por serem apenas aprimoramentos, não estão listados no [plano de versão](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Contudo, para garantir que esses aprimoramentos não entrem em conflito com suas personalizações ou preferências existentes, cada um deles é desativado por padrão (a menos haja indicação contrária).

Se quiser ativar ou desativar qualquer um desses recursos, você deverá fazer isso em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nome do recurso no gerenciamento de recursos | Mais informações |
|---|---|---|
| Gerenciamento de estoque e depósito | Habilitar intercompanhia disponível para mostrar apenas a quantidade disponível diferente de zero | Este recurso permite que você escolha se itens com quantidade zero disponível devem ser incluídos na lista intercompanhia disponível. Você pode controlar essa opção usando a configuração **Não mostrar itens com quantidade zero disponível na lista intercompanhia disponível**, que esse recurso adiciona à página **Parâmetros de gerenciamento de estoque e depósito**. |
| Gerenciamento de estoque e depósito | (Índia) Para regras de preço de transferência, ignore a localização quando "Código do depósito de origem" estiver definido como "Todos" | <p>Este recurso se aplica apenas às localizações da Índia. Isso torna mais intuitivo o processo de configuração de preços de transferência para itens em transferências de estoque.</p><p>Você configura preços de transferência configurando cada item com regras de preços de transferência. Uma maneira de fazer essa configuração é incluir uma linha de regra em que o campo **Código do depósito de origem** esteja definido como *Tudo*. Essa configuração indica que o preço de transferência definido pela linha deve ser aplicado independentemente do depósito do qual o item é retirado. Quando esse recurso estiver ativado, as regras de preço de transferência em que o campo **Código do depósito de origem** estiver definido como *Tudo* ignorarão a configuração **Localização**. Portanto, a regra será aplicada independentemente do local especificado no pedido de transferência. Esse comportamento é provavelmente o esperado, porque o local está abaixo do depósito na hierarquia da dimensão de armazenamento.</p><p>Sem esse recurso, o sistema aplicará regras desse tipo somente quando o local na ordem de transferência corresponder exatamente ao local definido para a regra. (Se um local em branco for definido para a regra, o sistema aplicará a regra apenas a pedidos de transferência que também tenham um valor em branco para o local.)</p> |
| Gerenciamento de estoque e depósito | Limpeza de dados do relatório de estoque disponível | Esse recurso fornece uma maneira de limpar os dados que são usados para criar relatórios *Armazenamento de relatório de estoque disponível*. |
| Controle de produção | Atribuir atividades de projeto a contratos de serviço e linhas de ordem de serviço | Esse recurso adiciona um campo denominado **Atividade do projeto** ao contrato de serviço e às linhas da ordem de serviço, para que você possa definir uma atividade do projeto para eles. O recurso ajudará a evitar erros de bloqueio ao lançar diários de projeto de gerenciamento de serviço que exigem que uma atividade de projeto seja definida.  |
| Gerenciamento de depósito | Serviço de separação manual de linha de transferência para administradores ou usuários confiáveis semelhantes | Esse recurso permite que os administradores selecionem manualmente as transações de estoque relacionadas às linhas de transferência. Essas linhas incluem linhas que já foram liberadas para o depósito. Os administradores devem fazer essa seleção apenas em casos excepcionais, como quando o sistema está corrompido. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentação novos e atualizados

Recentemente, adicionamos ou atualizamos significativamente os seguintes tópicos de ajuda: Esses tópicos não estão necessariamente relacionados aos novos recursos que foram adicionados a essa versão, conforme listado em seções anteriores. No entanto, eles podem ajudar você a aproveitar mais os recursos existentes.

| Área de recursos | Tópicos novos ou atualizados |
|---|---|
| Gerenciamento de custo | [Preço de recebimento fixo](../cost-management/fixed-receipt-price.md) |
| Gerenciamento de custo | [Perguntas frequentes sobre custos de estoque](../cost-management/inventory-costing-faq.md) |
| Gerenciamento de custo | [Princípio contábil de lançar na conta de encargos](../cost-management/post-to-charge-account-accounting-principle.md) |
| Gerenciamento de estoque | [Detalhes da transação de estoque](../inventory/inventory-transactions-details.md) |

## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Supply Chain Management 10.0.28 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações de plataforma para a versão 10.0.28 de aplicativos de finanças e operações (Junho de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-28.md).<!-- KFM Confirm link -->

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.28, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).

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