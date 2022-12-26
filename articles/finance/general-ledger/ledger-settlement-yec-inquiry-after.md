---
title: Recurso de Reconhecimento entre liquidações do razão depois do fechamento do exercício da contabilidade usando a página de consulta
description: Este artigo explica como usar o recurso de Reconhecimento entre liquidações do razão usando a nova página de consulta após a execução do fechamento do exercício da contabilidade.
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
ms.openlocfilehash: 921d2a17409ae10cd9c22eeca11557ba1248b9bc
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853113"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close-using-the-inquiry-page"></a>Recurso de Reconhecimento entre liquidações do razão depois do fechamento do exercício da contabilidade usando a página de consulta

Uma alteração importante do recurso de **Reconhecimento entre a liquidação do razão e o fechamento do exercício** (o recurso de **Reconhecimento**) é que a liquidação do razão não pode ser feita entre anos fiscais. Esse limite entre anos é relevante apenas para liquidações do razão, não para as liquidações de contas a receber ou contas a pagar.

Antes de habilitar o recurso de **Reconhecimento**, o ano fiscal que passará pelo fechamento do exercício não pode ter nenhuma transação do razão liquidada entre anos fiscais. Especificamente, todas as transações lançadas no ano fiscal para o qual você está executando o fechamento do exercício devem ser desliquidadas das transações que foram lançadas em outro ano fiscal. Então, as transações podem ser reliquidadas em relação a transações no mesmo ano fiscal.

Este artigo descreve as etapas necessárias para identificar, desliquidar e reliquidar transações do razão que são liquidadas entre os anos. No exemplo fornecido, o ano fiscal de 2022 foi fechado. O foco é a preparação das transações de liquidação do razão antes da execução do fechamento do exercício da contabilidade de 2023.

A partir do Microsoft Dynamics 365 Finance versão 10.0.29, você pode identificar, desliquidar e reliquidar transações do razão usando uma nova página de consulta disponível. Se você não está usando o Microsoft Dynamics 365 Finance versão 10.0.29 ou posterior, veja as etapas para identificar, desliquidar e reliquidar as transações do razão nos seguintes artigos:

- [Recurso de Reconhecimento entre a liquidação do razão antes do fechamento do exercício](ledger-settle-yec.md)
- [Recurso de Reconhecimento entre a liquidação do razão depois do fechamento do exercício](ledger-settle-yec-after.md)

Para obter mais informações sobre a nova janela de consulta, acesse [Consulta de liquidação do razão](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Exemplo de configuração

A ilustração a seguir mostra as transações lançadas para a conta principal 110200. As transações em verde foram liquidadas pelo razão no mesmo ano fiscal e não precisam ser alteradas. As transações em vermelho foram liquidadas pelo razão, mas têm datas de transação em anos fiscais diferentes. Essas transações devem ser identificadas, e a liquidação do razão pode precisar ser revertida.

![Transações do razão lançadas.](./media/excel.png)

## <a name="example"></a>exemplo

Siga estas etapas se a sua organização quiser usar o recurso de **Reconhecimento** depois que você executar o fechamento do exercício do ano fiscal de 2022.

> [!NOTE]
> O fechamento do exercício de 2022 e dos anos fiscais anteriores só deve ser executado novamente se novas transações forem lançadas no ano fiscal de 2022 ou anteriores. Quando você concluir o procedimento a seguir, nenhuma transação nova será lançada em 2022. Portanto, o fechamento do exercício não precisa ser executado novamente.
>
> As transações do razão que são liquidadas em anos fiscais podem permanecer liquidadas pelo razão se não forem liquidadas em relação a uma transação lançada em 2022 ou em anos posteriores. Por exemplo, se você tiver liquidado transações em 2019 e 2020, elas poderão permanecer liquidadas.

1. Conclua o fechamento do exercício de 2022 sem o recurso de **Reconhecimento** habilitado.
2. Identifique todas as transações que foram lançadas em outros anos fiscais, mas liquidadas em relação a transações que foram lançadas em 2023 (o próximo ano fiscal que será fechado).

    > [!NOTE]
    > As transações de 2021 que foram liquidadas em relação a transações de 2022 não são relevantes porque o ano já foi fechado para 2022. Essas transações podem permanecer liquidadas.

    1. Na página **Liquidações do razão**, selecione **Examinar liquidações entre anos**.
    2. Selecione o ano fiscal de 2023, o próximo ano fiscal para o qual você quer executar o processo de fechamento do exercício.
    3. Selecione um valor no campo **Conjunto de dimensões financeiras** para mostrar as dimensões financeiras que você deseja exibir para a conta do razão. A conta principal será sempre mostrada, mesmo que o conjunto de dimensões selecionado não contenha uma conta principal.
    4. Selecione **Mostrar transações**.

    A página de consulta mostrará todas as transações de outros anos fiscais que são liquidadas em relação a transações que foram lançadas em 2023.

    ![Liquidações entre anos de 2023.](./media/2023-cross-settlement.png)

3. Selecione e segure (ou clique com o botão direito do mouse) na grade e, depois, selecione **Exportar todas as linhas**. Essas linhas são todas as transações que devem ser desliquidadas a partir das transações em 2022 antes da execução do fechamento do exercício do ano seguinte (2023). Você quer ter um registro dessas transações.

    Depois que todas as transações detalhadas de 2022 forem exportadas para o Excel, você estará pronto para desliquidar as transações usando a página de consulta.

4. Selecione todos os registros na grade e, depois, selecione **Desliquidar registros marcados**. Todas as transações selecionadas na grade serão desliquidadas.

    Duas mensagens de aviso são exibidas para garantir que os detalhes da transação sejam exportados para o Excel antes que as transações sejam desliquidadas. Se você desliquidar acidentalmente as transações do razão antes de enviar os detalhes para o Excel, não há como reverter a desliquidação.

    ![Desliquidar liquidações entre anos.](./media/revert-settlement.png)

5. Use os dados do Excel para encontrar o valor total das transações em 2022 que foram liquidadas para transações em 2023. Neste exemplo, as transações de 2023 totalizam USD 700.
6. Lance um diário geral de ajuste para dividir o saldo inicial de 2022 em dois valores: a parte liquidada em relação à transação do ano fiscal de 2022 e a parte que ainda não foi liquidada para 2023.

    - **Parte do saldo inicial que foi liquidado para o ano anterior:** O primeiro valor é de USD 700, com base nos totais encontrados que foram liquidados entre 2021 e 2022.
    - **Parte do saldo inicial que não foi liquidado para o ano anterior:** O segundo valor é a diferença entre o saldo inicial e o valor liquidado de USD 700. O valor restante é de USD 1.700 – USD 700 = USD 1.000.

    Desse modo, você pode liquidar as transações de 2023 em relação aos USD 700 que foram originalmente liquidados em relação à transação de 2022. Essa etapa é necessária porque a liquidação do razão não permite liquidação parcial.

    1. Vá para o diário geral e lance o ajuste. Sua organização terá que decidir qual data da transação será usada, com base nos períodos que estão abertos em 2023.
    2. Talvez seja necessário desativar temporariamente o parâmetro **Não permitir entrada manual** na página **Conta principal**. Esse ajuste não será lançado se a conta principal não permitir entrada manual.

    ![Lançar um diário geral de ajuste.](./media/no-manual4.png)

7. Agora você pode reliquidar as transações desliquidadas. Retorne à página **Liquidações do razão** e limite o intervalo de datas a 1º de janeiro a 31 de dezembro de 2023. Em seguida, use as transações detalhadas exportadas para o Excel para localizar as transações específicas que precisam ser reliquidadas. A ilustração a seguir mostra as transações não liquidadas geradas.

    ![Transações não liquidadas para 2023.](./media/2023-unsettled5.png)

    - O saldo inicial de USD 1.700 pode ser liquidado em relação ao ajuste para -USD 1.700.
    - As transações detalhadas que foram desliquidadas para -USD 700 podem ser liquidadas em relação ao ajuste para USD 700.

8. Habilite o recurso de **Reconhecimento**. Agora você pode executar o fechamento do exercício.

    - Antes de executar o fechamento do exercício de 2023, considere marcar a opção **Manter detalhes** para todas as contas de balanço na configuração de liquidação do razão. Para obter mais informações, consulte [Reconhecimento entre a liquidação do razão e o fechamento do exercício](awareness-between-ledger-settlement-year-end-close.md).
    - Ao iniciar o fechamento do exercício de 2023, se ainda forem encontradas transações que foram liquidadas entre os anos fiscais, o processo de fechamento do exercício notificará você imediatamente. Essa situação poderá ocorrer se os usuários liquidarem transações entre anos fiscais antes da habilitação do recurso de **Reconhecimento**.
    - Se as transações de 2022 e 2023 ainda estiverem liquidadas, você terá que desabilitar o recurso de **Reconhecimento** novamente e repetir as etapas anteriores para desliquidar essas transações. Essa abordagem é necessária porque 2022 está fechado, e as transações não podem ser desliquidadas em um ano fiscal fechado.

Depois que o fechamento do exercício de 2022 for executado com êxito, você poderá deixar o recurso de **Reconhecimento** habilitado desse momento em diante.
