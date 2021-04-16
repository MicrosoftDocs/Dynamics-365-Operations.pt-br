---
title: Fechamento de estoque
description: Como parte do processo para liquidar transações de saída com transações de recebimento, você também optar por atualizar a contabilidade para refletir os ajustes feitos.
author: AndersGirke
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61973
ms.assetid: c210c882-6849-4704-b78c-a777dd6cfdb6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d55ee9a851e2a7bfbba7d60b0b1fc774c4f6c170
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830307"
---
# <a name="inventory-close"></a>Fechamento de estoque

[!include [banner](../includes/banner.md)]

Como parte do processo para liquidar transações de saída com transações de recebimento, você também optar por atualizar a contabilidade para refletir os ajustes feitos.

O processo de fechamento de estoque liquida transações de saída para transações de recebimento com base no método de avaliação do estoque selecionado no grupo de modelos do item. Como parte do processo de liquidação, você pode especificar que a contabilidade deva ser atualizada de modo que reflita os ajustes feitos. Entretanto, até que o fechamento ou o recálculo do estoque tenha sido executado, as transações de saída serão lançadas ao preço de custo médio calculado. 

Após o fechamento do estoque, você não poderá mais lançar em períodos antes da data de fechamento do estoque definida, a menos que você reverta um processo de fechamento de estoque concluído. Por exemplo, se o fechamento de estoque for executado para o período que termina em 31 de janeiro, você não poderá lançar transações que têm uma data anterior a 31 de janeiro. 

Os itens no estoque são atribuídos a um dos dois tipos de estoque: item ou serviço. O fechamento de estoque executa as mesmas funções para os dois tipos. No entanto, para itens de serviço, o fechamento de estoque ainda liquida saída para recebimentos. 

A frequência com que o processo de fechamento de estoque é executado varia por empresa. No entanto, o volume da transação deve ajudar a determinar com que frequência você executará o fechamento de estoque. Em geral, a maioria das empresas executa o fechamento de estoque como parte dos procedimentos de reconciliação e fechamento de fim de mês.

## <a name="inventory-recalculation-and-the-general-ledger"></a>Recálculo do estoque e a contabilidade
Se forem necessários ajustes ao estoque e à contabilidade durante um mês ou outro período de estoque, você poderá executar o recálculo do estoque em vez do fechamento. O recálculo do estoque faz ajustes, mas não faz liquidações nas transações de estoque. 

Durante o recálculo do estoque, o estoque disponível é ajustado, as transações de estoque são ajustadas, e os recálculos do estoque e fechamento do estoque são executados. Essas tarefas afetam a conta contábil que está vinculada à transação de estoque original. 

**Exemplo** 

Quando você cria uma ordem de compra a partir de uma ordem de venda, as contas contábeis usadas para a ordem de venda original são atualizadas. Mesmo se as contas contábeis para o grupo do item atribuído a esse item tiverem sido alteradas depois do lançamento da ordem de compra e um recálculo do estoque criar um valor de ajuste, o valor de ajuste é postado para a conta contábil original. O valor ajustado não é lançado para as novas contas contábeis atribuídas ao item. 

Depois que a atualização é concluída, você pode revisar o comprovante do razão lançado por causa de uma dessas tarefas.

1.  Na página **Fechamento e ajuste**, na guia **Visão geral**, selecione a atualização para rever.
2.  Clique em **Detalhes**, e então selecione **Comprovante**.

## <a name="effects-of-the-inventory-close-process-on-the-general-ledger"></a>Efeitos do processo de fechamento do estoque na contabilidade
Várias tarefas que podem ser executadas da página **Fechamento e ajuste** causam uma atualização na contabilidade. Por exemplo, a contabilidade é atualizada quando você faz ajustes no estoque disponível, faz ajustes de transação de estoque, executa novos cálculos de estoque e executa o fechamento de estoque. 

As contas contábeis atualizadas por causa dessas tarefas são vinculadas à transação de estoque original. Por exemplo, se uma ordem de venda for liquidada para uma ordem de compra, as contas contábeis gerais que foram usadas para a ordem de venda original serão ajustadas. Esse comportamento ocorrerá mesmo se a conta contábil do grupo de itens atribuído a esse item for alterada desde que a ordem de venda foi lançada. Depois que o fechamento de estoque cria um valor de liquidação, esse valor ainda será lançado nas contas contábeis originais e não nas novas contas contábeis atribuídas ao item. A contabilidade também poderá ser atualizada, se você estornar um fechamento de estoque. 

> [!NOTE] 
> - O fechamento de estoque é uma etapa obrigatória no procedimento de fechamento do mês final para todos os modelos de estoque, exceto a média móvel.  Você será avisado se tentar fechar um período financeiro sem antes executar o fechamento do estoque na data final do período.
> - Antes de executar o procedimento de fechamento, você poderá exibir uma lista de itens que não pode ser liquidada durante a atualização
> - Recomendamos que você execute o fechamento de estoque durante horários de menor movimento para distribuir os recursos computacionais de maneira mais uniforme.

## <a name="the-inventory-close-log"></a>O log de fechamento de estoque
Depois de concluído o fechamento do estoque, uma mensagem no centro de mensagens pode informar você que um preço de custo unitário pode estar incorreto porque uma transação não pôde ser totalmente liquidada. 

Antes que essa mensagem seja mostrada, o sistema relatará o número do item e a transação afetada. A mensagem informa que o valor de custo usado para a transação não foi atualizado devido ao fechamento do estoque. Essa mensagem aparece quando uma transação de tipo de saída não pode ser liquidada. 

Durante o processo de fechamento de estoque, o sistema verifica todas as dimensões financeiras para ver se há mais saídas do que recebimentos até a data de fechamento especificada. Esse tipo de desequilíbrio pode acontecer quando uma transação de estoque de uma ordem de compra não é totalmente lançada financeiramente porque a fatura de fornecedor não foi recebida, ou porque os componentes da lista de materiais (BOM) incluídos em uma produção em um nível mais alto não foram lançados financeiramente (A subprodução não é calculada por custo). Nesse caso, o fechamento subsequente não ajustará todas as saídas para o preço de custo correto porque não há informações suficientes sobre recebimento. 

Para cada execução do fechamento, o sistema indicará se um log com os avisos foi armazenado e pode ser exibido. 

Se você receber muitos avisos na mensagem, recomenda-se realizar estas ações:

-   Atualizar financeiramente os recebimentos
-   Adiantar a data de fechamento.
-   Reavaliar os procedimentos de negócios.

Em algumas circunstâncias, talvez você não consiga fazer nada em relação aos avisos. Por exemplo, se a marcação for usada onde a ordem de compra marcada tem uma data financeira posterior à data de fechamento, a data de fechamento não pode ser alterada.

## <a name="reversing-a-completed-inventory-close"></a>Estornar um fechamento de estoque concluído
Ocasionalmente, talvez seja necessário reverter um fechamento de estoque concluído, retornando as liquidações para o estado que tinham antes dos ajustes. Quando você reverte um fechamento de estoque concluído, o estoque é reaberto para habilitar o lançamento no período coberto pelo fechamento de estoque. As alterações relacionadas também podem ser feitas na contabilidade. Depois que concluir os ajustes, você poderá executar o fechamento de estoque novamente para o período em que está trabalhando. 

> [!NOTE] 
> Somente o último período de estoque que foi fechado pode ser reaberto. Para estornar um fechamento de estoque anterior, você deverá estornar cada fechamento de estoque subsequente, um de cada vez, começando pelo fechamento mais recente.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]