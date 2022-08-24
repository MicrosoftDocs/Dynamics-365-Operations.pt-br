---
title: Cálculo de atraso do preço exato e cálculo de desconto para melhorar o desempenho
description: Este artigo descreve a capacidade de cálculo de atraso do preço que está disponível no PDV (ponto de venda) do Microsoft Dynamics 365 Commerce e no Call Center.
author: boycezhu
ms.date: 09/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 66c7c5a61648ba0423b27b74a1c4e42bc1b22b8b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267581"
---
# <a name="delay-exact-price-and-discount-calculation-for-improved-performance"></a>Cálculo de atraso do preço exato e cálculo de desconto para melhorar o desempenho

[!include [banner](includes/banner.md)]

Este artigo descreve a capacidade de cálculo de atraso do preço que está disponível no PDV (ponto de venda) do Microsoft Dynamics 365 Commerce e no Call Center.

O Dynamics 365 Commerce oferece suporte à criação de descontos combinados que são aplicados quando várias linhas de venda de uma ordem de venda ou cotação de venda são combinadas. Esses descontos incluem descontos de compra combinada e de correspondência, de limite e de quantidade.

Sempre que uma nova linha for adicionada a uma ordem, o mecanismo de preços do Commerce avaliará o carrinho inteiro para determinar se qualquer um desses descontos combinados pode ser aplicado. Por causa desse recálculo, a adição de novas linhas pode afetar o desempenho à medida que a ordem de venda cresce.

No entanto, as empresas B2B (Business-to-Business) e algumas empresas de business-to-consumer (B2C) geralmente têm grandes tamanhos de ordem. Portanto, pode ser demorado esperar o mecanismo de precificação recalcular após cada item ser adicionado ao carrinho. Além disso, para ordens grandes, normalmente não é muito importante que o preço e o desconto exatos sejam mostrados sempre que um item for adicionado ao carrinho. É mais importante que os usuários possam adicionar itens rapidamente. A capacidade de atrasar o cálculo de preço e desconto exato até que um usuário solicite-o ou que uma ordem seja finalizada pode melhorar significativamente o desempenho. Ele também pode reduzir o tempo necessário para concluir a inserção de uma ordem.

A capacidade de atrasar o cálculo de preço e desconto está disponível há muito tempo no PDV. A partir da versão 10.0.22 do Commerce, ela também está disponível para call center.

## <a name="enable-delayed-price-and-discount-calculation-for-pos"></a>Habilitar cálculo de preço e desconto atrasados para PDV

Para habilitar cálculo de preço e desconto atrasados para PDV, siga estas etapas.

1. No Commerce headquarters, vá para o perfil de funcionalidade associado ao armazenamento físico.
1. Na Guia Rápida **Valor**, habilite a configuração **Calcular manualmente descontos de vários itens**.
1. Abra o designer do layout de tela para os registros nos quais o cálculo atrasado deve ser habilitado.
1. Adicione um botão para a operação **Calcular total** para a grade de botões desejada.
1. Execute os trabalhos **1070** e **1090**.

Agora, quando os itens são adicionados a uma transação, os descontos combinados não são calculados a menos que o caixa selecione o botão **Calcular total**. Depois que **Calcular total** for selecionado para uma transação, os descontos combinados sempre serão calculados para ele. O caixa não terá que selecionar o botão novamente, mesmo que itens adicionais sejam adicionados ao carrinho. O sistema não permite que o caixa capture o pagamento até que a opção **Calcular total** seja selecionada.

## <a name="enable-delayed-price-and-discount-calculation-for-call-center"></a>Habilitar cálculo de preço e desconto atrasados para call center

Para habilitar cálculo de preço e desconto atrasados para call center, siga estas etapas.

1. No Commerce headquarters, vá para **Espaços de trabalho \> Gerenciamento de recursos**.
1. Habilite o recurso **Impedir o cálculo de preço não intencional para ordens comerciais**. Este recurso é um pré-requisito para a capacidade de cálculo de preço e desconto atrasado.

    > [!NOTE]
    > Para novas implantações, o recurso **Impedir o cálculo de preço não intencional para ordens comerciais** é habilitado por padrão.

1. Vá para **Parâmetros do Commerce \> Preços e descontos**.
1. Na seção **Diversos**, habilite a configuração **Calcular manualmente preços e descontos de várias linhas**.

Agora, quando uma ordem de venda ou cotação de venda é criada ou editada no call center, o preço exato e o cálculo do desconto são atrasados. O mecanismo de preços considerará somente a linha de venda que está sendo adicionada ou editada e ignorará todas as outras linhas de venda. O valor líquido de um item inclui o cálculo de preços e os descontos simples (porcentagem ou valor de desconto em um item individual). No entanto, os descontos de compra combinada e de correspondência, de limite e de quantidade não serão aplicados. Os usuários do Call Center que desejam exibir o preço exato, incluindo todos os descontos, podem selecionar um dos três botões: **Recalcular**, **Totais** ou **Concluir**.

> [!NOTE]
> Para ordens de call center, o sistema mostra uma mensagem de aviso para lembrar ao usuário que eles devem selecionar o botão **Recalcular**, **Totais** ou **Concluir** para que seja executado o cálculo de preço exato e de desconto. Para ordens nos quais o botão **Concluir** está disponível, não há como o usuário do call center omitir o preço exato e o cálculo do desconto, pois ele deve selecionar **Concluir** para concluir a captura da ordem. Para ordens nas quais o botão **Concluir** não está disponível, não há ação que indique a conclusão da captura da ordem. Portanto, o usuário do call center é responsável por selecionar **Recalcular** ou **Totais** antes de concluir a captura da ordem.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
