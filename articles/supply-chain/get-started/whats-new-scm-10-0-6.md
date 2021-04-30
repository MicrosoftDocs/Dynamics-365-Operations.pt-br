---
title: Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.6 (Novembro de 2019)
description: Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 83798af9c39ae8845125026903741882356d8845
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909320"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a>Novidades ou alterações no Dynamics 365 Supply Chain Management 10.0.6 (Novembro de 2019)

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Supply Chain Management 10.0.6. Esta versão tem um número de compilação de 10.0.234. Embora a data de disponibilidade geral seja em novembro, os novos recursos estão disponíveis para o lançamento antecipado em outubro. Para obter mais informações sobre a versão 10.0.6, consulte [Recursos adicionais](whats-new-scm-10-0-6.md#additional-resources).

## <a name="product-configuration-models-v2-data-entity"></a>Entidade de dados V2 de modelos de configuração de produto

Uma segunda versão da entidade de dados de "modelos de configuração de produto" será lançada (chamada "modelos de configuração de produto V2"). O modelo padrão de "modelos de configuração de produto 418" também deve ser para usar a nova entidade de dados "modelos de configuração de produto V2" nos modelos de estrutura de importação/exportação. O modelo não será atualizado automaticamente para que você tenha que carregar o modelo manualmente a partir do padrão. A entidade V2 exporta uma linha como arquivo separado em um anexo em vez de embutida, solucionando as limitações de tamanho da entidade V1. 
 
O que você precisa fazer para realizar esta alteração?
-    Como a entidade V1 foi substituída, você deve iniciar a migração do V1 para o V2. Se estiver usando o modelo de "modelos de configuração de produto 418", você pode clicar no botão "carregar modelos padrão" e recarregar o modelo de "modelos de configuração de produto – 418"
-    Se for necessário manter a compatibilidade com sistemas existentes, você pode continuar usando o modelo existente e a entidade V1 (preterida) até mover as integrações para o novo modelo. 

## <a name="feature-management-enhancements"></a>Aprimoramentos em gerenciamento de recursos
O gerenciamento de recursos agora permite habilitar todos os novos recursos por padrão, exigir a confirmação para habilitar um recurso e habilitar todos os recursos que ainda não foram habilitados. 


## <a name="purchase-agreement-responsible-party"></a>Participante responsável pelo Contrato de compra
Agora você pode definir as partes primárias e secundárias responsáveis no formulário de classificação do Contrato de compra e os Contratos de compra resultantes.  Isso fornece ao usuário acesso a quem supervisiona os contratos.

## <a name="rfq-link-on-the-purchase-order-line"></a>Link da RFQ na linha da Ordem de compra
Você pode adicionar um link de referência das linhas da Ordem de compra às linhas da RFQ correspondentes das quais elas foram originadas, permitindo que o usuário receba facilmente o documento da solicitação de cotação de suporte.

## <a name="additional-resources"></a>Recursos adicionais

### <a name="bug-fixes"></a>Correções de bug
Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte do 10.0.6, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da base de dados de conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).

### <a name="platform-update-30"></a>Update 30 para plataforma
O Microsoft Dynamics 365 Supply Chain Management 10.0.6 inclui a Atualização de plataforma 30. Para saber mais sobre a Atualização de plataforma 30, consulte [Novidades ou alterações da Atualização de plataforma 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Dynamics 365: plano do ciclo de lançamentos 2 de 2019
Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira o [Dynamics 365: plano do ciclo de lançamentos 2 de 2019](/dynamics365-release-plan/2019wave2/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Recursos removidos e preteridos do Supply Chain Management

O tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descreve os recursos que foram ou serão removidos ou preteridos do Supply Chain Management.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no tópico [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes da remoção.

Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]