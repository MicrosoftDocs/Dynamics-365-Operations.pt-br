---
title: Módulo de pagamento
description: Este tópico abrange o módulo do pagamento e explica como configurá-lo no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 894ac35973927c193d6e9c54e326daefb8a3f4a5
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055372"
---
# <a name="payment-module"></a>Módulo de pagamento

[!include [banner](includes/banner.md)]

Este tópico abrange o módulo do pagamento e explica como configurá-lo no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O módulo de pagamento permite que clientes paguem por pedidos usando cartões de crédito ou de débito. A integração de pagamento para este módulo é fornecida pelo Conector de Pagamento do Dynamics 365 para Adyen. Para obter mais informações sobre como configurar o conector de pagamento, consulte [Conector de Pagamento do Dynamics 365 para Adyen](dev-itpro/adyen-connector.md).

O módulo de pagamento hospeda as informações de pagamento fornecidas por meio de Adyen em um quadro embutido em HTML (iFrame). O módulo de pagamento interage com a Commerce Scale Unit para recuperar as informações de pagamento de Adyen. Como parte da interação da Commerce Scale Unit, o módulo de pagamento pode permitir que as informações de endereço de cobrança sejam fornecidas no iFrame ou como um módulo separado. No tema Fabrikam, o endereço de cobrança é mostrado em um módulo separado. Essa abordagem permite mais flexibilidade de formatação porque as linhas de endereço podem ser processadas para que se pareçam com as linhas do endereço de remessa.

O módulo de pagamento também permite que os clientes conectados salvem informações de pagamento. As informações de pagamento e o endereço de cobrança são salvos e gerenciados pelo conector de pagamento Adyen.

O módulo de pagamento cobre todos os encargos de ordem que ainda não foram cobertos por pontos de fidelidade ou um vale-presente. Se o total de uma ordem for totalmente abrangido por pontos de fidelidade ou créditos de vale-presente, o módulo de pagamento ficará oculto e o cliente poderá fazer o pedido sem ele.

O conector de pagamento de Adyen também dá suporte à Autenticação de Cliente Forte (SCA). Parte da Diretiva de Serviços de Pagamento da União Europeia (UE) 2.0 (PSD 2.0) exige que os compradores online sejam autenticados fora da experiência de compra online quando usam um método de pagamento eletrônico. Durante o fluxo check-out, os clientes são redirecionados para o site de banco. Depois da autenticação, eles são redirecionados novamente para o fluxo de check-out do Commerce. Durante esse redirecionamento, as informações que um cliente inseriu no fluxo de check-out (por exemplo, o endereço de remessa, as opções de entrega, as informações do vale-presente e as informações sobre fidelidade) serão mantidas. Para poder ativar este recurso, o conector de pagamento deve ser configurado para o SCA na sede do Commerce. Para obter mais informações, consulte [Autenticação de Cliente Forte usando Adyen](adyen_redirect.md).

> [!NOTE]
> Para o conector de pagamento da Adyen, o módulo iframe no módulo de pagamento só poderá ser renderizado se você adicionar a URL da Adyen à lista de permissões do seu site. Para concluir esta etapa, adicione **\*.adyen.com** às diretivas **child-src** , **connect-src** , **img-src** , **script-src** e **style-src** da política de segurança de conteúdo do seu site. Para obter mais informações, consulte [Gerenciar a Política de Segurança de Conteúdo](manage-csp.md). 

A ilustração a seguir mostra um exemplo de módulos vale-presente, fidelidade e pagamento em uma página de check-out.

![Exemplo de módulos de vale-presente, fidelidade e pagamento em uma página de check-out](./media/ecommerce-payments.PNG)

## <a name="payment-module-properties"></a>Propriedades de módulo de pagamento

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Cabeçalho | Texto do título | Um título opcional para o módulo de pagamento. |
| Altura do iFrame | Pixels | A altura do iFrame, em pixels. A altura pode ser ajustada conforme necessário. |
| Mostrar o endereço de cobrança | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro** , o endereço de cobrança será fornecido por Adyen no módulo de pagamento iFrame. Se ela estiver definida como **Falso** , o endereço de cobrança não será fornecido por Adyen e um usuário do Commerce deverá configurar um módulo para mostrar o endereço de cobrança na página de check-out. |
| Substituição do estilo de pagamento | Código de folhas de estilo em cascata (CSS) | Como o módulo de pagamento está hospedado em um iFrame, há capacidade de estilo limitada. Você pode obter algum estilo usando essa propriedade. Para substituir estilos de site, você deve colar o código de CSS como o valor dessa propriedade. As substituições e os estilos de criação de sites CSS não se aplicam a este módulo. |

## <a name="billing-address"></a>Endereço para cobrança

O módulo de pagamento permite que clientes forneçam um endereço de cobrança para as informações de pagamento. Ele também permite que eles usem o endereço de remessa como endereço de cobrança para facilitar e agilizar o fluxo de check-out. Se a propriedade **Mostrar endereço de cobrança** for definida como **Falso** , o módulo de pagamento deverá ser configurado na página de check-out.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Adicionar um módulo de pagamento para uma página de check-out e definir as propriedades necessárias

Um módulo de pagamento pode ser adicionado somente a um módulo de check-out. Para obter mais informações sobre como configurar um módulo de pagamento para uma página de check-out, consulte [Módulo de check-out](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de carrinho](add-cart-module.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo do endereço de remessa](ship-address-module.md)

[Módulo de opções de entrega](delivery-options-module.md)

[Módulo de detalhes da ordem](order-confirmation-module.md)

[Módulo de vale-presente](add-giftcard.md)

[Conector de Pagamento do Dynamics 365 para Adyen](dev-itpro/adyen-connector.md)

[Autenticação de Cliente Forte usando o Adyen](adyen_redirect.md)
