---
title: Versão preliminar do Dynamics 365 Commerce 10.0.30 (novembro de 2022)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Commerce 10.0.30.
author: josaw1
ms.date: 08/31/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-09-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 0149c9671e8baeb26965b4f136ed91d09e2d039b
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405542"
---
# <a name="preview-of-dynamics-365-commerce-10030-november-2022"></a>Versão preliminar do Dynamics 365 Commerce 10.0.30 (novembro de 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo lista os recursos novos ou alterados na versão preliminar 10.0.30 do Microsoft Dynamics 365 Commerce. Esta versão tem um número de compilação 10.0.1362 e está disponível na seguinte agenda:

- **Versão preliminar:** setembro de 2022
- **Disponibilidade geral da versão (autoatualização):** outubro de 2022
- **Disponibilidade geral da versão (autoatualização):** novembro de 2022

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este artigo para incluir recursos que foram adicionados à compilação após a publicação inicial deste artigo.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---------|------------------|----------------|--------------| 
| Atendimento ao cliente   | Chat em um site de comércio eletrônico usando um bot do Power Virtual Agents. | Este recurso oferecerá aos usuários do site de comércio eletrônico uma opção para usar um bot de chat do Power Virtual Agents para solicitações de suporte. | Habilitado por administradores/responsáveis para usuários finais |
| Insights  |  Fluxo de insights operacionais do ponto de venda (PDV) para a sua conta do Application Insights. | [Acessar logs no Application Insights](../dev-itpro/retail-component-events-diagnostics-troubleshooting.md#enable-diagnostic-events-in-application-insights)   |  Aceitação de profissional de TI/desenvolvedor   |
|  Pagamentos  | Suporte para ordem do PayPal além do período de autorização de 29 dias. | O período máximo de autorização para o PayPal é de 29 dias, após o qual uma nova autorização e a ID da ordem deverão ser geradas. Como alternativa, o PayPal oferece uma opção em que uma ordem de PayPal pode ser referenciada como uma ordem geral, permitindo várias autorizações e capturas na mesma ID da ordem, em vez de gerar uma nova autorização e ID de ordem em 29 dias). | Ao configurar o conector de pagamento PayPal no Commerce headquarters, o campo **OrderIntent** foi adicionado e pode ter dois valores:<p><p>- **Autorizar**: esta configuração é o padrão (se o campo for deixado em branco, **Autorizar** atuará como padrão). Configurar **OrderIntent** como **Autorizar** está correlacionado ao valor PayPal **processing_instruction** de **NO_INSTRUCTION**. A ordem será autorizada com o PayPal e a autorização não poderá ser modificada quando esse valor for usado.<p>- **Salvar**: quando o valor **OrderIntent** estiver definido como **Salvar**, isso será correlacionado ao valor PayPal **processing_instruction** de **ORDER_SAVED_EXPLICITLY**. As referências da ordem serão salvas no serviço PayPal quando esse valor for usado.  |
| Entrada de PDV  | [Habilitar recursos de diagnóstico de autoatendimento para entrada de PDV](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-self-serve-diagnosis-capabilities-pos-sign-in)  |  Esse recurso fornece recursos de diagnóstico de autoatendimento no PDV (ponto de venda) e no Commerce headquarters para ajudar funcionários e gerentes de loja a identificar e corrigir rapidamente as causas dos problemas de entrada de PDV.<p><p>- As mensagens de falha mostradas na tela de entrada de PDV foram aperfeiçoadas para fornecer informações de causa raiz concretas que podem ajudar funcionários de loja que usam o PDV para entender o que deu errado para que possam executar as ações necessárias para solucionar o problema.<p>- Uma função **Testar logon** está disponível na página **Trabalhadores** no Commerce headquarters para que os gerentes de loja que configuram dispositivos de PDV possam simular a entrada de PDV. No caso de uma falha de entrada, esta função fornece guias de solução de problemas acionáveis para que os gerentes possam verificar as configurações relevantes, corrigir os problemas e validar as correções.  | Ativado por padrão |


## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Dynamics 365 Finance 10.0.30 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações da plataforma para a versão 10.0.30 de aplicativos de finanças e operações](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte da versão 10.0.30, faça logon no Lifecycle Services (LCS) e exiba o [Artigo da KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 e nuvens do setor: plano 2 do ciclo de lançamentos de 2022

Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira [Dynamics 365 e nuvens do setor: plano 2 do ciclo de lançamentos de 2022](/dynamics365-release-plan/2022wave2/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-features"></a>Recursos removidos e preteridos

Os [recursos removidos ou preteridos no artigo Dynamics 365 Commerce](removed-deprecated-features-commerce.md) descrevem os recursos que foram removidos ou preteridos para o Commerce.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no artigo [Recursos removidos ou preteridos no Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 meses antes da remoção.

Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
