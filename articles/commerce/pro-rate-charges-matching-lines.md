---
title: Realizar rateio de alterações de cabeçalho para linhas de vendas correspondentes
description: Este tópico descreve recursos adicionais para calcular e aplicar encargos automáticos dos pedidos de canal do Commerce usando o recurso de encargos automáticos avançado.
author: hhaines
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0de29e1817840c172f9235f2ee48251c4878a0573d270a60fde5b42ba6f88d31
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774500"
---
# <a name="prorate-header-charges-to-matching-sales-lines"></a>Realizar rateio de alterações de cabeçalho para linhas de vendas correspondentes


[!include [banner](includes/banner.md)]

Este tópico descreve a funcionalidade para agrupar encargos automáticos em nível de cabeçalho e realizar rateio dela para as linhas de venda do Commerce. Esta funcionalidade ficará disponível para transações criadas no ponto de venda (POS) na versão 10.0.1 do Retail e vendas criadas em um call center na versão 10.0.2 do Retail.

Esta funcionalidade só estará disponível se o recurso [encargos automáticos avançados](/dynamics365/unified-operations/retail/omni-auto-charges) estiver ativado usando a opção na página **Parâmetros do Commerce**. Além disso, o método de cálculo avançado para encargos automáticos pode ser aplicado apenas a ordens de venda de varejo criadas por meio de canais de comércio (o PDV, um call center, e a plataforma do Dynamics e-Commerce).

Essa nova funcionalidade dá às organizações mais flexibilidade na forma em que os encargos automáticos de nível de cabeçalho são calculados e aplicados para transações de vendas.

Em versões do aplicativo anteriores à versão 10.0.1, os encargos automáticos de nível de cabeçalho que têm um modo específico de relação de entrega são calculados apenas quando há uma combinação com o modo de entrega definido no cabeçalho da ordem de venda.

Por exemplo, encargos automáticos de nível de cabeçalho são definidos para modo de entrega **99** e modo de entrega **11**. Uma ordem de venda é criada e o modo de entrega **99** é definido no cabeçalho da ordem. Porém, algumas linhas de venda são configuradas de forma que sejam enviadas com o modo de entrega **11**. Neste caso, somente os encargos de nível de cabeçalho vinculados ao modo de entrega **99** são considerados e aplicados à ordem de vendas.

No Commerce, os encargos de nível de cabeçalho têm um recurso adicional que permite definir uma [configuração de encargo em camadas](/dynamics365/unified-operations/retail/configure-call-center-delivery) que é baseada no valor da ordem. Por exemplo, se o valor da ordem está entre US$ 50,00 e US$ 200,00 uma organização pode cobrar US$ 5,00 de frete. Entretanto, se o valor da ordem estiver entre US$ 200,01 e US$ 500,00, o encargo de frete pode ser US$ 4,00.

Algumas organizações desejam os benefícios de cálculo de encargo em camadas fornecido com encargos de nível de cabeçalho. Entretanto, em cenários envolvendo modes mistos de entrega, eles também desejam garantir que os encargos são calculados com base em uma correspondência com o modo de entrega definido em cada linha de vendas.

Agora você pode configurar encargos automáticos de nível de cabeçalho para que todos os modos de entrega na ordem sejam considerados quando encargos são calculados. Esta funcionalidade requer uma lógica de cálculo mais complexa para calcular os encargos de nível de cabeçalho. A lógica agrupa todos os itens enviados usando o mesmo modo de entrega, e trata esse grupo como o grupo de cálculo dos itens quando calcula os encargos automáticos de nível de cabeçalho. Para itens que têm o mesmo modo de entrega, encargos automáticos são calculados com base no valor de vendas combinado dos itens. Assim, a camada de encargo automático apropriada é determinada.

Depois que os encargos de nível de cabeçalho apropriados são obtidos para linhas de vendas enviadas usando o mesmo modo de entrega, os encargos calculados são rateados para o nível de linha de vendas. Como esses encargos estão no nível de linha e não mantidos no nível de cabeçalho, um vínculo mais específico é estabelecido entre o item e o valor do encargo calculado para ele. Esse comportamento pode ser útil nos cenários de devolução parciais, onde a organização deseja devolver apenas parte do encargo em vez do encargo inteiro quando apenas alguns itens são devolvidos.

## <a name="scenarios"></a>Cenários

Os dois cenários de exemplo a seguir destacam como esses encargos são calculados quando a nova funcionalidade é usada e quanto não é.

### <a name="scenario-1"></a>Cenário 1

Este cenário destaca o comportamento quando a opção **Pró-rateio para correspondência de linhas de vendas** é definida como **Não** na configuração de encargo automático. (O comportamento é equivalente ao comportamento dos encargos de nível de cabeçalho nas versões do aplicativo anteriores à versão 10.0.1.)

Neste cenário, a organização definiu os encargos de nível de cabeçalho para modo de relação de entrega **99** e modo de relação de entrega **11**. Nenhum encargo automático é configurado para modo de entrega **21**.

![Encargos automáticos para modo de entrega 99 na correspondência de pró-rateio de linha está desligado.](media/99_disabled.png)

![Encargos automáticos para modo de entrega 11 na correspondência de pró-rateio de linha está desligado.](media/11_disabled.png)

Uma ordem de venda é criada no call center, e o modo de entrega será **99**. Essa ordem contém cinco itens. Duas linhas de ordem foram configuradas para usar modo de entrega **99**, duas linhas foram configuradas para usar modo de entrega **11**, e uma linha foi configurada para usar modo de entrega **21**, como exibido na tabela a seguir.

| Item  | Quantidade da linha | Modo de entrega | Preço unitário |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | US$ 10            |
| 81332 | 1             | 99            | $50            |
| 81333 | 2             | 11            | US$ 30            |
| 81334 | 3             | 99            | US$ 10            |
| 81334 | 3             | 21            | US$ 5             |

Neste cenário, a ordem inteira é avaliada em relação à tabela de encargos para modo de entrega **99**. O total completo de todas as linhas de vendas é usado para determinar uma camada correspondente na configuração de encargo automático, e esse encargo é aplicado no nível de cabeçalho da ordem. Neste exemplo, o total da ordem é de US$ 165,00 e o frete de US$ 15,00 é aplicado ao cabeçalho da ordem. Encargos automáticos que são configurados para modo de entrega **11** nunca são referenciados ou aplicados.

Neste cenário, se um cliente devolver alguns dos itens na ordem, e se o [código de encargo foi configurado para que ele seja reembolsado](/dynamics365/unified-operations/retail/omni-auto-charges#setup-and-configuration-2), o encargo de nível de cabeçalho total é sistematicamente aplicado para o reembolso, mesmo se apenas alguns dos itens são devolvidos.

### <a name="scenario-2"></a>Cenário 2

Neste cenário, os encargos de nível de cabeçalho são definidos para modo de relação de entrega **99** e modo de relação de entrega **11**. No entanto, a opção **Pró-rateio para correspondência de linhas de vendas** é definida como **Sim** para essas tabelas de encargo automático.

![Encargos automáticos para modo de entrega 99 na correspondência de pró-rateio de linha está ligado.](media/99_enabled.png)

![Encargos automáticos para modo de entrega 11 na correspondência de pró-rateio de linha está ligado.](media/11_enabled.png)

Esse cenário usa a mesma ordem de venda que contém cinco linhas. O modo de entrega no cabeçalho de ordem é definido como **99**, mas o modo de entrega para cada item na ordem de vendas é configurado como exibido na tabela a seguir.

| Item  | Quantidade da linha | Modo de entrega | Preço unitário |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | US$ 10            |
| 81332 | 1             | 99            | $50            |
| 81333 | 2             | 11            | US$ 30            |
| 81334 | 3             | 99            | US$ 10            |
| 81334 | 3             | 21            | US$ 5             |

Como a configuração de encargos automáticos é definida para pró-rata de linhas de vendas correspondente, o sistema realiza as etapas de cálculo a seguir.

1. Todos os itens com o mesmo modo de entrega são agrupados juntos, e o sistema calcula o valor do produto total dos itens no grupo.

    **Modo de Entrega 11**

    - Item 81331, quantidade 1 = US$ 10
    - Item 81333, quantidade 2 = US$ 60 líquido (US$ 30 por unidade)
    - **Valor de produto total para modo de entrega 11 = US$ 70**

    **Modo de Entrega 99**

    - Item 81332, quantidade 1 = US$ 50
    - Item 81334, quantidade 3 = US$ 30 líquido
    - **Valor de produto total para modo de entrega 99 = US$ 80**

    **Modo de Entrega 21**

    - Item 81334, quantidade 3 = US$ 15 líquido
    - **Valor de produto total para modo de entrega 21 = US$ 15**

2. O sistema procura pela configuração dos encargos automáticos de nível de cabeçalho que corresponde às configurações do cliente e modo de entrega de cada grupo de itens. Se a configuração for encontrada, o sistema busca na configuração em camadas o encargo que deve ser aplicado, com base no valor de produto total de itens no modo de grupo de entrega.

    **Modo de Entrega 11**

    - Valor de produto total = US$ 70
    - **Valor do encargo = US$ 7**

    **Modo de Entrega 99**

    - Valor de produto total = US$ 80
    - **Valor do encargo = US$ 15**

    **Modo de Entrega 21**

    - Valor de produto total = US$ 15
    - **Valor do encargo = $0** (Nenhum encargo automático foi configurado para essa combinação de um cliente e um modo de entrega.)

    ![Encargos de modo de entrega 11 caem na camada destacada.](media/step2mode11.png)

    ![Encargos de modo de entrega 99 caem na camada destacada.](media/step2mode99.png)

3. O sistema calcula o valor do encargo que deve ser aplicado a cada linha, baseado na lógica de pró-rata que considera o valor proporcional da linha em relação ao valor de produto total do grupo.

    **Modo de Entrega 11**

    - Valor do encargo = US$ 7
    - Valor de produto do grupo = US$ 70
    - Valor da linha 1 = US$ 10 (= 14,2857% do valor do grupo)
    - Valor da linha 3 = US$ 60 (= 85,7143% do valor do grupo)
    - **Encargo de linha para linha 1 = US$ 1**
    - **Encargo de linha para linha 3 = US$ 6**

    **Modo de Entrega 99**

    - Valor do encargo = US$ 15
    - Valor de produto do grupo = US$ 80
    - Valor da linha 2 = US$ 50 (= 62,5% do valor do grupo)
    - Valor da linha 4 = US$ 30 (= 37,5% do valor do grupo)
    - **Encargo de linha para linha 2 = US$ 9,38**
    - **Encargo de linha para linha 4 = US$ 5,62**

    **Modo de Entrega 21**

    - Valor do encargo = US$ 0
    - Valor de produto do grupo = US$ 15
    - Valor da linha 5 = US$ 15 (= 100% do valor do grupo)
    - **Encargo de linha para linha 5 = US$ 0**

Portanto, neste exemplo, o item 81334 será atribuído ao encargo de frete de US$ 5,62. Você pode exibir esses encargos na página **Manter encargos** da linha de vendas. A ilustração a seguir mostra como essa página se parece para o item 81334.

![Encargos em pró-rata sobre vendas para o item 81334.](media/proratedlinecharge.png)

Quando esse método de cálculo é usado em um cenário de devolução parcial, se o código de encargo é reembolsável, apenas a parte do encargo atribuído a essa linha será reembolsado quando o item é devolvido.

## <a name="additional-resources"></a>Recursos adicionais

[Encargos automáticos avançados de omnicanal](omni-auto-charges.md)

[Habilitar e configurar encargos automáticos por canal](auto-charges-by-channel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]