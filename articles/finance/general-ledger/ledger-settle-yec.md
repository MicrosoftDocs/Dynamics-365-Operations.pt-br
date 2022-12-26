---
title: Recurso de Reconhecimento entre a liquidação do razão antes do fechamento do exercício
description: Este artigo explica como usar o recurso de Reconhecimento entre liquidações do razão antes da execução do processo de fechamento do exercício da contabilidade.
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
ms.openlocfilehash: c79b6f50296560e1534be0621bb2aa8eaa2c1dc8
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832151"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close"></a>Recurso de Reconhecimento entre a liquidação do razão antes do fechamento do exercício

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-before-year-end-close"></a>Preparar-se para o recurso de Reconhecimento entre a liquidação do razão antes do fechamento do exercício

Uma alteração importante do recurso de **Reconhecimento entre a liquidação do razão e o fechamento do exercício** (o recurso de **Reconhecimento**) é que a liquidação do razão não pode ser feita entre anos fiscais. Esse limite entre anos é relevante apenas para liquidações do razão, não para as liquidações de contas a receber ou contas a pagar.

Antes de habilitar o recurso de **Reconhecimento**, o ano fiscal que passará pelo fechamento do exercício não pode ter nenhuma transação do razão liquidada entre anos fiscais. Especificamente, todas as transações lançadas no ano fiscal para o qual você está executando o fechamento do exercício devem ser desliquidadas das transações que foram lançadas em outro ano fiscal. Então, as transações podem ser reliquidadas em relação a transações no mesmo ano fiscal.

Este artigo descreve as etapas necessárias para identificar, desliquidar e reliquidar as transações do razão que são liquidadas entre os anos fiscais. No exemplo fornecido, o ano fiscal de 2021 foi fechado, e você está se preparando para executar o fechamento do exercício do ano fiscal de 2022.

## <a name="example-setup"></a>Exemplo de configuração

A ilustração a seguir mostra as transações lançadas para a conta principal 110190. As transações do razão em verde são liquidadas no mesmo ano fiscal e não precisam ser alteradas. As transações em vermelho são liquidadas pelo razão, mas têm datas de transação em anos fiscais diferentes. Essas transações devem ser identificadas, e a liquidação do razão pode precisar ser revertida.

![Transações do razão.](./media/YEC1.png)

## <a name="example"></a>exemplo

Siga estas etapas se a sua organização quiser usar o recurso de **Reconhecimento** antes da execução do fechamento do exercício do ano fiscal de 2022.

> [!NOTE]
> O fechamento do exercício de 2021 e dos anos fiscais anteriores só deve ser executado novamente se novas transações forem lançadas no ano fiscal de 2021 ou anteriores. Quando você concluir o procedimento a seguir, nenhuma transação nova será lançada em 2021. Portanto, o fechamento do exercício não precisa ser executado novamente.
>
> As transações do razão que são liquidadas em anos fiscais podem permanecer liquidadas pelo razão se não forem liquidadas em relação a uma transação lançada em 2022 ou em anos posteriores. Por exemplo, se você tiver liquidado transações em 2019 e 2020, elas poderão permanecer liquidadas.

1. Opcional: habilite temporariamente o recurso de **Reconhecimento**.

    - Se você optar por habilitar o recurso, precisará desabilitá-lo em etapas posteriores, conforme indicado. A vantagem de habilitar o recurso agora é que você impede temporariamente os usuários de liquidar transações do razão que foram lançadas em diferentes anos fiscais.
    - Se você optar por não habilitar o recurso, recomendamos que peça à equipe para não liquidar transações entre anos fiscais. Caso a liquidação entre anos ocorra após a conclusão das etapas a seguir, você terá que repetir as etapas para identificar e desliquidar as transações do razão.

2. Na página **Liquidação do razão**, identifique o total de todas as transações liquidadas entre os anos fiscais de 2021 e 2022.

    1. Especifique um intervalo de datas para todo o ano fiscal de 2021. Por exemplo, insira 1º de janeiro de 2021 a 31 de dezembro de 2021, se você estiver usando um ano civil como o ano fiscal.

        Se o recurso de **Reconhecimento** estiver habilitado, você receberá um aviso informando que as transações não podem ser liquidadas ou desliquidadas para um ano fiscal fechado. O aviso não é relevante porque nenhuma liquidação ou desliquidação está ocorrendo nessa etapa.

    2. No campo **Status**, selecione **Liquidada**.
    3. Filtre uma conta do razão por vez.

        - Você terá que repetir essas etapas para cada conta do razão na qual ocorre a liquidação do razão.
        - Se outras contas do razão não estiverem mais configuradas para liquidação do razão, talvez seja necessário adicioná-las temporariamente de volta à configuração de liquidação do razão. Em seguida, siga estas etapas se as contas do razão tiverem transações em 2022 liquidadas em relação a transações em outro ano fiscal.

    4. Selecione e segure (ou clique com o botão direito) a coluna **Status** e, em seguida, selecione Agrupar por esta coluna.
    5. Selecione e segure (ou clique com o botão direito) a coluna **Valor na moeda da transação** e, depois, selecione Totalizar esta coluna.

        - Se você liquidar as transações somente em 2021, o total será 0 (zero).
        - Se você tiver transações que foram liquidadas em anos fiscais, o total não será 0 (zero).

        Na ilustração a seguir, há um saldo de USD 525. Esse saldo é o total das transações que foram liquidadas em relação a transações em outro ano fiscal. O total pode incluir transações que foram liquidadas entre 2021 e 2022 e transações que foram liquidadas entre 2022 e 2023.

        ![Transações do razão de 2021 a 2022.](./media/YEC2.png)

    6. Identifique quais transações foram liquidadas entre 2020 e 2021 filtrando pelo valor da **Data de liquidação**. Especifique um filtro de intervalo de datas de 1º de janeiro de 2021 a 31 de dezembro de 2021. Nenhuma transação é mostrada porque nenhuma transação de 2020 foi liquidada em relação a transações que foram lançadas em 2021.
    7. Identifique quais transações foram liquidadas entre 2021 e 2022 alterando o filtro de datas para o valor da **Data de liquidação**. Especifique um filtro de intervalo de datas de 1º de janeiro de 2022 a 31 de dezembro de 2022. As transações são mostradas novamente, e o total é de USD 525 porque todas as transações foram liquidadas entre 2021 e 2022.

3. Na página **Liquidação do razão**, identifique o total de todas as transações liquidadas entre os anos fiscais de 2021 e 2022.

    1. Especifique um intervalo de datas para todo o ano fiscal de 2022. Por exemplo, especifique 1º de janeiro de 2022 a 31 de dezembro de 2022, se você estiver usando um ano civil como o ano fiscal.
    2. No campo **Status**, selecione **Liquidada**.
    3. Filtre uma conta do razão por vez.
    4. Selecione e segure (ou clique com o botão direito) a coluna **Status** e, em seguida, selecione Agrupar por esta coluna.
    5. Selecione e segure (ou clique com o botão direito) a coluna **Valor na moeda da transação** e, depois, selecione Totalizar esta coluna.

        ![Valores totais das transações do razão.](./media/YEC3.png)

    6. Adicione mais um filtro ao valor da **Data de liquidação**. Especifique um filtro de intervalo de datas de 1º de janeiro de 2022 a 31 de dezembro de 2022. O mesmo total de USD 525 é mostrado. Esse resultado valida que o valor total das transações liquidadas entre 2021 e 2022 é de USD 525.

        ![Transações do razão para datas de liquidação em 2022 e 2023.](./media/YEC4.png)

    7. Altere o filtro adicional no valor da **Data de liquidação**. Especifique um filtro de intervalo de datas de 1º de janeiro de 2023 a 31 de dezembro de 2023. É exibido um novo total de USD 700. Esse total é o valor total das transações que foram liquidadas entre 2022 e 2023.
 
4. Repita a etapa 3 para o ano fiscal de 2023. O total deve corresponder aos USD 700 de 2022 porque nenhuma transação de 2023 foi liquidada em relação a transações de 2024.
5. Se você habilitou o recurso de **Reconhecimento** na etapa 1, desabilite-o antes de passar para a etapa 6. Nas próximas etapas, você reverterá a liquidação do razão que ultrapassou anos fiscais. Se o recurso de **Reconhecimento** estiver habilitado, a liquidação do razão não poderá ser revertida para o ano fiscal de 2021. Portanto, você precisa desabilitar o recurso antes de continuar.
6. Depois que o recurso de **Reconhecimento** estiver desabilitado, use os mesmos filtros na página **Liquidação do razão** para reverter a liquidação do razão das transações detalhadas.

    1. Retorne à página **Liquidação do razão** e filtre as datas de transação de 2021. Adicione mais um filtro ao valor da **Data de liquidação**. Especifique um filtro de intervalo de datas de 1º de janeiro de 2022 a 31 de dezembro de 2022. Em seguida, localize as transações detalhadas que compõem o total de USD 525. A filtragem dessas informações pode não ser fácil. Talvez seja necessário enviar os dados ao Microsoft Excel para avaliação.
    2. Quando você tiver a lista de transações, selecione as transações do razão na página **Liquidação do razão** e selecione **Marcar selecionada**. Não é necessário ver os dois lados das transações do razão que foram liquidadas. Se você marcar o débito ou o crédito, tudo que tiver o mesmo valor de **ID da liquidação** será revertido, mesmo que o **Valor marcado** não seja **0** (zero).
    3. Selecione **Reverter transações marcadas** para desliquidar as transações.

    ![Reverta as transações marcadas.](./media/YEC5.png)

7. Repita a etapa 6 para reverter a liquidação das transações que foram liquidadas entre 2022 e 2023.

    ![Reverta as transações do razão.](./media/YEC6.png)

8. Lance um diário geral de ajuste para dividir o saldo inicial de 2022 em dois valores: a parte liquidada em relação à transação do ano fiscal de 2021 e a parte que ainda não está liquidada em 2022.

    - **Parte do saldo inicial que foi liquidado em relação ao ano anterior:** O primeiro valor é de USD 525, com base nos totais encontrados que foram liquidados entre 2021 e 2022.
    - **Parte do saldo inicial que não foi liquidado em relação ao ano anterior:** O segundo valor é a diferença entre o saldo inicial e o valor liquidado de USD 525. O valor restante é de USD 1.025 – USD 525 = USD 500.

    Desse modo, você pode liquidar as transações de 2022 em relação aos USD 525 que foram originalmente liquidados em relação à transação de 2021. Essa etapa é necessária porque a liquidação do razão não permite liquidação parcial.

    1. Vá para o diário geral e lance o ajuste. Sua organização terá que decidir qual data da transação será usada, com base nos períodos que estão abertos. Essas transações podem ter sido liquidadas usando uma data de liquidação de janeiro ou fevereiro de 2022, mas o ajuste pode ter de ser lançado em dezembro, se esse for o único período aberto.
    2. Talvez seja necessário desativar temporariamente o parâmetro **Não permitir entrada manual** na página **Conta principal**. Esse ajuste não será lançado se a conta principal não permitir entrada manual.

    ![O ajuste não está sendo lançado.](./media/YEC7.png)

9. Agora você pode reliquidar as transações desliquidadas. Retorne à página **Liquidação do razão** e limite o intervalo de datas a 1º de janeiro de 2022 a 31 de dezembro de 2022. A ilustração a seguir mostra as transações não liquidadas geradas.

    ![Transações não liquidadas.](./media/YEC8.png)

    - O saldo inicial de USD 1.025 pode ser liquidado em relação ao ajuste para -USD 1.025.
    - As transações detalhadas que foram desliquidadas para -USD 400, -USD 50 e -USD 75 podem ser liquidadas em relação ao ajuste para USD 525.

    ![Transações detalhadas.](./media/YEC9.png)

10. Habilite o recurso de **Reconhecimento**. Agora você pode executar o fechamento do exercício.

    - Antes de executar o fechamento do exercício, considere marcar a opção **Manter detalhes** na configuração de liquidação do razão para todas as contas de balanço. Para obter mais informações sobre as vantagens de concluir esta etapa, consulte o documento sobre Reconhecimento.
    - Ao iniciar o fechamento do exercício de 2022, se ainda forem encontradas transações liquidadas entre os anos fiscais, o processo de fechamento do exercício notificará você imediatamente.
    - Se as transações de 2021 e 2022 ainda estiverem liquidadas, você terá que desabilitar o recurso de **Reconhecimento** novamente e repetir as etapas anteriores para desliquidar as transações. Essa abordagem é necessária porque 2021 está fechado, e as transações não podem ser desliquidadas em um ano fiscal fechado.
    - Se as transações de 2022 e 2023 ainda estiverem liquidadas, você **não** precisará desabilitar o recurso de **Reconhecimento**. Como nem 2022 nem 2023 estão fechados, você pode seguir as etapas anteriores para desliquidar as transações.

Depois que o fechamento do exercício de 2022 for executado com êxito, você poderá deixar o recurso de **Reconhecimento** habilitado desse momento em diante.
