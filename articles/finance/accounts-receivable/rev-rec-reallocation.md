---
title: Realocação de reconhecimento de receita
description: Este tópico fornece informações sobre a realocação, que permite que as organizações recalculem os preços de receita quando os termos de uma venda contratual são alterados. Ele inclui links para outros tópicos que descrevem como reconhecer a receita em vários cenários.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a7c57ac5f3fc8d9a0e0b57ba5d7a3e2924bbd4c6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5114709"
---
# <a name="revenue-recognition-reallocation"></a>Realocação de reconhecimento de receita

[!include [banner](../includes/banner.md)]

A realocação permite que as organizações recalculem os preços de receita quando os termos de uma venda contratual são alterados. Para fins de reconhecimento de receita, os documentos da ordem de venda são considerados como o contrato.

Sua organização deve determinar se a realocação em si é necessária. A adição de uma nova linha a uma ordem de venda ou a adição de uma nova ordem de venda para um cliente pode não constituir uma alteração no contrato. Os seguintes cenários podem exigir realocação:

- Um cliente adicionou itens a uma ordem de venda ou removeu itens da ordem de venda depois que a ordem foi faturada total ou parcialmente.
- Várias ordens de venda, em um estado confirmado ou faturado, foram inseridas para o mesmo contrato negociado.
- Um cliente devolveu ou recebeu o crédito de um item depois que a ordem de venda original foi faturada total ou parcialmente.

Existem algumas limitações importantes no processo de realocação:

- O processo só pode ser executado uma vez. Portanto, é importante executá-lo somente após a finalização de todas as alterações.
- O processo não pode ser executado em ordens de venda do projeto.
- Se várias ordens de venda estiverem envolvidas, elas deverão ser para a mesma conta de cliente.
- Todas as ordens de venda realocadas devem estar na mesma moeda da transação.
- O processo não pode ser revertido nem desfeito após a execução.

## <a name="set-up-reallocation"></a>Configurar realocação

Um parâmetro afeta o processo de realocação.

Como a realocação pode ser feita em uma ordem de venda que esteja faturada parcial ou totalmente, qualquer entrada contábil anterior para a fatura deve ser corrigida usando os preços de receita novos e realocados. Essa correção é feita com a reversão da entrada contábil da fatura original e o lançamento de uma nova entrada contábil baseada nos preços de receita realocados.

Cada organização deve decidir se a correção deve atualizar somente a Contabilidade ou se ela também deve atualizar Contas a receber. A decisão tomada determina a configuração apropriada da opção **Lançar correções de fatura em Contas a receber** na guia **Reconhecimento de receita** da página **Parâmetros da contabilidade** (**Reconhecimento de receita \> Configurar \> Parâmetros da contabilidade**). A configuração apropriada depende do cenário específico. Para obter mais informações sobre possíveis cenários, use os links na seção [Cenários para realocação](#scenarios-for-reallocation) posteriormente neste tópico.

[![Guia Reconhecimento de receita na página Parâmetros da contabilidade](./media/01_RevRecScenarios.png)](./media/01_RevRecScenarios.png)

Se a opção **Lançar correções de fatura em Contas a receber** estiver definida como **Sim**, o processo de realocação produzirá o seguinte resultado:

- Um documento de crédito será criado em Contas a receber para reverter a fatura que requer correção.

    - O documento de crédito reutilizará o número da fatura original, mas "-1" será acrescentado a ele.
    - O documento de crédito será liquidado automaticamente com base na fatura original. Se a fatura original já tiver sido liquidada com outro documento de crédito ou pagamento, essa liquidação será revertida automaticamente.
    - O documento de crédito será lançado na Contabilidade para reverter a entrada contábil lançada na fatura original. No entanto, as entradas de transação de estoque e de custo dos produtos vendidos (COGS) não serão revertidas.

- Uma nova fatura baseada nos novos valores de preço realocado será criada em Contas a receber.

    - A nova fatura reutilizará o número da fatura original, mas "-2" será acrescentado a ele.
    - A nova fatura será liquidada automaticamente com base em qualquer documento de crédito ou pagamentos que foram liquidados anteriormente com a fatura original.
    - A nova fatura será lançada na Contabilidade usando os valores de preço de receita novos e realocados. Ela não será lançada novamente nas contas de estoque e COGS porque essas entradas são mantidas na entrada contábil da fatura original.

Se a opção **Lançar correções de fatura em Contas a receber** estiver definida como **Não**, o processo de realocação produzirá o seguinte resultado:

- Uma entrada contábil de reversão será lançada somente na Contabilidade. Todas a contabilidade da fatura original será revertida, exceto as entradas de conta de estoque e COGS.
- Uma nova entrada contábil será lançada somente na Contabilidade, com base nos preços de receita novos e realocados. Ela não será lançada novamente nas contas de estoque e COGS porque essas entradas são mantidas na entrada contábil da fatura original.
- A fatura na página **Transações do cliente** não será afetada ou alterada, mas ainda refletirá a entrada contábil original. Não haverá referência à reversão ou a novas entradas contábeis.

Como foi mencionado, você pode atualizar somente a Contabilidade ou pode atualizar a Contabilidade e Contas a receber. As duas abordagens têm prós e contras. É recomendável avaliar os requisitos de sua organização para determinar qual opção deve ser usada. Se você atualizar a Contabilidade e Contas a receber, as entradas contábeis corretas serão mostradas na nova fatura e poderão ser exibidas no documento na página **Transações do cliente**. Além disso, o processo de liquidação usará as entradas contábeis atualizadas para lançar descontos à vista e ganhos ou perdas. Por outro lado, o documento de crédito e a nova nota fiscal aparecerão em demonstrativos de cliente e relatórios de classificação por vencimento, da mesma forma que outros documentos de crédito e faturas de clientes. A descrição desses documentos indicará que eles foram criados por meio de uma correção contábil.

## <a name="run-the-reallocation-process"></a>Executar o processo de realocação

Para iniciar o processo de realocação, selecione **Realocar o preço com as novas linhas de ordem** em qualquer ordem de venda que deva ser realocada. Como alternativa, acesse **Reconhecimento de receita \> Tarefas periódicas \> Realocar o preço com novas linhas da ordem** e insira os filtros apropriados, como a conta do cliente.

[![Página Realocar preço com novas linhas da ordem](./media/02_RevRecScenarios.png)](./media/02_RevRecScenarios.png)

A grade superior da página **Realocar o preço com novas linhas da ordem** é chamada **Vendas**. Ela lista as ordens de venda para o cliente. Selecione as ordens de venda que devem ser realocadas. Não é possível selecionar ordens de venda do projeto porque as ordens de venda do projeto não podem ser realocadas. Também não é possível selecionar ordens de venda que já tenham uma ID de realocação, porque as ordens de venda não relacionadas ao projeto só podem ser realocadas uma vez. Se uma ordem de venda tiver uma ID de realocação, ela já foi marcada para realocação por outro usuário.

A grade inferior na página é chamada **Linhas**. Depois que selecionar uma ou mais ordens de venda na grade de **Vendas**, a grade de **Linhas** mostrará as linhas da ordem de venda. Selecione as linhas da ordem de venda que devem ser realocadas. Se você selecionou somente uma ordem de venda, as linhas na mesma ordem de venda deverão ser realocadas. Essa situação pode ocorrer quando uma das linhas da ordem de venda foi faturada anteriormente e uma nova linha foi adicionada ou quando uma linha existente foi removida ou cancelada. Se uma linha foi removida, ela não aparecerá na grade. Portanto, ela não pode ser selecionada. No entanto, ela ainda será considerada quando o processo de realocação for executado.

Depois que concluir a seleção das linhas de ordem de venda necessárias, use os botões no Painel de Ações conforme descrito aqui:

- **Atualizar realocação** — calcula os novos valores de preço de receita para as linhas de ordem de venda selecionadas. Se uma linha foi removida ou cancelada, a realocação será feita somente para as linhas existentes que você selecionou. A ilustração a seguir mostra um exemplo de linhas de ordem de venda antes que a realocação seja atualizada.

    [![Linhas de ordem de venda antes que a realocação seja atualizada](./media/03_RevRecScenarios.png)](./media/03_RevRecScenarios.png)

    Os novos valores de preço de receita são mostrados na coluna **Valor realocado** na grade de **Linhas**. Nesse ponto, a realocação foi processada, mas ainda não foi calculada. A ilustração a seguir mostra um exemplo de linhas de ordem de venda depois que a realocação foi atualizada.

    [![Linhas de ordem de venda depois que a realocação foi atualizada](./media/04_RevRecScenarios.png)](./media/04_RevRecScenarios.png)

- **Processar** — processa ou lança os preços de receita realocados. Depois que você selecionar este botão, não haverá como reverter a realocação. Se você não selecionar **Atualizar realocação** antes de selecionar **Processar**, a realocação será executada automaticamente.

    - Se nenhuma linha da ordem de venda tiver sido faturada, os valores de preço de receita serão atualizados em todas as ordens de venda que tiverem sido selecionadas para realocação.
    - Se uma ou mais linhas da ordem de venda tiverem sido faturadas, a correção das entradas contábeis será lançada e todos os detalhes da agenda de receita criados para a linha da ordem de venda faturada serão corrigidos.

- **Comprovante esperado** — mostra uma visualização das entradas contábeis criadas para todas as linhas da ordem de venda que foram faturadas. Se nenhuma linha tiver sido faturada, nada será exibido. Se você não selecionar **Atualizar realocação** antes de selecionar **Comprovante esperado**, a realocação será executada automaticamente.
- **Realocação de receita** — abre uma página que mostra a alocação de preço de receita para todas as linhas selecionadas. Não é possível alterar as informações na página. Ela mostra os valores de linha usados para fazer a realocação.

    [![Valores de linha usados para realocação](./media/05_RevRecScenarios.png)](./media/05_RevRecScenarios.png)

- **Redefinir dados para o cliente selecionado** — se o processo de realocação foi iniciado mas não foi concluído, limpa os dados na tabela de realocação somente para o cliente selecionado. Por exemplo, você marca várias linhas de ordem de venda para realocação, deixa a página aberta sem selecionar **Processar** e, em seguida, a página expira. Nesse caso, as linhas da ordem de venda permanecerão marcadas e não estarão disponíveis para que outro usuário conclua o processo de realocação. A página pode estar em branco ao ser aberta. Nesse caso, o botão **Redefinir dados do cliente selecionado** pode ser usado para limpar ordens de venda não processadas para que outro usuário possa concluir o processo de realocação.

## <a name="scenarios-for-reallocation"></a>Cenários para realocação

Os tópicos a seguir passam por vários cenários de reconhecimento de receita:

- [Realocação de reconhecimento de receita — cenário 1](rev-rec-reallocation-scenario-1.md) — duas ordens de venda são inseridas, mas só são confirmadas. O mesmo cenário produzirá resultados semelhantes, se houver mais de duas ordens de venda em um estado confirmado.
- [Realocação de reconhecimento de receita — cenário 2](rev-rec-reallocation-scenario-2.md) — duas ordens de venda são inseridas e o cliente adiciona um item ao contrato depois que a primeira ordem de venda foi faturada.
- [Realocação de reconhecimento de receita — cenário 3](rev-rec-reallocation-scenario-3.md) — uma nova linha é adicionada a uma ordem de venda faturada existente.
- [Realocação de reconhecimento de receita — cenário 4](rev-rec-reallocation-scenario-4.md) — uma linha é removida de uma ordem de venda existente faturada parcialmente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]