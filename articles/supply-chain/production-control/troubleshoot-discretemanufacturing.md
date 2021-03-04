---
title: Solucionar problemas de fabricação discreta
description: Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com fabricação discreta.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 604e0c3406b15d885991fcb067e93ef83533e3b0
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516724"
---
# <a name="troubleshoot-discrete-manufacturing"></a>Solucionar problemas de fabricação discreta

Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com fabricação discreta.

## <a name="i-receive-the-following-error-message-warehouse-management-processes-are-currently-being-used-if-work-lines-are-not-yet-registered-you-can-cancel-the-created-work-and-any-load-or-shipment-lines-and-then-continue-with-the-picking-or-shipping-process"></a>Recebo a seguinte mensagem de erro: "Processos de gerenciamento de depósito estão sendo usados. Se as linhas de trabalho ainda não estiverem registradas, você pode cancelar o trabalho criado e qualquer linha de carga ou expedição e continuar com o processo de separação ou remessa."

### <a name="issue-description"></a>Descrição do problema

Esse problema ocorre se você tentar reservar ou liberar trabalho para uma linha, mas a transação de estoque tiver um status de *Separado*, o que indica que o material foi separado.

### <a name="issue-resolution"></a>Resolução do problema

Para corrigir esse problema, siga uma destas etapas:

- Altere o status da ordem de produção de volta para *Previsto* ou *Liberado*.
- Abra a página de detalhes da ordem de produção relevante. No Painel de ações, na guia **Depósito**, no grupo **Parar**, selecione **Parar e desfazer separação** para desmarcar todas as transações selecionadas. Em seguida, selecione **Remover parada** para processar a ordem de produção.

Aqui está uma explicação das funções *Desfazer separação* e *Parar*:

- **Desfazer separação** - Esta função inverte o status das transações de estoque para linhas da lista de materiais (BOM) e linhas de fórmula que têm um status de *Separado* a *Em ordem*. Quando o trabalho de separação de matéria-prima é concluído, o status das linhas é definido como *Separado*. Este status evita que a ordem de produção seja redefinida para o status *Criado*. Nesse caso, você pode usar a função *Desfazer separação* para reverter as transações do status *Separado* e redefinir a ordem de produção para o status *Criado*.
- **Parar** – Esta função define um sinalizador **Interrompido** na ordem de produção para evitar qualquer atualização de status na ordem. É possível encontrar o sinalizador **Interrompido** na guia rápida **Depósito** da página de detalhes da ordem de produção.

> [!NOTE]
>
> - Os botões são visíveis somente quando a ordem de produção é criada para itens habilitados para processos de depósito.
> - O grupo **Parar** está visível apenas na guia **Depósito** no Painel de ações da página de detalhes da ordem de produção. Não está visível na FastTab **Depósito** da página de lista **Ordens de Produção**.

## <a name="the-matching-resource-name-isnt-updated-after-i-change-a-worker-name-in-the-global-address-book"></a>O nome do recurso correspondente não é atualizado depois que eu mudo o nome de um trabalhador no catálogo de endereços global.

### <a name="issue-description"></a>Descrição do problema

Se você alterar o nome de um trabalhador no catálogo de endereços global, o nome do recurso correspondente não será atualizado no mestre do grupo de recursos.

### <a name="issue-resolution"></a>Resolução do problema

Não há suporte para este cenário atualmente. Para corrigir o problema, você deve atualizar manualmente o nome do recurso.

## <a name="when-i-create-a-new-production-order-i-dont-receive-the-following-message-insert-the-active-version-of-bill-of-material-and-route"></a>Quando crio uma ordem de produção, não recebo a seguinte mensagem: "Inserir a versão ativa da lista de materiais e roteiro?"

### <a name="issue-description"></a>Descrição do problema

Quando você cria uma ordem de produção, depois de inserir o número do item, os campos **Local** e **Depósito** são automaticamente configurados para o local e depósito padrão definidos na página **Configurações de ordem padrão** para o item de produtos acabados. Além disso, o número da BOM e o número da rota ativos são inseridos automaticamente. Você não recebe a seguinte mensagem que solicita esses valores:

> Inserir versão ativa para lista de materiais e rota?

### <a name="issue-resolution"></a>Resolução do problema

Você não será solicitado a inserir BOM e números de rota se selecionar um produto para o qual um local e depósito estão definidos na página **Configurações de ordem padrão**. Você só receberá a solicitação se esses valores não forem definidos para o produto selecionado.

## <a name="production-orders-arent-shown-on-the-marking-page"></a>As ordens de produção não são mostradas na página Marcação.

### <a name="issue-description"></a>Descrição do problema

Algumas ordens de produção não são mostradas na página **Marcação**.

### <a name="issue-resolution"></a>Resolução do problema

Produtos que possuem a seguinte configuração não estão disponíveis para marcação. Portanto, eles não serão mostrados na página **Marcação**:

- Os produtos são definidos como produtos do tipo de *peso variável*.
- Eles são habilitados para os processos avançados de depósito.
- Eles são configurados para serem controlados pelo princípio de *Custo padrão*.

## <a name="when-i-try-to-end-a-production-order-i-receive-the-following-error-message-calculating-bom-consumptioncost-value-must-be-negative-upon-issue-from-inventory"></a>Quando tento encerrar uma ordem de produção, recebo a seguinte mensagem de erro: "O cálculo do valor consumptionCost da BOM deve ser negativo na saída do estoque."

Esse problema foi corrigido na versão 10.0.15.

## <a name="when-the-status-of-a-production-order-is-changed-from-reported-as-finished-to-end-i-receive-the-following-error-messages-update-conflict-the-standard-cost-does-not-match-with-the-financial-inventory-value-after-the-update-and-a-critical-error-has-occurred-in-function-inventcostmovementcheckvariance"></a>Quando o status de uma ordem de produção é alterado de Informado como concluído para Finalizado, recebo as seguintes mensagens de erro: "Conflito de atualização. O custo padrão não corresponde ao valor do estoque financeiro após a atualização" e "Ocorreu um erro crítico na função InventCostMovement.checkVariance."

Esse problema ocorre porque os dados subjacentes foram alterados por outro processo. O processo tentará atualizar os dados até cinco vezes. Se o conflito persistir após cinco tentativas, você receberá as seguintes mensagens de erro:

> Conflito de atualização. O custo padrão não corresponde ao valor do estoque financeiro após a atualização.

> Ocorreu um erro crítico na função InventCostMovement.checkVariance.

Esse comportamento é por design. Para atenuar o problema, retome o trabalho em lote. A execução deve ser finalizada.

Se o trabalho em lote falhar consistentemente depois de retomá-lo, verifique se a precisão do arredondamento para a moeda padrão do razão é compatível com o arredondamento que é aplicado aos valores na tabela InventSum. Se a precisão de arredondamento foi alterada para um valor não compatível, você provavelmente deve alterá-lo de volta para um valor compatível. Procure **ModifiedDateTime**. Em geral, nesse caso, o valor mostrará se a precisão do arredondamento foi alterada recentemente.

## <a name="when-i-release-to-a-warehouse-i-receive-the-following-error-message-item-rm-could-not-be-fully-reserved-ensure-that-the-full-quantity-is-available-or-reserve-the-items-manually-if-the-reservation-field-on-the-bom-line-is-set-to-manual-or-started-could-not-release-the-order-to-warehouse-because-some-materials-could-not-be-reserved-however-the-status-is-updated-to-released"></a>Ao liberar para um depósito, recebo a seguinte mensagem de erro: "O item RM não pôde ser totalmente reservado. Certifique-se de que a quantidade total esteja disponível ou reserve os itens manualmente se o campo Reserva na linha da BOM estiver definido como Manual ou Iniciado. Não foi possível liberar a ordem para o depósito porque alguns materiais não puderam ser reservados." No entanto, o status é atualizado para Liberado.

### <a name="issue-description"></a>Descrição do problema

Se nem todos os itens de linha da BOM estiverem fisicamente disponíveis quando uma ordem de produção for liberada e a política **Liberar para o depósito** for definida como *Exigir reserva cheia* na ordem de produção, você receberá a seguinte mensagem de erro:

> O item RM não pôde ser totalmente reservado. Certifique-se de que a quantidade total esteja disponível ou reserve os itens manualmente se o campo Reserva na linha da BOM estiver definido como Manual ou Iniciado. Não foi possível liberar a ordem para o depósito porque alguns materiais não puderam ser reservados.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é assim por design e está funcionando conforme o esperado.

## <a name="when-i-try-to-end-a-production-order-and-report-as-finished-i-receive-the-following-error-message-total-good-quantity-reported-as-finished-for-the-production-will-be-1-feedback-for-the-last-operation-is-000-in-total"></a>Quando tento encerrar uma ordem de produção e informá-la como concluída, recebo a seguinte mensagem de erro: "A quantidade total de produtos informada como concluída para a produção será %1. O feedback da última operação é de 0,00 no total."

### <a name="issue-description"></a>Descrição do problema

Ao tentar lançar um relatório como diário concluído em uma ordem de produção, você recebe a seguinte mensagem de erro:

> A quantidade total sem erros relatada como concluída da produção será %1. O feedback da última operação é de 0,00 no total.

### <a name="possible-cause"></a>Possível causa

Esse problema ocorre se as quantidades que foram lançadas nas últimas operações estavam incorretas. Por exemplo, se a produção for iniciada, mas a quantidade que deve ser iniciada não for alocada, o diário de cartão de rota será lançado sem nenhuma linha. Para confirmar a situação, abra a ordem de produção e, no Painel de Ações, na guia **Exibir**, selecione **Cartão de roteiro**.

### <a name="workaround"></a>Solução alternativa

É possível corrigir esse problema lançando diários adicionais para as operações para as quais os diários não foram lançados corretamente. Reinicie a ordem de produção e opte por lançar os diários adicionais. Essa ação não iniciará a ordem de produção, mas publicará os diários. O cartão de roteiro deve mostrar as quantidades que foram lançadas e você deve ser capaz de encerrar as ordens de produção com sucesso.

## <a name="can-i-report-a-production-order-as-finished-while-i-report-the-error-quantity-but-not-while-i-report-the-time-or-material-quantity"></a>Posso relatar uma ordem de produção como concluída enquanto relato a quantidade de erro, mas não enquanto relato o tempo ou a quantidade de material?

Você não pode relatar a quantidade de erro em uma ordem de produção, a menos que também relate a quantidade boa. Esse cenário **não** é compatível. O relatório de atualização concluída acabará falhando quando você tentar encerrar a ordem de produção. Além disso, você receberá a seguinte mensagem de erro:

> Quantidade de relatório de conclusão ausente.

## <a name="can-i-trace-the-serial-numbers-of-finished-goods-against-the-serial-numbers-of-consumed-goods"></a>Posso comparar os números de série dos produtos acabados com os números de série dos produtos consumidos?

Não é possível rastrear os números de série dos produtos concluídos em relação aos números de série do material que uma ordem de produção consome para fazer esses produtos concluídos. Não há suporte para este cenário atualmente. A solução alternativa é criar ordens de produção para uma quantidade de 1.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]