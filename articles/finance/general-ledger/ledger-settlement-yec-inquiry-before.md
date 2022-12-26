---
title: Recurso de Reconhecimento entre liquidações do razão antes do fechamento do exercício da contabilidade usando a página de consulta
description: Este artigo explica como usar o recurso de Reconhecimento entre liquidações do razão usando a nova página de consulta antes da execução do fechamento do exercício da contabilidade.
author: kweekley
ms.date: 12/15/2022
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
ms.openlocfilehash: b138d2d5e88ff7f2ca2240cf256a4938f55a5606
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853114"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close-using-the-inquiry-page"></a>Recurso de Reconhecimento entre liquidações do razão antes do fechamento do exercício da contabilidade usando a página de consulta

Uma alteração importante do recurso de **Reconhecimento entre a liquidação do razão e o fechamento do exercício** (o recurso de **Reconhecimento**) é que a liquidação do razão não pode ser feita entre anos fiscais. Esse limite entre anos é relevante apenas para liquidações do razão, não para as liquidações de contas a receber ou contas a pagar.

Antes de habilitar o recurso de **Reconhecimento**, o ano fiscal que passará pelo fechamento do exercício não pode ter nenhuma transação do razão liquidada entre anos fiscais. Especificamente, todas as transações lançadas no ano fiscal para o qual você está executando o fechamento do exercício devem ser desliquidadas das transações que foram lançadas em outro ano fiscal. Então, as transações podem ser reliquidadas em relação a transações no mesmo ano fiscal.

Este artigo descreve as etapas necessárias para identificar, desliquidar e reliquidar transações do razão que são liquidadas entre os anos fiscais. No exemplo fornecido, o ano fiscal de 2021 foi fechado, e você está se preparando para executar o fechamento do exercício do ano fiscal de 2022.

A partir do Microsoft Dynamics 365 Finance versão 10.0.29, você pode identificar, desliquidar e reliquidar transações do razão usando uma nova página de consulta disponível. Se você não está usando o Finance versão 10.0.29 ou posterior, veja as etapas para identificar, desliquidar e reliquidar as transações do razão nos seguintes artigos:

- [Recurso de Reconhecimento entre a liquidação do razão antes do fechamento do exercício](ledger-settle-yec.md)
- [Recurso de Reconhecimento entre a liquidação do razão depois do fechamento do exercício](ledger-settle-yec-after.md)

Para obter mais informações sobre a nova janela de consulta, acesse [Consulta de liquidação do razão](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Exemplo de configuração

A ilustração a seguir mostra as transações lançadas para a conta principal 110200. As transações em verde foram liquidadas pelo razão no mesmo ano fiscal e não precisam ser alteradas. As transações em vermelho foram liquidadas pelo razão, mas têm datas de transação em anos fiscais diferentes. Essas transações devem ser identificadas, e a liquidação do razão pode precisar ser revertida.

![Transações do razão lançadas.](./media/ledgersettlement.png)

## <a name="example"></a>exemplo

Siga estas etapas se a sua organização quiser usar o recurso de **Reconhecimento** antes de você executar o fechamento do exercício do ano fiscal de 2022.

> [!NOTE]
> O fechamento do exercício de 2021 e dos anos fiscais anteriores só deve ser executado novamente se novas transações forem lançadas no ano fiscal de 2021 ou anteriores. Quando você concluir o procedimento a seguir, nenhuma transação nova será lançada em 2021. Portanto, o fechamento do exercício não precisa ser executado novamente.
>
> As transações do razão que são liquidadas em anos fiscais podem permanecer liquidadas pelo razão se não forem liquidadas em relação a uma transação lançada em 2022 (o ano que está sendo fechado) ou em anos posteriores. Por exemplo, se você tiver liquidado transações em 2019 e 2020, elas poderão permanecer liquidadas.

1. **Não** habilite o recurso de **Reconhecimento**.
2. Na página **Liquidações do razão**, selecione **Examinar liquidações entre anos**.
3. Identifique todas as transações que foram lançadas em outros anos fiscais, mas liquidadas em relação a transações que foram lançadas em 2022.

    1. Selecione o ano fiscal de 2022, o ano fiscal para o qual você quer executar o processo de fechamento do exercício.
    2. Selecione um valor no campo **Conjunto de dimensões financeiras** para mostrar as dimensões financeiras que você deseja exibir para a conta do razão. A conta principal será sempre mostrada, mesmo que o conjunto de dimensões selecionado não contenha uma conta principal.
    3. Selecione **Mostrar transações**.

    A página de consulta mostrará todas as transações de todas as contas do razão (mesmo que elas não estejam mais na configuração de liquidação do razão) de todos os outros anos fiscais que são liquidados em relação a transações que foram lançadas em 2022. Três contas do razão diferentes são mostradas.

    ![Liquidações entre anos de 2022.](./media/review-cross-year.png)

3. Selecione e segure (ou clique com o botão direito do mouse) na grade e, depois, selecione **Exportar todas as linhas**. Essas linhas são todas as transações que devem ser desliquidadas a partir das transações em 2022 antes da execução do fechamento do exercício. Você quer a lista de transações detalhadas para reliquidar corretamente as transações posteriormente.
4. Anote os anos fiscais para os quais as transações foram lançadas. Neste exemplo, há transações em 2021 e 2023.
5. Na página de consulta, altere o ano fiscal para 2021, o primeiro ano fiscal que contém transações que foram liquidadas em relação a transações de 2022.
6. Filtre pela coluna **Data da transação** de modo que somente as transações que foram lançadas em 2022 sejam incluídas. Essas são as transações detalhadas de 2022 que foram liquidadas em relação a transações em 2021.
7. Selecione e segure (ou clique com o botão direito do mouse) na grade e, depois, selecione **Exportar todas as linhas**.

    > [!IMPORTANT]
    > Nas etapas a seguir, essas transações serão desliquidadas e, em seguida, reliquidadas em relação a transações em 2022. É essencial manter esses detalhes no Excel.

    ![Liquidações entre anos de 2021.](./media/review-cross-year.png)

8. Na página de consulta, altere o ano fiscal para 2023, o próximo ano fiscal que contém transações que foram liquidadas em relação a transações de 2022. 
9. Filtre pela coluna **Data da transação** de modo que somente as transações que foram lançadas em 2022 sejam incluídas. Essas são as transações detalhadas de 2023 que foram liquidadas em relação a transações em 2022. 
10. Selecione e segure (ou clique com o botão direito do mouse) na grade e, depois, selecione **Exportar todas as linhas**.

    > [!IMPORTANT]
    > Nas etapas a seguir, essas transações serão desliquidadas e, em seguida, reliquidadas em relação a transações em 2022. É essencial manter esses detalhes no Excel.

    ![Liquidações entre anos de 2023.](./media/filter-transactions.png)

11. Repita as etapas anteriores para cada ano fiscal que tem transações liquidadas em relação a transações em 2022. Sempre exporte as transações detalhadas para o Excel.

    Depois que todas as transações detalhadas de 2021 e 2023 forem exportadas para o Excel, você estará pronto para desliquidar as transações usando a nova página de consulta.

12. Altere o ano fiscal para 2022.
13. Selecione todos os registros na grade e, depois, selecione **Desliquidar registros marcados**. Todas as transações selecionadas na grade serão desliquidadas.

    Duas mensagens de aviso são exibidas para garantir que os detalhes da transação sejam exportados para o Excel antes que as transações sejam desliquidadas. Se você desliquidar acidentalmente as transações do razão antes de enviar os detalhes para o Excel, não há como reverter a desliquidação.

    ![Desliquidar transações de liquidação cruzada.](./media/revert-unsettle.png)

14. Use os dados do Excel para encontrar o valor total das transações em 2021 e 2023 que foram liquidadas em relação a transações em 2022. Neste exemplo, as transações de 2021 totalizam USD 525, e as transações de 2023 totalizam USD 700.
15. Lance um diário geral de ajuste para dividir o saldo inicial de 2022 em dois valores: a parte liquidada para o ano fiscal de 2021 e a parte que ainda não foi liquidada para 2022.

    - **Parte do saldo inicial que foi liquidado para o ano anterior:** O primeiro valor é de USD 525, com base nos totais encontrados que foram liquidados entre 2021 e 2022.
    - **Parte do saldo inicial que não foi liquidado para o ano anterior:** O segundo valor é a diferença entre o saldo inicial e o valor liquidado de USD 525. O valor restante é de USD 1.025 – USD 525 = USD 500.

    Desse modo, você pode liquidar as transações de 2022 em relação aos USD 525 que foram originalmente liquidados em relação à transação de 2021. Essa etapa é necessária porque a liquidação do razão não permite liquidação parcial.

    1. Vá para o diário geral e lance o ajuste. Sua organização terá que decidir qual data da transação será usada, com base nos períodos que estão abertos. Essas transações podem ter sido liquidadas usando uma data de liquidação de janeiro ou fevereiro de 2022, mas o ajuste pode ter de ser lançado em dezembro, se esse for o único período aberto.
    2. Talvez seja necessário desativar temporariamente o parâmetro **Não permitir entrada manual** para a conta 110200 na página **Conta principal**. Esse ajuste não será lançado se a conta principal não permitir entrada manual.

    ![Lançar um diário geral de ajuste.](./media/not-post.png)

16. Agora você pode reliquidar as transações desliquidadas. Retorne à página **Liquidações do razão**, especifique um intervalo de datas de 1º de janeiro a 31 de dezembro de 2022 e filtre na conta principal 110200. Em seguida, use as transações detalhadas exportadas para o Excel para localizar as transações específicas que precisam ser reliquidadas. A ilustração a seguir mostra as transações não liquidadas geradas.

    ![Transações desliquidadas.](./media/updated-unsettled.png)

    - O saldo inicial de USD 1.025 pode ser liquidado em relação ao ajuste para -USD 1.025.
    - As transações detalhadas que foram desliquidadas para -USD 400, -USD 50 e -USD 75 podem ser liquidadas em relação ao ajuste para USD 25.

17. Habilite o recurso de **Reconhecimento**. Agora você pode executar o fechamento do exercício.

    - Antes de executar o fechamento do exercício, considere marcar a opção **Manter detalhes** para todas as contas de balanço na configuração de liquidação do razão. Para obter mais informações, consulte [Reconhecimento entre a liquidação do razão e o fechamento do exercício](awareness-between-ledger-settlement-year-end-close.md).
    - Ao iniciar o fechamento do exercício de 2022, se ainda forem encontradas transações que foram liquidadas entre os anos fiscais, o processo de fechamento do exercício notificará você imediatamente. Essa situação poderá ocorrer se os usuários liquidarem transações entre anos fiscais depois que você concluir as etapas anteriores.
    - Se as transações de 2021 e 2022 ainda estiverem liquidadas, você terá que desabilitar o recurso de **Reconhecimento** novamente e repetir as etapas anteriores para desliquidar essas transações. Essa abordagem é necessária porque 2021 está fechado, e as transações não podem ser desliquidadas em um ano fiscal fechado.
    - Se as transações de 2022 e 2023 ainda estiverem liquidadas, você não precisará desabilitar o recurso de **Reconhecimento**. Como nem 2022 nem 2023 estão fechados, você pode seguir as etapas anteriores para desliquidar as transações.

18. Você pode liquidar a transação de USD 700 de 2023 em relação às transações detalhadas que foram lançadas como saldos iniciais em 2023. Essa transação não será liquidada em relação à transação original em 2022.

Depois que o fechamento do exercício de 2022 for executado com êxito, você poderá deixar o recurso de **Reconhecimento** habilitado desse momento em diante.
