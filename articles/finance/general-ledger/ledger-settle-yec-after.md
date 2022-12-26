---
title: Recurso de Reconhecimento entre a liquidação do razão depois do fechamento do exercício
description: Este artigo explica como usar o recurso de Reconhecimento entre liquidações do razão depois da execução do processo de fechamento do exercício da contabilidade.
author: kweekley
ms.date: 12/02/2022
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
ms.openlocfilehash: 7efa9d652d74bd836f51b5b1c5f6bfaf8934ea40
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832154"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close"></a>Recurso de Reconhecimento entre a liquidação do razão depois do fechamento do exercício

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-after-year-end-close"></a>Preparar-se para o recurso de Reconhecimento entre a liquidação do razão depois do fechamento do exercício

Uma alteração importante do recurso de **Reconhecimento entre a liquidação do razão e o fechamento do exercício** (o recurso de **Reconhecimento**) é que a liquidação do razão não pode ser feita entre anos fiscais. Esse limite entre anos é relevante apenas para liquidações do razão, não para as liquidações de contas a receber ou contas a pagar.

Antes de habilitar o recurso de **Reconhecimento**, o ano fiscal que passará pelo fechamento do exercício não pode ter nenhuma transação do razão liquidada entre anos fiscais. Especificamente, todas as transações lançadas no ano fiscal para o qual você está executando o fechamento do exercício devem ser desliquidadas das transações que foram lançadas em outro ano fiscal. Então, as transações podem ser reliquidadas em relação a transações no mesmo ano fiscal.

Este artigo descreveu as etapas necessárias para identificar, desliquidar e reliquidar as transações do razão que são liquidadas entre os anos fiscais. No exemplo fornecido, o ano fiscal de 2022 foi fechado. O foco é a preparação das transações de liquidação do razão bem antes da execução do fechamento do exercício da contabilidade de 2023.

## <a name="example-setup"></a>Exemplo de configuração

A ilustração a seguir mostra as transações lançadas para a conta principal 110190. As transações do razão em verde são liquidadas no mesmo ano fiscal e não precisam ser alteradas. As transações em vermelho são liquidadas pelo razão, mas têm datas de transação em anos fiscais diferentes. Essas transações devem ser identificadas, e a liquidação do razão pode precisar ser revertida.

![Transações do razão.](./media/afterYEC1.png)

## <a name="example"></a>exemplo

Siga estas etapas se a sua organização quiser usar o recurso de **Reconhecimento** após a execução do fechamento do exercício do ano fiscal de 2022.

> [!NOTE]
> O fechamento do exercício de 2022 e dos anos fiscais anteriores só deve ser executado novamente se novas transações forem lançadas no ano fiscal de 2022 ou anteriores. Quando você concluir o procedimento a seguir, nenhuma transação nova deverá ser lançada em 2022. Portanto, o fechamento do exercício não precisa ser executado novamente.
>
> As transações do razão que são liquidadas em anos fiscais podem permanecer liquidadas pelo razão se não forem liquidadas em relação a uma transação lançada em 2023 ou em anos posteriores. Por exemplo, se você tiver liquidado transações em 2019 e 2020, elas poderão permanecer liquidadas.

1. Conclua o fechamento do exercício de 2022 sem o recurso de **Reconhecimento** habilitado.
2. Opcional: após a conclusão do fechamento do exercício de 2022, habilite o recurso de **Reconhecimento**. Um fechamento do exercício é considerado concluído quando todos os ajustes são lançados e o processo de fechamento do exercício não será executado novamente.

    > [!IMPORTANT]
    > O recurso de **Reconhecimento** não deverá ser habilitado se o fechamento do exercício de 2022 for executado novamente. A vantagem de habilitar o recurso agora é que você impede os usuários de liquidar transações do razão que foram lançadas em diferentes anos fiscais.

    Se o fechamento do exercício não tiver sido concluído, você ainda poderá seguir as próximas etapas sem habilitar o recurso de **Reconhecimento**. Você habilitará o recurso em uma etapa posterior, conforme indicado.

3. Na página **Liquidação do razão**, identifique o total de todas as transações liquidadas entre os anos fiscais de 2022 e 2023. As transações de 2021 liquidadas em relação a transações de 2022 não são relevantes porque 2022 já foi fechado. Essas transações podem permanecer liquidadas.

    1. Especifique um intervalo de datas para todo o ano fiscal de 2022. Por exemplo, especifique 1º de janeiro de 2022 a 31 de dezembro de 2022, se você estiver usando um ano civil como o ano fiscal.
    2. No campo **Status**, selecione **Liquidada**.
    3. Filtre uma conta do razão por vez.

        - Você terá que repetir essas etapas para cada conta do razão na qual ocorre a liquidação do razão.
        - Se outras contas do razão não estiverem mais configuradas para liquidação do razão, talvez seja necessário adicioná-las temporariamente de volta à configuração de liquidação do razão. Em seguida, siga estas etapas se as contas do razão tiverem transações em 2023 liquidadas em relação a transações em 2022 ou em anos anteriores.

    4. Selecione e segure (ou clique com o botão direito) a coluna **Status** e, em seguida, selecione Agrupar por esta coluna.
    5. Selecione e segure (ou clique com o botão direito) a coluna **Valor na moeda da transação** e, depois, selecione Totalizar esta coluna.

        - Se você liquidar as transações somente em 2022, o total será 0 (zero).
        - Se você tiver transações que foram liquidadas em anos fiscais, o total não será 0 (zero).

    6. Identifique quais transações foram liquidadas entre 2022 e 2023 filtrando pelo valor da **Data de liquidação**. Se você filtrar por uma data de liquidação de 1º de janeiro de 2023 a 31 de dezembro de 2023, terá um total de USD 700, que é o total de transações que foram liquidadas pelo razão em 2022 e 2023.

    ![Total de transações do razão em 2022.](./media/afterYEC2.png)

4. Repita a etapa 3 para o ano fiscal de 2023. O total deve corresponder aos USD 700 de 2022 porque nenhuma transação de 2023 foi liquidada em relação a transações de 2024.

    ![Total de transações do razão em 2023.](./media/afterYEC3.png)

5. Se você habilitou o recurso de **Reconhecimento** na etapa 2, desabilite-o antes de passar para a etapa 6. Nas próximas etapas, você reverterá a liquidação do razão que ultrapassou anos fiscais. Se o recurso de **Reconhecimento** estiver habilitado, a liquidação do razão não poderá ser revertida para o ano fiscal de 2022. Portanto, você precisa desabilitar o recurso antes de continuar.
6. Depois que o recurso de **Reconhecimento** estiver desabilitado, use os mesmos filtros na página **Liquidação do razão** para reverter a liquidação do razão das transações detalhadas.

    1. Retorne à página **Liquidação do razão** e filtre as datas de transação de 2023. Em seguida, localize as transações detalhadas que compõem o total de USD 700. A filtragem dessas informações pode não ser fácil. Talvez seja necessário enviar os dados ao Microsoft Excel para avaliação.
    2. Quando você tiver a lista de transações, selecione as transações do razão na página **Liquidação do razão** e selecione **Marcar selecionada**. Não é necessário ver os dois lados das transações do razão que foram liquidadas. Se você marcar o débito ou o crédito, tudo que tiver o mesmo valor de **ID da liquidação** será revertido, mesmo que o **Valor marcado** não seja **0** (zero).
    3. Selecione **Reverter transações marcadas** para desliquidar as transações.

    ![Reverta transações.](./media/afterYEC4.png)

7. Lance um diário geral de ajuste para dividir o saldo inicial de 2023 em dois valores: a parte liquidada em relação à transação do ano fiscal de 2022 e a parte que ainda não está liquidada em 2023.

    - **Parte do saldo inicial que foi liquidado em relação ao ano anterior:** O primeiro valor é de USD 700, com base nos totais encontrados liquidados entre 2022 e 2023.
    - **Parte do saldo inicial que não foi liquidado em relação ao ano anterior:** O segundo valor é a diferença entre o saldo inicial e o primeiro valor de USD 525. O valor restante é de USD 1700 – USD 700 = USD 1000.

    Desse modo, você pode liquidar as transações de 2023 em relação aos USD 700 que foram originalmente liquidados em relação à transação de 2022. Essa etapa é necessária porque a liquidação do razão não permite liquidação parcial.

    1. Vá para o diário geral e lance o ajuste. Sua organização terá que decidir qual data da transação será usada, com base nos períodos que estão abertos em 2023.
    2. Talvez seja necessário desativar temporariamente o parâmetro **Não permitir entrada manual** na página **Conta principal**. Esse ajuste não será lançado se a conta principal não permitir entrada manual.

    ![O ajuste não está sendo lançado.](./media/afterYEC5.png)

8. Agora você pode reliquidar as transações desliquidadas. Retorne à página **Liquidação do razão** e limite o intervalo de datas a 1º de janeiro de 2022 a 31 de dezembro de 2022. A ilustração a seguir mostra as transações não liquidadas geradas.

    ![Transações não liquidadas.](./media/afterYEC6.png)

    - O saldo inicial de USD 1.700 pode ser liquidado em relação ao ajuste para -USD 1.700.
    - As transações detalhadas que foram desliquidadas para -USD 700 podem ser liquidadas em relação ao ajuste para USD 700.

9. Reabilite o recurso de **Reconhecimento**.
10. Depois que o recurso de **Reconhecimento** estiver habilitado, a liquidação do razão não poderá ser feita entre anos fiscais. Talvez seja necessário dividir ainda mais o saldo restante de USD 1.000 em valores menores antes de liquidar em relação a novas transações em 2023. Alguns clientes optam por lançar esses detalhes durante a etapa 8, em que os USD 1.000 são divididos para representar as transações não liquidadas de 2022. Essa abordagem imita o que o recurso de **Reconhecimento** faz somente para o ano atual. No próximo ano, isso será feito automaticamente usando a configuração **Manter detalhes** na configuração de liquidação do razão.
