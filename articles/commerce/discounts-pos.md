---
title: Mostrar descontos no PDV
description: Este artigo explica como o Microsoft Dynamics 365 Commerce ajuda os representantes de vendas a aprender sobre promoções e como elas podem ser usadas para vendas cruzadas e vendas adicionais.
author: ShalabhjainMSFT
ms.date: 07/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-02-28
ms.dyn365.ops.version: Application update 10.0.10
ms.openlocfilehash: e3ec16c5051088ed2777309899b26094e8d67743
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878531"
---
# <a name="show-discounts-in-pos"></a>Mostrar descontos em PDV

[!include [banner](includes/banner.md)]

As promoções exercem um papel importante na motivação de clientes que estão fazendo decisões de compra. Por exemplo, os feriados podem gerar o maior número de vendas para varejistas, pois todo o mercado de varejo é inundado com promoções e descontos atraentes. Se os associados da loja souberem e entenderem as promoções disponíveis, eles poderão aproveitar facilmente as promoções para realizar venda adicional e venda cruzada de itens. Este artigo explica como o Microsoft Dynamics 365 Commerce ajuda os representantes de vendas a aprender sobre promoções e como elas podem ser usadas para vendas cruzadas e vendas adicionais.

## <a name="learn-about-store-discounts"></a>Aprender sobre descontos de armazenamento

O Commerce contém uma operação que é chamada "Exibir todos os descontos". Esta operação mostra todos os descontos que estão em execução no momento em um armazenamento. A operação "Exibir todos os descontos" pode ser mapeada para um botão no ponto de venda (PDV) e esse botão pode ser adicionado à página de **Boas-vindas** ou à página **Transação**. A ilustração a seguir mostra um exemplo da página **Todas os descontos** que é aberta.

![Página Todos os descontos.](./media/View_all_discounts.png "Página Todos os descontos")

Para mostrar os descontos, o sistema procura todos os descontos que correspondam a uma ou mais das seguintes condições:

- O grupo de preços do desconto corresponde ao grupo de preços do armazenamento.
- O grupo de preços do desconto é mapeado para um programa de afiliação ou de fidelidade.
- O grupo de preços do desconto é mapeado para um catálogo associado à loja.

A página **Todos os descontos** mostra apenas alguns descontos baseados em cupom, pois os varejistas normalmente criam milhares de cupons e descontos correspondentes para clientes exclusivos, e essa página não se destina a mostrar descontos específicos do cliente. Os descontos baseados em cupom são mostrados somente se a opção **Aplicar sem um código de cupom** está ativada em cada cabeçalho de cupom. Nesse caso, os caixas podem aplicar o cupom sem a necessidade de inserir ou digitalizar código de cupom ou código de barras.

Quando a opção **Aplicar sem um código de cupom** for ativada, vários cenários estarão disponíveis. Por exemplo, os caixas podem fornecer descontos adicionais aos clientes para fins de pacificação de clientes ou por defeitos de produtos. Os códigos de cupom ou códigos de barras impressos não precisam ser distribuídos para caixas. Em vez disso, os caixas podem selecionar o botão **Aplicar cupom**. O cupom é, então, automaticamente aplicado à transação. Se existirem vários cupons para um cabeçalho de cupom, o sistema selecionará automaticamente o primeiro cupom ativo na transação.

Na página **Todos os descontos**, as vendas associadas também podem pesquisar descontos por palavras-chave. A pesquisa por palavra-chave examina os campos que contêm o nome do desconto e a descrição do desconto. Os associados de vendas também podem filtrar descontos com base no fato de um desconto exigir um código de cupom.

## <a name="cross-sell-and-upsell-by-using-discounts"></a>Vendas cruzadas e venda adicional com descontos

Os descontos combinados, como descontos de quantidade, descontos de compra combinada e descontos de limite, são uma ótima maneira de motivar os clientes a comprar mais produtos para obter descontos maiores. Portanto, eles também ajudam a aumentar o tamanho do carrinho do cliente e da receita varejista. Esses descontos podem ser divulgados em sites de comércio eletrônico, em mídia social e em faixas na loja.

No entanto, mesmo quando todos esses métodos de publicidade são usados, os clientes podem perder a oportunidade de aproveitar as promoções. Para facilitar para que os associados de vendas possam saber quais promoções são aplicáveis a uma linha selecionada, ou mesmo ao carrinho inteiro, os varejistas podem adicionar o botão para a operação **"Exibir descontos disponíveis"** na página **Transação**. Como resultado, uma associação de vendas pode selecionar uma linha de transação e, em seguida, selecionar o botão para mostrar todos os descontos disponíveis para a linha selecionada. O associado de vendas também pode selecionar outra guia para mostrar descontos que se aplicam à transação inteira. É importante observar que a opção **Exibir descontos disponíveis** não mostra os descontos já aplicados na linha de venda porque as informações de desconto já são mostradas na linha de venda. A finalidade desse cenário é mostrar apenas os descontos que ainda não foram aplicados. A exceção a isso é que os descontos aplicados com base em um cupom são marcados como "Aplicar sem um código de cupom". Isso facilita para que a venda associada remova facilmente o cupom que aplicou.

A página **Todos os descontos** mostra apenas descontos que não competem com nenhum dos descontos aplicados. Esse comportamento ajuda a garantir que, se um associado de vendas informar um cliente sobre um desconto e o cliente executar a ação necessária (por exemplo, o cliente compra mais um item para obter 10% desativado), o desconto será aplicado à transação. Os descontos baseados em cupom são mostrados quando a opção **Aplicar sem um código de cupom** está ativada.

Em um cenário simples no qual todos os descontos têm a mesma prioridade, o modo de concorrência de desconto é **Composto**, e o controle de concorrência de desconto é definido como **Melhor preço e composto em prioridade**, nunca composto entre as prioridades, a página **Todos os descontos** mostra os descontos disponíveis para um produto, pois todos os descontos são compostos e não são concorrentes entre si.

As ilustrações a seguir mostram a lógica que determina quais descontos são mostrados em cenários avançados, como um cenário no qual o modo de concorrência de desconto **Melhores práticas** ou **Exclusivo**, e duas ou mais prioridades são usadas. Nessas situações, os descontos mostrados são afetados ainda mais com base no fato de o controle de simultaneidade de desconto ser definido como **Melhor preço e composto na prioridade, nunca composto entre prioridades** ou **Melhor preço apenas dentro da prioridade, sempre composto entre prioridade**.

A ilustração a seguir mostra a lógica usada quando o controle de simultaneidade de desconto é definido como **Melhor preço e composto na prioridade, nunca composto entre as prioridades**.

![A lógica do melhor preço e composto em prioridade, nunca composto entre as prioridades.](./media/Model_1.png "A lógica do melhor preço e composto em prioridade, nunca composto entre as prioridades").

A ilustração a seguir mostra a lógica usada quando o controle de simultaneidade de desconto é definido como **Melhor preço somente dentro da prioridade, sempre composto entre prioridade**.

![A lógica do melhor preço somente dentro de prioridade, sempre comporto entre prioridade.](./media/Model_2.png "A lógica do melhor preço somente dentro de prioridade, sempre comporto entre prioridade").


[!INCLUDE[footer-include](../includes/footer-banner.md)]