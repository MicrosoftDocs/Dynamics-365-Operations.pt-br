---
title: Preço de recebimento fixo
description: Este artigo explica como você pode configurar e usar preços de recebimento fixos no Microsoft Dynamics 365 Supply Chain Management.
author: raprofit
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 2630952f395d1a18202698b4d73b67ef4b760194
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907570"
---
# <a name="fixed-receipt-price"></a>Preço de recebimento fixo

[!include [banner](../includes/banner.md)]

**Preço de recebimento fixo** é uma opção que você pode selecionar em um grupo de modelos de item quando usa um modelo de estoque diferente de *Custo padrão* ou *Média ponderada móvel*. Em versões anteriores do Microsoft Dynamics AX, esta opção era chamada de **Custo padrão**. Ela foi renomeada como **Preço de recebimento fixo** quando o novo modelo de estoque de custo padrão foi apresentado no Dynamics AX 2012. Este artigo explica como você pode configurar e usar preços de recebimento fixos no Dynamics 365 Supply Chain Management.

## <a name="about-fixed-receipt-prices"></a>Sobre preços de recebimento fixos

Quando você marca a caixa de seleção **Preço de recebimento fixo** na página **Grupo de modelos de item** para um item, o sistema usa o preço de recebimento como um custo padrão para o recebimento de estoque. Se o preço de compra e o preço de custo do item padrão configurados para um produto diferirem, a diferença será lançada na conta **Lucro sobre preço de recebimento fixo** e **Perda sobre preço de recebimento fixo**, e compensada na conta **Compensação do preço de recebimento fixo** especificada na página **Perfil de lançamento de estoque**.

Como a opção **Preço de recebimento fixo** é usada junto com modelos de estoque diferentes (como primeiro a entrar, primeiro a sair (PEPS); último a entrar, primeiro a sair (UEPS); e média ponderada), o processo *Fechamento e ajuste de estoque* ainda criará liquidações e ajustes de acordo com o princípio de estoque selecionado na página **Grupo de modelos do item**. No entanto, os ajustes são feitos somente para saídas do estoque.

Por exemplo, você configurou um produto com um grupo de modelos do item no qual o campo **Modelo de estoque** está definido como *PEPS* e a opção **Preço de recebimento fixo** está selecionada. Quando você recebe um estoque por uma ordem de compra, o valor do estoque é definido como o valor do preço de custo padrão no momento do recebimento do produto. Quando você faturar a ordem de compra, se o preço da fatura for diferente, o sistema lançará o preço de custo padrão no produto liberado para a conta de estoque. Ele lança a diferença na conta de lucros ou perdas de preço de recebimento fixo. Posteriormente, quando você vender ou consumir o produto, o sistema usará a média de execução do item no momento em que a fatura da ordem de venda for lançada (a menos que você use a marcação).

Quando você executa o processo *Inventory close and adjustment*, os sistema cria uma liquidação com a primeira saída no primeiro recebimento. A diferença entre o preço de recebimento usado no recebimento e a média em execução que foi usada na saída é lançada em um novo comprovante.

## <a name="enable-fixed-receipt-prices"></a>Habilitar preços de recebimento fixos

Para habilitar preços de recebimento fixos de um item, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Estoque \> Grupos de modelos de item**.
2. Crie um novo grupo de modelos de item, ou selecione um grupo de modelos existente.
3. Na FastTab **Método de avaliação de custo e reconhecimento de custo**, marque a caixa de seleção **Preço de recebimento fixo**.

    > [!NOTE]
    > Não será possível marcar a caixa de seleção **Preço de recebimento fixo** se o campo **Modelo de estoque** estiver definido como *Custo padrão* ou *Média móvel*.

4. Feche a página.

Depois de habilitar a opção **Preço de recebimento fixo**, você deve atualizar seu perfil de lançamentos de estoque seguindo estas etapas.

1. Acesse **Gerenciamento de estoque \> Configurar \> Lançamento \> Lançamento**.
1. Na guia **Ordem de compra**, na coluna **Selecionar**, selecione **Lucro sobre preço de recebimento fixo**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.
1. Configure a nova linha de forma que ela se aplique ao grupo de modelos de item para o qual você habilitou a definição de preços de recebimento fixo e especifique a conta principal que é usada para registrar lucros de preço de recebimento fixo para ordens de compra. Configure outras definições conforme necessário.
1. Na coluna **Selecionar**, selecione **Perda sobre preço de recebimento fixo**. Adicione uma nova linha que se aplique ao grupo de modelos de item para o qual você habilitou a definição de preços de recebimento fixo, e especifique a conta principal que é usada para registrar perdas de preço de recebimento fixo para ordens de compra. Configure outras definições conforme necessário.
1. Na coluna **Selecionar**, selecione **Compensação do preço de recebimento fixo**. Adicione uma nova linha que se aplique ao grupo de modelos de item para o qual você habilitou a definição de preços de recebimento fixo, e especifique a conta principal que é usada para registrar compensações de preço de recebimento fixo para ordens de compra. Configure outras definições conforme necessário.
1. Na guia **Estoque**, na coluna **Selecionar**, selecione **Lucro sobre preço de recebimento fixo**. Adicione uma nova linha que se aplique ao grupo de modelos de item para o qual você habilitou a definição de preços de recebimento fixo, e especifique a conta principal que é usada para registrar lucros de preço de recebimento fixo para estoque. Configure outras definições conforme necessário.
1. Na coluna **Selecionar**, selecione **Perda sobre preço de recebimento fixo**. Adicione uma nova linha que se aplique ao grupo de modelos de item para o qual você habilitou a definição de preços de recebimento fixo, e especifique a conta principal que é usada para registrar perdas de preço de recebimento fixo para estoque. Configure outras definições conforme necessário.

> [!NOTE]
> É recomendável que os campos **Lucro sobre preço de recebimento fixo** e **Perda sobre preço de recebimento fixo** usem a mesma conta principal para ordens de compra e estoque.

> [!IMPORTANT]
> Quando você altera o valor no campo **Preço** na FastTab **Gerenciar custos** da página **Produtos liberados**, o sistema não reavalia automaticamente o estoque disponível. Como solução manual, abra a página **Fechamento e ajuste** e selecione **Ajuste \> Disponível** no Painel de Ações. Selecione os itens disponíveis e ajuste-os ao preço atual. Uma vantagem clara de usar o modelo de estoque de custo padrão é que leva o sistema a reavaliar automaticamente o estoque disponível.
