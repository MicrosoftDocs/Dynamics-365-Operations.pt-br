---
title: Módulo de pagamento
description: Este tópico abrange o módulo do pagamento e explica como configurá-lo no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 11/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 303b5f0bdfdb00accab2598acc2545bca69660412e170202152303c8ed81314e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774548"
---
# <a name="payment-module"></a>Módulo de pagamento

[!include [banner](includes/banner.md)]

Este tópico abrange o módulo do pagamento e explica como configurá-lo no Microsoft Dynamics 365 Commerce.

O módulo de pagamento permite que clientes paguem por pedidos usando cartões de crédito ou de débito. A integração de pagamento para este módulo é fornecida pelo Conector de Pagamento do Dynamics 365 para Adyen. Para obter mais informações sobre como configurar o conector de pagamento, consulte [Conector de Pagamento do Dynamics 365 para Adyen](dev-itpro/adyen-connector.md).  

A partir do Commerce versão 10.0.14, o módulo de pagamento também foi integrado ao Conector de Pagamento do Dynamics 365 para PayPal a fim de permitir que os clientes paguem ordens usando o PayPal. Para obter mais informações sobre como configurar o Conector de Pagamento do Dynamics 365 para PayPal, consulte [Conector de Pagamento do Dynamics 365 para PayPal](paypal.md). 

## <a name="dynamics-365-payment-connector-for-adyen"></a>Conector de Pagamento do Dynamics 365 para Adyen 

O módulo de pagamento hospeda as informações de pagamento fornecidas por meio de Adyen em um quadro embutido em HTML (iFrame). O módulo de pagamento interage com a Commerce Scale Unit para recuperar as informações de pagamento de Adyen. Como parte da interação da Commerce Scale Unit, o módulo de pagamento pode permitir que as informações de endereço de cobrança sejam fornecidas no iFrame via Adyen ou como um módulo separado. No tema Fabrikam, o endereço de cobrança é habilitado como um módulo separado. Essa abordagem permite mais flexibilidade de formatação porque as linhas de endereço podem ser processadas para que se pareçam com as linhas do endereço de remessa.

O módulo de pagamento também permite que os clientes conectados salvem informações de pagamento. As informações de pagamento e o endereço de cobrança são salvos e gerenciados pelo conector de pagamento Adyen.

O módulo de pagamento cobre todos os encargos de ordem que ainda não foram cobertos por pontos de fidelidade ou um vale-presente. Se o total de uma ordem for totalmente abrangido por pontos de fidelidade ou créditos de vale-presente, o módulo de pagamento ficará oculto e o cliente poderá fazer o pedido sem ele.

O conector de pagamento de Adyen também dá suporte à Autenticação de Cliente Forte (SCA). Parte da Diretiva de Serviços de Pagamento Revisada (PSD2) da União Europeia (UE) exige que os compradores online sejam autenticados fora da experiência de compra online quando usarem um método de pagamento eletrônico. Durante o fluxo de finalização de compra, os clientes são redirecionados para o site do banco e, após a autenticação, são redirecionados de volta para o fluxo de finalização de compra do Commerce. Durante esse redirecionamento, as informações que um cliente inseriu ao longo do fluxo de finalização de compra (por exemplo, endereço de remessa, opções de entrega, informações do vale-presente e informações de fidelidade) serão mantidas. Para ativar o recurso Conector de pagamento Adyen, o conector de pagamento deverá ser configurado para o SCA na sede do Commerce. Para obter mais informações, consulte [Autenticação de Cliente Forte usando Adyen](adyen_redirect.md). Esse recurso foi habilitado no Commerce versão 10.0.12.

> [!NOTE]
> Para o conector de pagamento da Adyen, o módulo iframe no módulo de pagamento só poderá ser renderizado se você adicionar a URL da Adyen à lista de permissões do seu site. Para concluir esta etapa, adicione **\*.adyen.com** às diretivas **child-src**, **connect-src**, **img-src**, **script-src** e **style-src** da política de segurança de conteúdo do seu site. Para obter mais informações, consulte [Gerenciar a Política de Segurança de Conteúdo](manage-csp.md). 

A ilustração a seguir mostra um exemplo dos módulos de pagamento vale-presente, fidelidade e Adyen em uma página de finalização de compra.

![Exemplo dos módulos de pagamento vale-presente, fidelidade e Adyen em uma página de finalização de compra.](./media/ecommerce-payments.PNG)

## <a name="dynamics-365-payment-connector-for-paypal"></a>Dynamics 365 Payment Connector para PayPal

A partir do Commerce versão 10.0.14, o módulo de pagamento também foi integrado ao Conector de Pagamento do Dynamics 365 para PayPal. Para obter mais informações sobre como configurar esse conector de pagamento, consulte [Conector de Pagamento do Dynamics 365 para PayPal](paypal.md).
 
Na página de finalização de compra, você pode ter os conectores Adyen e PayPal configurados. O módulo de pagamento foi aprimorado com propriedades adicionais para ajudar a identificar com qual conector ele deve trabalhar. Para obter detalhes, consulte as propriedades de módulo **Tipos de meio de pagamento com suporte** e **É pagamento principal** na tabela a seguir.
  
Quando o módulo de pagamento for configurado para usar o conector de pagamento PayPal, um botão PayPal aparecerá na página de finalização de compra. Quando invocado pelo cliente, o módulo de pagamento renderiza um iFrame que contém informações do PayPal. O cliente pode entrar e fornecer suas informações do PayPal nesse iFrame para concluir a transação. Quando um cliente optar por pagar com o PayPal, o saldo restante na ordem será cobrado via PayPal.

O conector de pagamento PayPal não requer um módulo de endereço de cobrança porque todas as informações relacionadas à cobrança são tratadas pelo PayPal em seu iFrame. No entanto, os módulos de endereço de remessa e opções de entrega são necessários.

A ilustração a seguir mostra um exemplo de dois módulos de pagamento em uma página de finalização de compra, um configurado com o conector de pagamento Adyen e o outro com o conector de pagamento PayPal.
![Exemplo de módulos de pagamento com Adyen e PayPal em uma página de finalização de compra.](./media/ecommerce-paypal.png)

A ilustração a seguir mostra um exemplo do iFrame do PayPal invocado usando o botão PayPal. 
![Exemplo de iFrame do Paypal em uma página de finalização de compra.](./media/ecommerce-paypal-iframe.png)

## <a name="payment-module-properties"></a>Propriedades de módulo de pagamento

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Cabeçalho | Texto do título | Um título opcional para o módulo de pagamento. |
| Altura do iFrame | Pixels | A altura do iFrame, em pixels. A altura pode ser ajustada conforme necessário. |
| Mostrar o endereço de cobrança | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, o endereço de cobrança será fornecido por Adyen no módulo de pagamento iFrame. Se for definida como **Falso**, o endereço de cobrança não será fornecido por Adyen e um usuário do Commerce deverá configurar um módulo para mostrar o endereço de cobrança na página de finalização de compra. Para o conector de pagamento PayPal, esse campo não tem impacto, pois o endereço de cobrança é totalmente tratado no PayPal. |
| Substituição do estilo de pagamento | Código de folhas de estilo em cascata (CSS) | Como o módulo de pagamento está hospedado em um iFrame, há capacidade de estilo limitada. Você pode obter algum estilo usando essa propriedade. Para substituir estilos de site, você deve colar o código de CSS como o valor dessa propriedade. As substituições e os estilos de criação de sites CSS não se aplicam a este módulo. |
|Tipos de meio de pagamento com suporte| Sequência de caracteres| Se vários conectores de pagamento estiverem configurados, você deverá fornecer a cadeia de caracteres do tipo de meio de pagamento com suporte, conforme definido na configuração do conector de pagamento na sede do Commerce (consulte a seguinte imagem). Se estiver em branco, o padrão será o conector de pagamento Adyen. Adicionado ao Commerce Release 10.0.14.|
|É pagamento principal|  **Verdadeiro** ou **Falso** | Se **Verdadeiro**, as mensagens de erro serão geradas a partir do conector de pagamento principal na página de finalização de compra. Se os conectores de pagamento Adyen e PayPal estiverem configurados, defina Adyen como **Verdadeiro**, que foi adicionado no Commerce versão 10.0.14.|

A ilustração a seguir mostra um exemplo do valor **Tipos de meio de pagamento com suporte** definido como "PayPal" na configuração do conector de pagamento na sede do Commerce.
![Exemplo de tipos de meio de pagamento com suporte na sede do Commerce.](./media/ecommerce-paymenttendertypes.png)

## <a name="billing-address"></a>Endereço para cobrança

Um módulo de endereço de cobrança poderá ser usado na página de finalização de compra se as linhas do endereço de cobrança do conector de pagamento Adyen não corresponderem suficientemente à aparência do restante do site. 

Para usar um módulo de endereço de cobrança na página de finalização de compra quando o módulo de pagamento estiver integrado ao conector de pagamento Adyen, defina a propriedade **Mostrar endereço de cobrança** como **Falso** para que um módulo de endereço de cobrança dedicado possa ser usado em vez do endereço de cobrança Adyen padrão. Nesse caso, o autor do site deve incluir um módulo de endereço de cobrança na página de finalização de compra. O conector de pagamento Adyen também permite usar o endereço de remessa como endereço de cobrança a fim de minimizar o número de etapas para o usuário do site.

Semelhante aos módulos de pagamento, uma propriedade **Tipos de meio de pagamento com suporte** foi adicionada ao módulo de endereço de cobrança no Commerce versão 10.0.14. O valor dessa propriedade deve ser idêntico ao valor fornecido no módulo de pagamento para garantir que funcionem juntos. Para o conector de pagamento Adyen, o módulo de pagamento e o módulo de endereço de cobrança devem deixar esse valor em branco (o estado padrão). Para o conector PayPal, não é necessário um módulo de endereço de cobrança dedicado. Para outros tipos de conectores de pagamento, a cadeia de caracteres deve ser fornecida conforme configurado na sede do Commerce.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Adicionar um módulo de pagamento para uma página de check-out e definir as propriedades necessárias

Um módulo de pagamento pode ser adicionado somente a um módulo de check-out. Para obter mais informações sobre como configurar um módulo de pagamento para uma página de check-out, consulte [Módulo de check-out](add-checkout-module.md).

Se os conectores de pagamento Adyen e PayPal forem necessários, adicione os dois módulos à seção de pagamento. Verifique se o valor da propriedade **Tipos de meio de pagamento com suporte** está configurado para PayPal e deixe-o em branco para Adyen. Além disso, defina a propriedade **É pagamento principal** como **Verdadeiro** para Adyen.

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de carrinho](add-cart-module.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de endereço de remessa](ship-address-module.md)

[Módulo de opções de entrega](delivery-options-module.md)

[Módulo de informações sobre retirada](pickup-info-module.md)

[Módulo de detalhes da ordem](order-confirmation-module.md)

[Módulo de cartão-presente](add-giftcard.md)

[Conector de Pagamento do Dynamics 365 para Adyen](dev-itpro/adyen-connector.md)

[Conector de Pagamento do Dynamics 365 para PayPal](paypal.md)

[Autenticação de Cliente Forte usando o Adyen](adyen_redirect.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]