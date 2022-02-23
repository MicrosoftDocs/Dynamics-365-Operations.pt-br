---
title: Adiar a execução de elementos de sequência nos formatos de ER
description: Este tópico explica como adiar a execução de um elemento de sequência em um formato de ER (Relatório eletrônico).
author: NickSelin
manager: kfend
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-01
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 9aa019e20b218fdaad4659fa65d9df629069204b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680725"
---
# <a name="defer-the-execution-of-sequence-elements-in-er-formats"></a>Adiar a execução de elementos de sequência nos formatos de ER

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Visão geral

Você pode usar o Designer de operações da estrutura do [ER (Relatório eletrônico)](general-electronic-reporting.md) para [configurar](tasks/er-format-configuration-2016-11.md) o [componente de formato](general-electronic-reporting.md#FormatComponentOutbound) de uma solução ER que é usada para gerar documentos de saída em um formato de texto. A estrutura hierárquica do componente de formato configurado consiste em elementos de formato de vários tipos. Esses elementos de formato são usados para preencher documentos gerados com as informações necessárias no tempo de execução. Por padrão, quando você executa um formato de ER, os elementos de formato são executados na mesma ordem em que são apresentados na hierarquia de formato: um por um, de cima para baixo. No entanto, no tempo de design, você pode alterar a ordem de execução de qualquer elemento de sequência do componente de formato configurado.

Ao ativar a opção <a name="DeferredSequenceExecution"></a>**Execução adiada** para um elemento de formato de sequência no formato configurado, você pode adiar (postergar) a execução desse elemento. Nesse caso, o elemento não será executado até que todos os outros elementos de seu pai tenham sido executados.

Para saber mais sobre este recurso, conclua o exemplo neste tópico.

## <a name="limitations"></a>Limitações

A opção **Execução adiada** só tem suporte para os elementos de sequência que são configurados para um formato de ER usado para gerar documentos de **saída** no formato de texto.

A opção **Execução adiada** não se aplica a sequências que foram configuradas como sequências aparadas em que o comprimento máximo é limitado.

## <a name="example-defer-the-execution-of-a-sequence-element-in-an-er-format"></a><a name="Example"></a>Exemplo: Adiar a execução de um elemento de sequência em um formato de ER

As etapas a seguir explicam como um usuário na [função](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/assign-users-security-roles) de Administrador do sistema ou de Consultor funcional de relatório eletrônico pode configurar um formato de ER que contém um elemento de sequência em que a ordem da execução difere da ordem na hierarquia de formato.

Essas etapas podem ser executadas na empresa **USMF** no Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Pré-requisitos

Para concluir este exemplo, você deve ter acesso à empresa **USMF** no Finance para uma das seguintes funções:

- Consultor funcional de relatório eletrônico
- Administrador do sistema

Se você ainda não tiver concluído o exemplo no tópico [Adiar a execução de elementos XML nos formatos de ER](er-defer-xml-element.md#Example), baixe as [configurações](general-electronic-reporting.md#Configuration) a seguir do exemplo da solução ER.

| Descrição do conteúdo            | Nome do arquivo |
|--------------------------------|-----------|
| Configuração do modelo de dados de ER    | [Modelo para conhecer elementos adiados.versão.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Configuração de mapeamento do modelo de ER | [Mapeamento para conhecer elementos adiados.versão.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Antes de começar, você também deve baixar e salvar a configuração a seguir do exemplo da solução ER.

| Descrição do conteúdo     |Nome do arquivo |
|-------------------------|----------|
| Configuração de formato ER | [Formato para conhecer sequências adiadas.versão.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="import-the-sample-er-configurations"></a>Importar o exemplo de configurações de ER

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Selecione **Configurações de relatórios**.
3. Na página **Configurações**, se a configuração **Modelo para conhecer elementos adiados** não estiver disponível na árvore de configuração, importe a configuração do modelo de dados do ER:

    1. Selecione **Troca** e, em seguida, **Carregar de um arquivo XML**.
    2. Selecione **Procurar**, encontre e selecione o arquivo **Modelo para conhecer elementos adiados.1.xml** e selecione **OK**.

4. Se a configuração **Mapeamento para conhecer elementos adiados** não estiver disponível na árvore de configuração, importe a configuração do mapeamento de modelo do ER:

    1. Selecione **Troca** e, em seguida, **Carregar de um arquivo XML**.
    2. Selecione **Procurar**, encontre e selecione o arquivo **Mapeamento para conhecer elementos adiados.1.1.xml** e selecione **OK**.

5. Importe a configuração de formato de ER:

    1. Selecione **Troca** e, em seguida, **Carregar de um arquivo XML**.
    2. Selecione **Procurar**, encontre e selecione o arquivo **Formato para conhecer sequências adiadas.1.1.xml** e selecione **OK**.

6. Na árvore de configuração, expanda **Modelo para conhecer elementos adiados**.
7. Revise a lista de configurações de ER importadas na árvore de configuração.

    ![Configurações de ER importadas na página Configurações](./media/ER-DeferredSequence-Configurations.png)

### <a name="activate-a-configurations-provider"></a>Ativar um provedor de configurações

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, verifique se o [provedor de configuração](general-electronic-reporting.md#Provider) para a empresa de exemplo Litware, Inc. (`http://www.litware.com`) está listado e marcado como ativo. Se esse provedor de configuração não estiver listado, ou se ele não estiver marcado como ativo, siga as etapas no tópico [Criar um provedor de configuração e marcá-lo como ativo](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![A empresa de exemplo Litware, Inc. na página Configurações de localização](./media/ER-DeferredSequence-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>Revise o mapeamento do modelo importado

Examine as configurações do componente de mapeamento do modelo de ER que é configurado para acessar as transações de imposto e expor dados acessados na solicitação.

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Selecione **Configurações de relatórios**.
3. Na página **Configurações**, na árvore de configuração, expanda **Modelo para conhecer elementos adiados**.
4. Selecione a configuração **Mapeamento para conhecer elemento adiados**.
5. Selecione **Designer** para abrir a lista de mapeamentos.
6. Selecione **Designer** para revisar os detalhes do mapeamento.
7. Selecione **Mostrar detalhes**.
8. Revise as fontes de dados configuradas para acessar transações de imposto:

    - A fonte de dados **Transações** do tipo *Registro de tabela* é configurada para acessar registros da tabela de aplicativos **TaxTrans**.
    - A fonte de dados **Comprovantes** do tipo *Campo calculado* é configurada para retornar os códigos de comprovantes necessários (**INV-10000349** e **INV-10000350**) como uma lista de registros.
    - A fonte de dados **Filtrados** do tipo *Campo calculado* é configurada para selecionar, na fonte de dados **Transações**, somente as transações de imposto dos comprovantes necessários.
    - O campo **\$TaxAmount** do tipo *Campo calculado* é adicionado para a fonte de dados **Filtrados** de modo a expor o valor do imposto que tem o sinal oposto.
    - A fonte de dados **Agrupados** do tipo *Agrupar por* é configurada para agrupar transações de imposto filtradas da fonte de dados **Filtrados**.
    - O campo de agregação **TotalSum** da fonte de dados **Agrupados** é configurado para resumir valores do campo **\$TaxAmount** da fonte de dados **Filtrados** para todas as transações de imposto filtradas dessa fonte de dados.

        ![Campo de agregação TotalSum na página Editar parâmetros 'GroupBy'](./media/ER-DeferredSequence-GroupByParameters.png)

9. Revise como as fontes de dados configuradas são associadas ao modelo de dados e como elas expõem os dados acessados para torná-los disponíveis em um formato de ER:

    - A fonte de dados **Filtrados** é associada ao campo **Data.List** do modelo de dados.
    - O campo **\$TaxAmount** da fonte de dados **Filtrados** é associado ao campo **Data.List.Value** do modelo de dados.
    - O campo **TotalSum** da fonte de dados **Agrupados** é associado ao campo **Data.Summary.Total** do modelo de dados.

    ![Página do designer de mapeamento de modelo](./media/ER-DeferredSequence-ModelMapping.png)

10. Feche as páginas **Designer de mapeamento de modelo** e **Mapeamentos de modelo**.

### <a name="review-the-imported-format"></a>Examine o formato importado

1. Na página **Configurações**, na árvore de configuração, selecione a configuração **Formato para conhecer sequências adiadas**.
2. Selecione **Designer** para revisar os detalhes do formato.
3. Selecione **Mostrar detalhes**.
4. Examine as configurações dos componentes de formato de ER que estão configurados para gerar um documento de saída no formato de texto que inclui detalhes das transações de imposto:

    - O elemento do formato de sequência **Relatório\\Linhas** é configurado para preencher o documento de saída com uma única linha que é gerada dos elementos de sequência aninhados (**Cabeçalho**, **Registro** e **Resumo**).

        ![Elemento do formato de sequência de linhas e elementos aninhados na página Designer de formato](./media/ER-DeferredSequence-Format.png)

    - O elemento do formato de sequência **Relatório\\Linhas\\Cabeçalho** é configurado para preencher o documento de saída com uma única linha de cabeçalho que mostra a data e a hora do início do processamento.
    - O elemento do formato de sequência **Relatório \\Linhas\\Registro** é configurado para preencher o documento de saída com uma única linha que mostra os detalhes das transações de imposto individuais. Essas transações de imposto são separadas por um ponto-e-vírgula.

        ![Elemento do formato de sequência de registro que usa um ponto-e-vírgula como delimitador](./media/ER-DeferredSequence-Format1.png)

    - O elemento do formato de sequência **Relatório\\Linhas\\Resumo** é configurado para preencher o documento de saída com uma única linha de resumo que inclui a soma dos valores de imposto das transações de imposto processadas.

4. Na guia **Mapeamento**, revise os seguintes detalhes:

    - O elemento **Relatório\\Linhas\\Cabeçalho** não precisa estar associado a uma fonte de dados para gerar uma única linha em um documento de saída.
    - O elemento **Prefix1** gera símbolos **P1** para indicar que a linha adicionada é a linha de cabeçalho do relatório.
    - O elemento **ExecutionDateTime** gera a data e a hora (incluindo milissegundos) quando a linha de cabeçalho é adicionada.
    - O elemento **Relatório\\Linhas\\Registro** é associado à lista **model.Data.List** de modo a gerar uma única linha para cada registro a partir da lista associada.
    - O elemento **Prefix2** gera símbolos **P2** para indicar que a linha adicionada serve para os detalhes de transação de imposto.
    - O elemento **TaxAmount** é associado a **model.Data.List.Value** (que é mostrado como **\@.Value** na exibição de caminho relativo) para gerar o valor de imposto da transação de imposto atual.
    - O elemento **RunningTotal** é um espaço reservado para o total acumulado dos valores de imposto. No momento, esse elemento não tem saída, pois nem uma associação nem um valor padrão é configurado para ele.
    - O elemento **ExecutionDateTime** gera a data e a hora (incluindo milissegundos) quando a transação atual é processada nesse relatório.
    - O elemento **Relatório\\Linhas\\Resumo** não precisa estar associado a uma fonte de dados para gerar uma única linha em um documento de saída.
    - O elemento **Prefix3** gera símbolos **P3** para indicar que a linha adicionada contém o valor total de imposto.
    - O elemento **TotalTaxAmount** é associado a **model.Data.Summary.Total** para gerar a soma dos valores de imposto das transações de imposto processadas.
    - O elemento **ExecutionDateTime** gera a data e a hora (incluindo milissegundos) quando a linha de resumo é adicionada.

    ![Guia Mapeamento na página Designer de formato](./media/ER-DeferredSequence-Format2.png)

### <a name="run-the-imported-format"></a>Executar o formato importado

1. Na página **Designer de formato**, selecione **Executar**.
2. Baixe o arquivo oferecido pelo navegador da Web e abra-o para revisão.

    ![Arquivo baixado](./media/ER-DeferredSequence-Run.png)

Observe que a linha de resumo 22 apresenta a soma dos valores de imposto para as transações processadas. Como o formato está configurado para usar a associação **model.Data.Summary.Total** de modo a retornar essa soma, a soma é calculada chamado a agregação **TotalSum** da fonte de dados **Agrupados** do tipo *GroupBy* que usa o mapeamento de modelo. Para calcular essa agregação, o mapeamento de modelos itera em todas as transações que foram selecionadas na fonte de dados **Filtrados**. Ao comparar os tempos de execução das linhas 21 e 22, você pode determinar que o cálculo da soma levou 10 milissegundos (ms). Ao comparar os tempos de execução das linhas 2 e 21, você pode determinar que a geração de todas as linhas transacionais levou 7 ms. Portanto, foi necessário um total de 17 ms.

### <a name="modify-the-format-so-that-the-summing-is-based-on-generated-output"></a>Modificar o formato para que a soma seja baseada na saída gerada

Se o volume de transações for muito maior do que o volume no exemplo atual, o tempo de soma poderá aumentar e causar problemas de desempenho. Ao alterar a configuração do formato, você pode ajudar a evitar esses problemas de desempenho. Como você acessa valores de impostos para incluí-los no relatório gerado, é possível reutilizar essas informações para somar os valores de imposto. Para obter mais informações, consulte [Configurar o formato para contagem e soma](./tasks/er-format-counting-summing-1.md).

1. Na página **Designer de formato**, na guia **Formatar**, selecione o elemento de arquivo **Relatório** na árvore de formatos.
2. Defina a opção **Coletar detalhes de saída** como **Sim**. Agora você pode configurar esse formato usando o conteúdo de um relatório existente como uma fonte de dados que pode ser acessada usando as funções internas de ER na categoria [Coleta de dados](er-functions-category-data-collection.md).
3. Na guia **Mapeamento**, selecione o elemento sequência **Relatório\\Linhas**.
4. Configure a expressão **Nome da chave de dados coletada** como `WsColumn`.
5. Configure a expressão **Valor da chave de dados coletada** como `WsRow`.

    ![Elemento da sequência de linhas na página Designer de formato](./media/ER-DeferredSequence-Format3.png)

6. Selecione o elemento numérico **Relatório\\Linhas\\Registro\\TaxAmount**.
7. Configure a expressão **Nome da chave de dados coletada** como `SummingAmountKey`.

    ![Elemento numérico TaxAmount na página Designer de formato](./media/ER-DeferredSequence-Format4.png)

    Você pode considerar essa configuração o preenchimento de uma planilha virtual, em que o valor da célula A1 é acrescentado ao valor do imposto de cada transação de imposto processada.

8. Selecione o elemento numérico **Relatório\\Linhas\\Registro\\RunningTotal** e, em seguida, **Editar fórmula**.
9. Configure a expressão `SUMIF(SummingAmountKey, WsColumn, WsRow)` usando a função interna de ER [SUMIF](er-functions-datacollection-sumif.md).
10. Selecione **Salvar**.

    ![Expressão SUMIF](./media/ER-DeferredSequence-FormulaDesigner.png)

11. Feche a página **Designer de fórmulas**.
12. Selecione **Salvar** e **Executar**.
13. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado](./media/ER-DeferredSequence-Run1.png)

    A linha 21 contém o total acumulado de valores de imposto que é calculado para todas as transações processadas usando a saída gerada como uma fonte de dados. Essa fonte de dados é iniciada desde o começo do relatório e continua até a última transação de imposto. A linha 22 contém a soma dos valores de imposto para todas as transações processadas que são calculadas no mapeamento de modelo usando a fonte de dados do tipo *GroupBy*. Observe que esses valores são iguais. Portanto, a soma baseada na saída pode ser usada no lugar de **GroupBy**. Ao comparar os tempos de execução das linhas 2 e 21, você pode determinar que a geração de todas as linhas transacionais e a soma levou 9 ms. Portanto, no que diz respeito à geração de linhas detalhadas e à soma dos valores de imposto, o formato modificado é aproximadamente duas vezes mais rápido do que o formato original.

14. Selecione o elemento numérico **Relatório\\Linhas\\Resumo\\TotalTaxAmount** e, em seguida, **Editar fórmula**.
15. Insira a expressão `SUMIF(SummingAmountKey, WsColumn, WsRow)` no lugar da expressão existente.
16. Selecione **Salvar** e **Executar**.
17. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado](./media/ER-DeferredSequence-Run2.png)

    Observe que o total acumulado dos valores de imposto na última linha dos detalhes da transação agora é igual à soma na linha de resumo.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Colocar valores da soma baseada na saída no cabeçalho do relatório

Se você tiver que apresentar a soma dos valores de imposto no cabeçalho do relatório, por exemplo, é possível modificar o formato.

1. Na página **Designer de formato**, na guia **Formatar**, selecione o elemento de sequência **Relatório\\Linhas\\Resumo**.
2. Selecione **Mover para cima**.
3. Selecione **Salvar** e **Executar**.
4. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado](./media/ER-DeferredSequence-Run3.png)

    Observe que a soma dos valores de imposto na linha de resumo 2 agora é igual a 0 (zero), pois a soma agora é calculada com base na saída gerada. Quando a linha 2 é gerada, a saída gerada ainda não contém linhas com detalhes da transação. É possível configurar esse formato para adiar a execução do elemento de sequência **Relatório\\Linhas\\Resumo** até que o elemento de sequência **Relatório\\Linhas\\Registro** tenha sido executado para todas as transações de imposto.

### <a name="defer-the-execution-of-the-summary-sequence-so-that-the-calculated-total-is-used"></a>Adiar a execução da sequência de resumo para que o total calculado seja usado

1. Na página **Designer de formato**, na guia **Formatar**, selecione o elemento de sequência **Relatório\\Linhas\\Resumo**.
2. Defina a opção **Execução adiada** como **Sim**.

    ![Opção Execução adiada do elemento de sequência Resumo na página Designer de formato](./media/ER-DeferredSequence-Format5.png)

3. Selecione **Salvar** e **Executar**.
4. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado](./media/ER-DeferredSequence-Run4.png)

    O elemento de sequência **Relatório\\Linhas\\Resumo** agora é executado somente depois que todos os outros itens que estão aninhados sob seu elemento pai, **Relatório\\Linhas**, tiverem sido executados. Portanto, ele é executado depois que o elemento de sequência **Relatório\\Linhas\\Registro** tiver sido executado para todas as transações de imposto da fonte de dados **model.Data.List**. Os tempos de execução das linhas 1, 2 e 3, e da última linha, 22, revelam esse fato.

## <a name="additional-resources"></a>Recursos adicionais

- [Configurar o formato para contagem e soma](./tasks/er-format-counting-summing-1.md)
- [Rastrear a execução do formato ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md)
- [Adiar a execução de elementos XML nos formatos de ER](er-defer-xml-element.md#Example)
