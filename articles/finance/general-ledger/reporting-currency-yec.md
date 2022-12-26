---
title: Falta de saldo na moeda de relatório quando o fechamento do exercício é executado
description: Este artigo explica como a moeda de relatório pode faltar quando o fechamento do exercício é executado.
author: kweekley
ms.date: 12/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 31f79791330e076d4fbd7b604ba9f9c6cd9b9195
ms.sourcegitcommit: 44f0b4ef8d74c86b5c5040be37981e32eb43e1a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2022
ms.locfileid: "9850253"
---
# <a name="reporting-currency-out-of-balance-when-the-year-end-close-is-run"></a>Falta de saldo na moeda de relatório quando o fechamento do exercício é executado

Depois de habilitar o recurso **Reconhecimento entre a liquidação do razão e o fechamento do exercício** (recurso **Reconhecimento**), as transações do razão que tiverem sido liquidadas não serão mais incluídas no saldo inicial do ano fiscal seguinte quando o fechamento do exercício da contabilidade for executado. A exclusão das transações do razão que são liquidadas poderá ser um desafio para os clientes no fechamento do exercício se uma moeda de relatório tiver sido definida para o razão.

A liquidação do razão é feita apenas para a moeda contábil. Quando as transações do razão são liquidadas, a validação confirma apenas que os débitos da moeda contábil são iguais aos créditos. Os valores da moeda de relatório para essas transações contábeis não são validados e podem ter débitos diferentes dos créditos. Além disso, a liquidação do razão não calcula nem lança automaticamente um lucro/perda na moeda do relatório.

Devido a essas limitações, uma transação de ganho/perda deve existir na moeda de relatório quando a liquidação do razão acontecer. Se nenhum ganho/perda for incluído na liquidação do razão, uma mensagem de falta de saldo aparecerá no fechamento do exercício.

O exemplo a seguir percorre as etapas para resolver esse problema antes que o fechamento do exercício seja executado.

## <a name="example-setup"></a>Exemplo de configuração

Para configurar este exemplo, habilite o recurso **Reconhecimento** e configure a liquidação do razão da conta principal 110180. A ilustração a seguir mostra as transações do razão que foram lançadas na entidade legal DEMF. A moeda contábil para DEMF está em dólar americano (USD) e a moeda do relatório, em euro (EUR).

![Transações do razão lançadas na moeda secundária.](./media/reporting-currency-1.png)

A página **Liquidações do razão** mostra as transações do razão para a conta principal 110180. Selecione e segure (ou clique com o botão direito do mouse) na grade e, depois, selecione **Inserir colunas**. Adicione a coluna **Valor na moeda de relatório** para que os valores da moeda de transação, moeda contábil e de relatório sejam exibidos.

![Valor na coluna de moeda organizacional adicionado à página de liquidações do razão.](./media/Ledger-settlement2.png)

As duas primeiras transações do razão de 100 EUR são liquidadas como um grupo, e as duas próximas transações do razão de 200 EUR são liquidadas como outro grupo. (As duas transações terão IDs de liquidação diferentes). Essa configuração mostra que as organizações terão vários grupos de transações do razão que são liquidados em horas diferentes e que têm datas de liquidação distintas. Depois que a liquidação for concluída, a página **Liquidações do razão** mostra as seguintes informações quando ela é filtrada para exibir transações com um status de **Liquidado**.

![Transações liquidadas na página de liquidações do razão.](./media/Settled-trans-filtered3.png)

Na página **Liquidações do razão**, selecione e segure (ou clique com o botão direito) na coluna **Valor** e **Totalizar esta coluna**. Repita esta etapa para as colunas **Valor na moeda de relatório**. A moeda contábil deve ter uma diferença de 0 (zero) para que a liquidação ocorra. No entanto, não há validação do valor de liquidação para a moeda de relatório. A ilustração a seguir mostra uma diferença de -27,79 USD para a moeda de relatório.

![Diferença para a moeda de relatório.](./media/Difference4.png)

## <a name="year-end-close"></a>Fechamento do exercício

Se o fechamento do exercício for concluído agora para 2022, o processo terminará com um erro de falta de saldo. Esse erro é causado diretamente pelo fato de a moeda de relatório não ter um valor de liquidação do razão que totalize 0 (zero) como valor líquido.

![Mensagem de erro que indica que o valor de liquidação do razão não é 0 (zero).](./media/YEC5.png)

## <a name="posting-reporting-currency-gainloss"></a>Lançar ganho/perda na moeda de relatório

Para que o fechamento do exercício seja executado com êxito, a diferença no valor da moeda de relatório precisa ser contabilizada, geralmente como um ganho ou perda, além de ser incluída na liquidação do razão. O ganho/perda da moeda de relatório pode ser lançada de várias maneiras:

- Se a conta principal for de contas a pagar ou contas a receber, a liquidação de AR/AP desses documentos gerará o ganho/perda necessário. Essa entrada contábil precisa ser incluída na liquidação do razão quando as transações do razão correspondentes da nota fiscal, dos pagamentos, das notas de crédito, entre outros, são liquidadas.
- Se a conta principal for qualquer conta além das contas a pagar ou da conta a receber, o ganho/perda deverá ser inserido manualmente. Quando o ganho/perda é lançado, o nível de detalhe da entrada contábil é determinado pela sua organização.
- Para cada conta principal, identifique o valor de ganho/perda da moeda secundária que deve ser lançado.

Conforme descrito anteriormente, esse lançamento pode ser feito na página **Liquidações do razão**.

1. Filtre até o intervalo de datas para o qual você quer lançar o ganho/perda. Se você planeja lançar um ganho/perda por mês, filtre cada mês. Se você planeja lançar um ganho/perda por ano fiscal, filtre o ano inteiro.
2. Filtre na conta principal.
3. Filtre o status para que só as transações **Liquidadas** sejam mostradas.
4. Adicione um total à coluna **Valor na moeda de relatório**.
5. Se você deseja lançar o ganho/perda em um nível mais granular, é possível aplicar um filtro adicional na ID de liquidação, nas dimensões financeiras e assim por diante. O valor total da coluna **Valor na moeda de relatório** representa o valor para o qual o ganho/perda será lançado.
6. Acesse **Contabilidade \> Entradas do diário \> Diários de ajuste de moeda de relatório**.
7. Insira a transação do ganho/perda. Este diário lançará um ajuste somente na moeda de relatório. Os valores da moeda da transação e da moeda contábil lançados são sempre 0 (zero). Se esse diário não tiver sido usado antes, talvez seja necessário criar um nome contendo um tipo de diário de **Ajuste da moeda de relatório** em **Contabilidade \> Configuração do diário \> Nomes do diário**.
8. Se a conta principal não permitir uma entrada manual, o ajuste não será lançado. Sendo assim, talvez seja necessário desativar temporariamente o parâmetro **Do not allow manual entry** na página **Conta principal**.

![Entrada manual na página Comprovante de diário.](./media/Manual-entry6.png)

Depois de lançar o diário de ajuste, retorne à página **Liquidações do razão** e selecione a conta principal para a qual você lançou o ganho/perda. O ajuste de ganho/perda precisa ser incluído em uma liquidação do razão. Como o valor da moeda de relatório não tem de ser um líquido de 0 (zero), você pode desliquidar todas as transações anteriores e depois reliquidá-las, incluindo o ganho/perda. O nível de precisão necessário para o lançamento do ganho/perda e a liquidação desse valor nas liquidações do razão depende da sua organização.

A ilustração a seguir mostra que as transações de 200 EUR não foram liquidadas e foram marcadas para liquidação novamente. Desta vez, eles incluirão o ajuste de ganho/perda.

![Ajuste de ganho/perda na página Liquidações do razão.](./media/gain-loss7.png)

Depois da liquidação das transações, mude o filtro de **Status** para que a página mostre as transações **Liquidadas**. O total da coluna **Valor na moeda de relatório** agora é 0 (zero). O fechamento do exercício agora pode ser executado.

![Fechamento do exercício concluído.](./media/Zero-settled8.png)
