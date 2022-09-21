---
title: Desconto de remessa
description: Este artigo descreve as capacidades de desconto de remessa no Microsoft Dynamics 365 Commerce e a configuração necessária para usá-los.
author: ShalabhjainMSFT
ms.date: 08/23/2020
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2019-01-31
ms.openlocfilehash: 74cfe5246ad72cbdedd0ed4e3b3394bf7277919e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473841"
---
# <a name="shipping-discount"></a>Desconto de remessa

[!include [banner](includes/banner.md)]

Este artigo descreve as capacidades de desconto de remessa no Microsoft Dynamics 365 Commerce e a configuração necessária para usá-los.

A remessa gratuita ou com desconto é um fator que influencia as decisões de compra online dos clientes. Para aumentar a receita por transação, diversos varejistas usam uma vantagem de entrega gratuita para motivar os clientes a aumentar o tamanho do carrinho.

O Commerce oferece suporte a um recurso de desconto de remessa que permite aos varejistas configurar um percentual de desconto sobre os encargos de remessa para um método de remessa específico, quando o valor total de vendas para itens qualificados na transação atende aos critérios específicos. Um exemplo de cenário que usa o recurso de desconto de remessa é "Gaste US$ 50 ou mais para obter entrega gratuita durante a noite".

## <a name="prerequisites"></a>Pré-requisitos

A capacidade de desconto de remessa tem suporte dos recursos de [encargos automáticos avançados do omnicanal](/dynamics365/unified-operations/retail/omni-auto-charges) do Commerce. Para que a capacidade de desconto de remessa funcione, você deve habilitar a configuração **Usar encargos automáticos avançados** na guia **Ordens do cliente** da página **Parâmetros do Commerce** no Commerce Headquarters. Os varejistas podem usar o recurso de encargos automáticos avançados para configurar vários tipos de encargos, como manuseio, instalação e alienação.

O desconto de remessa é aplicado apenas aos encargos de remessa. Portanto, um varejista deve especificar quais encargos são encargos de remessa. Para especificar os encargos de remessa, no Commerce headquarters, vá para **Configuração do canal \> Encargos \> Código de encargos** e defina a opção **Encargo de remessa** como **Sim** para os encargos desejados.

![Como especificar um encargo como encargo de remessa.](./media/Specify_shipping_charge.png)

## <a name="configuration"></a>Configuração

A capacidade de desconto de remessa baseia-se em camadas e oferece suporte somente ao tipo de cálculo **Porcentagem deduzida**. Para configurar um desconto de remessa, no Commerce Headquarters, vá até **Preços e descontos \> Desconto limite de remessa**. Em seguida, você poderá especificar o modo de entrega ao qual o desconto se aplica, definir um ou mais limites de valor e definir a porcentagem de desconto para cada limite. Você também pode configurar uma lista de categorias ou produtos como itens qualificados. Dessa forma, somente o valor de venda contra esses itens em uma transação será contado quando o mecanismo de precificação avaliar se o total da transação atende ao limite.

> [!NOTE]
> Diferentemente de outros tipos de desconto, o desconto de remessa não cria linhas de desconto. Em vez disso, ele edita diretamente o encargo de remessa e anexa o nome do desconto à descrição do encargo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
