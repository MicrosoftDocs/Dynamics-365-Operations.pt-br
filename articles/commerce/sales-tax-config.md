---
title: Configurar o imposto para ordens online
description: Este artigo fornece uma visão geral da seleção do grupo de impostos para diferentes tipos de ordens online no Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: c899bd020ec9536a906a98635a6c70fac1355789
ms.sourcegitcommit: 68efa7b89273d04484566cbe14d3533a8fd4ee53
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2022
ms.locfileid: "9819260"
---
# <a name="configure-sales-tax-for-online-orders"></a>Configurar o imposto para ordens online

[!include [banner](includes/banner.md)]

Este artigo fornece uma visão geral da seleção de grupos de impostos para diferentes tipos de pedidos online usando configurações de imposto baseadas em destino ou em conta de cliente. 

Seu canal de comércio eletrônico pode oferecer suporte a opções como entrega ou retirada para pedidos online. A aplicabilidade do imposto é baseada na opção selecionada por seus clientes online. 

## <a name="destination-based-taxes-for-online-orders"></a>Impostos baseados no destino para pedidos online

Em geral, os impostos para ordens online que enviam para endereços de clientes são definidos pelo destino. Cada grupo de imposto tem uma configuração de imposto baseada no destino de varejo na qual sua empresa pode definir detalhes de destino, como país ou região, estado e cidade de forma hierárquica.

A configuração do **Imposto baseado no destino de varejo** se encontra na seção **Módulo do imposto > Impostos indiretos >Imposto > Grupos de impostos** .

### <a name="orders-delivered-to-customer-address"></a>Pedidos entregues para o endereço de um cliente

Quando um pedido online é realizado, o mecanismo de imposto do Commerce usa o endereço de entrega de cada item de linha no pedido e encontra grupos de impostos com critérios de imposto baseados no destino correspondentes. Por exemplo, em uma ordem online com um endereço de entrega de item de linha para São Francisco (Califórnia), o mecanismo de cálculo de impostos encontrará o grupo de impostos e o código do imposto para a Califórnia e calculará o imposto para cada item de linha apropriadamente.

### <a name="order-pick-up-in-store"></a>Retirada de pedidos na loja

Para linhas de pedidos com retirada na loja ou retirada em frente à loja especificada, o grupo de imposto da loja de retirada selecionada será aplicado. Para obter mais informações sobre como definir os impostos para determinada loja, consulte [Definir outras opções de imposto para lojas](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

## <a name="customer-account-based-taxes-for-online-orders"></a>Impostos baseados na conta de cliente para pedidos online

Pode haver um cenário comercial no qual você deseja definir um grupo de impostos sobre uma conta de cliente específica no Commerce headquarters. Há dois locais no headquarters nos quais é possível definir o imposto sobre uma conta de cliente. Para acessá-los, primeiro é necessário acessar uma página de informações do cliente em **Varejo e comércio \> Clientes \> Todos os clientes** e selecionando um cliente.

Os dois locais nos quais é possível definir o imposto sobre uma conta de cliente são:

- **Grupo de impostos** na FastTab **Fatura e entrega** da página de informações do cliente. 
- **Imposto** na FastTab **Geral** da página **Gerenciar endereços**. Para chegar lá pela página de informações do cliente, selecione um endereço específico na FastTab **Endereços** e selecione **Avançado**.

> [!TIP]
> No caso de pedidos online de clientes, se você quiser aplicar somente os impostos baseados no destino e evitar os impostos baseados na conta de cliente, verifique se o campo **Grupo de impostos** está em branco na FastTab **Fatura e entrega** na página de informações do cliente. Para garantir que os novos clientes que se inscrevam usando o canal online não herdem as configurações do grupo de impostos das configurações de cliente ou grupo de clientes padrão, verifique se o campo **Grupo de impostos** também está em branco para as configurações padrão do cliente do canal online e para as configurações de grupo de clientes (**Varejo e comércio \> Clientes \> Grupos de clientes**).

## <a name="determine-destination-based-tax-or-customer-account-based-tax-applicability"></a>Determinar a aplicabilidade de imposto baseado no destino ou na conta do cliente 

A tabela abaixo explica se os impostos baseados no destino ou os impostos baseados na conta do cliente são aplicados para pedidos online. 

| Tipo de cliente | Endereço de entrega                   | Cliente > Fatura e a entrega > Grupo de impostos? | Endereço da conta do cliente no headquarters? | Endereço do cliente > Avançado > Geral > Grupo de impostos?                                              | Grupo de impostos aplicado      |
|---------------|------------------------------------|-----------------------------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------------|------------------------------|
| Convidado         | Manhattan, NY                      | Não (em branco)                                                | Não (em branco)                              | Não (em branco)                                                                                                   | NY (impostos baseados em destino) |
| Conectado     | Austin, TX                          | Não (em branco)                                             | Sim                               | Nenhuma<br/><br/>Novo endereço adicionado pelo canal online.                                                            | TX (impostos baseados em destino) |
| Conectado     | San Francisco, CA (retirada na loja) | Sim (NY)                                            | Não Aplicável                              | Não Aplicável                                                                                                    | CA (impostos baseados em destino) |
| Conectado     | Houston, TX                         | Sim (NY)                                            | Sim                               | Sim (NY)<br/><br/>Novo endereço adicionado pelo canal online e grupo de impostos herdado da conta do cliente. | NY (impostos baseados na conta do cliente)  |
| Conectado     | Austin, TX                          | Sim (NY)                                            | Sim                               | Sim (NY)<br/><br/>Novo endereço adicionado pelo canal online e grupo de impostos herdado da conta do cliente. | NY (impostos baseados na conta do cliente)  |
| Conectado     | Sarasota, FL                       | Sim (NY)                                            | Sim                               | Sim (WA)<br/><br/>Definido manualmente como WA.                                                                          | WA (impostos baseados na conta do cliente)  |
| Conectado     | Sarasota, FL                       | Não (em branco)                                                | Sim                               | Sim (WA)<br/><br/>Definido manualmente como WA.                                                                          | WA (impostos baseados na conta do cliente)  |

## <a name="additional-resources"></a>Recursos adicionais

[Configurar os impostos para as lojas online baseados no destino](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination)

[Visão geral de imposto](../finance/general-ledger/indirect-taxes-overview.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Métodos de cálculo de impostos no campo de Origem](../finance/general-ledger/sales-tax-calculation-methods-origin-field.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[ Substituições e atribuições de impostos](../supply-chain/procurement/tasks/sales-tax-assignment-overrides.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Opções de cálculo do valor total e do intervalo para códigos de impostos](../finance/general-ledger/whole-amount-interval-options-sales-tax-codes.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Cálculo da isenção de imposto](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
