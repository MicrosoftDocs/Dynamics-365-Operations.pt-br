---
title: Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B
description: Este tópico descreve como configurar o método de pagamento da conta do cliente para sites de comércio eletrônico business-to-business (B2B).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 62e8f4949dcea1cb201bece171991047ce28da04
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799796"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B

[!include [banner](../../includes/banner.md)]

Este tópico descreve como configurar o método de pagamento da conta do cliente para sites de comércio eletrônico business-to-business (B2B).

Os varejistas podem aceitar vários tipos de pagamento em troca de produtos e serviços vendidos em um canal de comércio eletrônico. Cada tipo de pagamento que o varejista aceita deve ser configurado no Microsoft Dynamics 365 Commerce quando o sistema for configurado. O método de pagamento da conta do cliente (ou "por conta") deve ter suporte em sites de comércio eletrônico B2B. 

## <a name="prerequisites"></a>Pré-requisitos

1. Adicione o método de pagamento da conta do cliente na sede do Commerce.
2. Associe o método de pagamento da conta do cliente ao canal de comércio eletrônico.
3. Verifique se **Permitir por conta** está habilitado para o cliente em **Varejo e Comércio \> Clientes \> Todos os clientes \> Padrões de pagamentos** na sede do Commerce. Verifique também se os parâmetros de **Limite de crédito** estão definidos corretamente para o cliente em **Varejo e Comércio \> Clientes \> Todos os clientes \> Crédito e Coleções** na sede do Commerce. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Habilitar o método de pagamento da conta do cliente no assistente para criação de sites do Commerce 

Para habilitar o método de pagamento da conta do cliente no assistente para criação de sites do Commerce, siga estas etapas.

1. Acesse **Configurações do Site \> Extensões**.
1. Defina a propriedade **Habilitar pagamentos de conta do cliente** como **Habilitado para clientes B2B**. 
1. Selecione **Salvar e publicar**.

> [!NOTE]
> As novas configurações de sites terão efeito somente após a atualização do arquivo app.settings.json. Para obter mais informações, consulte [SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Habilitar o método de pagamento da conta do cliente na página de finalização de compra para o site de comércio eletrônico B2B

Para habilitar o método de pagamento da conta do cliente na página de finalização de compra para o site de comércio eletrônico B2B, siga estas etapas.

1. No assistente para criação de sites do Commerce, encontre e edite a página de finalização de compra ou o fragmento que contenha o módulo de finalização de compra para o site de comércio eletrônico B2B.
1. No slot de **Contêiner da seção de finalização de compra**, selecione **Adicionar Módulo** e, depois, adicione um módulo **Pagamento de conta do cliente**.
1. Para posicionar o módulo **Pagamento da conta do cliente**, selecione a elipse (**...**) e, depois, selecione **Mover para cima** ou **Mover para baixo**, conforme necessário.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Confirme que o método de pagamento da conta do cliente foi ativado e publicado

Para confirmar que o método de pagamento da conta do cliente foi ativado e publicado, siga estas etapas.

1. Entre no site de comércio eletrônico.
1. Adicione um produto ao carrinho.
1. Acesse a página de finalização de compra. Você deve ver o novo método de pagamento da **Conta do Cliente**.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um site de comércio eletrônico B2B](set-up-b2b-site.md)

[Criar hierarquias de modelagem de organização para organizações B2B](org-model.md)

[Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B](manage-b2b-users.md)

[Definir limites de quantidade de produto para sites de comércio eletrônico B2B](quantity-limits.md)

[SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]