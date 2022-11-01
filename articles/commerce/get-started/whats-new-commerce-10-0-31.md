---
title: Versão preliminar do Dynamics 365 Commerce 10.0.31 (fevereiro de 2023)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Commerce 10.0.31.
author: josaw1
ms.date: 10/18/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-10-01
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 05ccd9794ffeba6a09d6fec0a57ffad2b59707ad
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709851"
---
# <a name="preview-of-dynamics-365-commerce-10031-february-2023"></a>Versão preliminar do Dynamics 365 Commerce 10.0.31 (fevereiro de 2023)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo lista os recursos novos ou alterados na versão preliminar 10.0.31 do Microsoft Dynamics 365 Commerce. Esta versão tem um número de compilação 10.0.1406 e está disponível na seguinte agenda:

- **Versão preliminar:** outubro de 2022
- **Disponibilidade geral da versão (atualização automática):** janeiro de 2023
- **Disponibilidade geral da versão (atualização automática):** fevereiro de 2023

## <a name="features-included-in-this-release"></a>Recursos incluídos nesta versão

A tabela a seguir lista os recursos incluídos nesta versão. Podemos atualizar este artigo para incluir recursos que foram adicionados à compilação após a publicação inicial deste artigo.

| Área de recursos | Recurso | Mais informações | Habilitado por   |
|---|---|---|---|
| Códigos de erro | O Commerce introduziu referências de erro padronizadas a serem incluídas nos erros de finalização da compra no canal on-line que os compradores recebem.| [Códigos de erro do módulo de finalização da compra](../checkout-module-error-codes.md)  | Ativado por padrão |
| Pagamentos | [Habilitar o Apple Pay com o Dynamics 365 Payment Connector para Adyen](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-apple-pay-dynamics-365-payment-connector-adyen)  | Os clientes de comércio eletrônico podem usar o Apple Pay nas páginas do carrinho e de finalização da compra em dispositivos e navegadores compatíveis. | Aceitação do desenvolvedor |
| Pagamentos  |  O Commerce adicionou a capacidade de limitar a forma que os usuários interagem com os tokens de pagamento recorrente em toda a interface do Commerce headquarters. As formas de pagamento, como a página **Pedido de Venda do Call Center**, não exibem mais o token de pagamento recorrente utilizado anteriormente por um cliente para uso em uma nova transação. Apenas uma determinada entrada de "cartão registrado" na tela **Pagamentos do Cliente** no Commerce, ou com o consentimento de um cliente ao pagar um pedido de venda, aparecerá para os usuários de call center ou do Commerce headquarters ao processar um pagamento de uma nova transação. | [Limitar o uso de token de pagamento](../dev-itpro/limit-token-usage.md)  |  Gerenciamento de recursos<p>*Restringir uso do Token de Pagamento no Contexto da ordem*  |
| PDV | [Criar ordens de compra do PDV](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/create-purchase-orders-pos)  |  Operação aprimorada de estoque de entrada no aplicativo do ponto de venda (PDV) para permitir que os usuários criem, editem e confirmem solicitações de ordem de compra. |  Gerenciamento de recursos<p>*Capacidade de criar solicitações de ordem de compra no PDV*   |



## <a name="additional-resources"></a>Recursos adicionais

### <a name="platform-updates-for-finance-and-operations-apps"></a>Atualizações da plataforma para aplicativos do Finanças e operações

O Microsoft Dynamics 365 Commerce 10.0.31 inclui atualizações de plataforma. Para saber mais, consulte [Atualizações da plataforma para a versão 10.0.31 dos aplicativos de finanças e operações (fevereiro de 2023)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-31.md). 
  

### <a name="bug-fixes"></a>Correções de bug

Para obter informações sobre as correções de bug incluídas em cada uma das atualizações que fazem parte da versão 10.0.31, entre no Microsoft Dynamics Lifecycle Services e abra o [Artigo da Base de Dados de Conhecimento](https://fix.lcs.dynamics.com/Issue/Details?bugId=758525).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 e nuvens do setor: plano 2 do ciclo de lançamentos de 2022

Quer saber sobre os futuros recursos e as funcionalidades lançadas recentemente em nossos aplicativos ou plataforma de negócios?

Confira [Dynamics 365 e nuvens do setor: plano 2 do ciclo de lançamentos de 2022](/dynamics365-release-plan/2022wave2/). Capturamos todos os detalhes, de todos os ângulos, em um único documento que você pode usar para o planejamento.

### <a name="removed-and-deprecated-commerce-features"></a>Recursos do Commerce removidos e preteridos

Os [recursos removidos ou preteridos no artigo Dynamics 365 Commerce](removed-deprecated-features-commerce.md) descrevem os recursos que foram removidos ou preteridos para o Commerce.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Antes que qualquer recurso seja removido do produto, o aviso de substituição será anunciado no artigo [Recursos removidos ou preteridos no Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 meses antes da remoção.


Para as últimas alterações que afetam somente o tempo de compilação, mas são compatíveis binárias com a área restrita e os ambientes de produção, o tempo de substituição será inferior a 12 meses. Normalmente, essas são atualizações funcionais que precisam ser feitas no compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
