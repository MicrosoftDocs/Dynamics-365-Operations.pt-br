---
title: Adiar a execução de elementos XML nos formatos de ER
description: Este tópico explica como adiar a execução de um elemento de XML em um formato de ER (Relatório eletrônico).
author: NickSelin
manager: kfend
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: f9a19f4ba6bb124de948dcd9e62b258b2178687a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562133"
---
# <a name="defer-the-execution-of-xml-elements-in-er-formats"></a>Adiar a execução de elementos XML nos formatos de ER

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Visão geral

Você pode usar o Designer de operações da estrutura do [ER (Relatório eletrônico)](general-electronic-reporting.md) para [configurar](./tasks/er-format-configuration-2016-11.md) o [componente de formato](general-electronic-reporting.md#FormatComponentOutbound) de uma solução ER que é usada para gerar documentos de saída em um formato XML. A estrutura hierárquica do componente de formato configurado consiste em elementos de formato de vários tipos. Esses elementos de formato são usados para preencher documentos gerados com as informações necessárias no tempo de execução. Por padrão, quando você executa um formato de ER, os elementos de formato são executados na mesma ordem em que são apresentados na hierarquia de formato: um por um, de cima para baixo. No entanto, no tempo de design, você pode alterar a ordem de execução de qualquer elemento XML do componente de formato configurado.

Ao ativar a opção <a name="DeferredXmlElementExecution"></a>**Execução adiada** para um elemento XML no formato configurado, você pode adiar (postergar) a execução desse elemento. Nesse caso, o elemento não será executado até que todos os outros elementos de seu pai tenham sido executados.

Para saber mais sobre este recurso, conclua o exemplo neste tópico.

## <a name="limitations"></a>Limitações

A opção **Execução adiada** só tem suporte para os elementos XML que são configurados para um formato de ER usado para gerar documentos de **saída** no formato XML.

A opção **Execução adiada** só tem suporte para elementos XML que residem apenas em um outro elemento XML. Portanto, ela não se aplica a elementos XML que residem em outros tipos de elemento de formato (por exemplo, em um elemento de **sequência XML)**.

A opção **Execução adiada** não tem suporte para elementos XML que residem no elemento de formato **Comum\\Arquivo** quando a opção **Dividir arquivo** é definida como **Sim**. Para obter mais informações sobre como dividir arquivos XML, consulte [Dividir arquivos XML gerados com base no tamanho do arquivo e na quantidade de conteúdo](er-split-files.md).

## <a name="example-defer-the-execution-of-an-xml-element-in-an-er-format"></a><a name="Example"></a>Exemplo: Adiar a execução de um elemento XML em um formato de ER

As etapas a seguir explicam como um usuário na [função](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/assign-users-security-roles) de Administrador do sistema ou de Consultor funcional de relatório eletrônico pode configurar um formato de ER que contém um elemento XML em que a ordem da execução difere da ordem na hierarquia de formato.

Essas etapas podem ser executadas na empresa **USMF** no Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Pré-requisitos

Para concluir este exemplo, você deve ter acesso à empresa **USMF** no Finance para uma das seguintes funções:

- Consultor funcional de relatório eletrônico
- Administrador do sistema

Se você ainda não tiver concluído o exemplo no tópico [Adiar a execução de elementos de sequência nos formatos de ER](er-defer-sequence-element.md#Example), baixe as [configurações](general-electronic-reporting.md#Configuration) a seguir do exemplo da solução ER.

| Descrição do conteúdo            | Nome do arquivo |
|--------------------------------|-----------|
| Configuração do modelo de dados de ER    | [Modelo para conhecer elementos adiados.versão.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Configuração de mapeamento do modelo de ER | [Mapeamento para conhecer elementos adiados.versão.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Antes de começar, você também deve baixar e salvar a configuração a seguir do exemplo da solução ER no seu computador local.

| Descrição do conteúdo     | Nome do arquivo |
|-------------------------|-----------|
| Configuração de formato ER | [Formato para conhecer elementos XML adiados.versão.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

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
    2. Selecione **Procurar**, encontre e selecione o arquivo **Formato para conhecer elementos XML adiados.1.1.xml** e selecione **OK**.

6. Na árvore de configuração, expanda **Modelo para conhecer elementos adiados**.
7. Revise a lista de configurações de ER importadas na árvore de configuração.

    ![Configurações de ER importadas na página Configurações](./media/ER-DeferredXml-Configurations.png)

### <a name="activate-a-configuration-provider"></a>Ativar um provedor de configuração

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Na página **Configurações de localização**, na seção **Provedores de configuração**, verifique se o [provedor de configuração](general-electronic-reporting.md#Provider) para a empresa de exemplo Litware, Inc. (`http://www.litware.com`) está listado e marcado como ativo. Se esse provedor de configuração não estiver listado, ou se ele não estiver marcado como ativo, siga as etapas no tópico [Criar um provedor de configuração e marcá-lo como ativo](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![A empresa de exemplo Litware, Inc. na página Configurações de localização](./media/ER-DeferredXml-ElectronicReportingWorkspace.png)

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

        ![Campo de agregação TotalSum na página Editar parâmetros 'GroupBy'](./media/ER-DeferredXml-GroupByParameters.png)

9. Revise como as fontes de dados configuradas são associadas ao modelo de dados e como elas expõem os dados acessados para torná-los disponíveis em um formato de ER:

    - A fonte de dados **Filtrados** é associada ao campo **Data.List** do modelo de dados.
    - O campo **\$TaxAmount** da fonte de dados **Filtrados** é associado ao campo **Data.List.Value** do modelo de dados.
    - O campo **TotalSum** da fonte de dados **Agrupados** é associado ao campo **Data.Summary.Total** do modelo de dados.

    ![Página do designer de mapeamento de modelo](./media/ER-DeferredXml-ModelMapping.png)

10. Feche as páginas **Designer de mapeamento de modelo** e **Mapeamentos de modelo**.

### <a name="review-the-imported-format"></a>Examine o formato importado

1. Na página **Configurações**, na árvore de configuração, selecione a configuração **Formato para conhecer elementos XML adiados**.
2. Selecione **Designer** para revisar os detalhes do formato.
3. Selecione **Mostrar detalhes**.
4. Examine as configurações dos componentes de formato de ER que estão configurados para gerar um documento de saída no formato XML que inclui detalhes das transações de imposto:

    - O elemento XML **Relatório\\Mensagem** é configurado para preencher o documento de saída com um único nó que inclui os elementos XML aninhados (**Cabeçalho**, **Registro** e **Resumo**).
    - O elemento XML **Relatório\\Mensagem\\Cabeçalho** é configurado para preencher o documento de saída com um único nó de cabeçalho que mostra a data e a hora do início do processamento.
    - O elemento XML **Relatório \\Mensagem\\Registro** é configurado para preencher o documento de saída com um único nó de registro que mostra os detalhes de uma única transação de imposto.
    - O elemento XML **Relatório\\Mensagem\\Resumo** é configurado para preencher o documento de saída com um único nó de resumo que inclui a soma dos valores de imposto das transações de imposto processadas.

    ![Elemento XML da mensagem e elementos XML aninhados na página Designer de formato](./media/ER-DeferredXml-Format.png)

5. Na guia **Mapeamento**, revise os seguintes detalhes:

    - O elemento **Relatório\\Mensagem\\Cabeçalho** não precisa estar associado a uma fonte para gerar um único nó em um documento de saída.
    - O atributo **ExecutionDateTime** gera a data e a hora (incluindo milissegundos) quando o nó de cabeçalho é adicionado.
    - O elemento **Relatório\\Mensagem\\Registro** é associado à lista **model.Data.List** de modo a gerar um único nó de registro para cada registro a partir da lista associada.
    - O atributo **TaxAmount** é associado a **model.Data.List.Value** (que é mostrado como **\@.Value** na exibição de caminho relativo) para gerar o valor de imposto da transação de imposto atual.
    - O atributo **RunningTotal** é um espaço reservado para o total acumulado dos valores de imposto. No momento, esse atributo não tem saída, pois nem uma associação nem um valor padrão é configurado para ele.
    - O atributo **ExecutionDateTime** gera a data e a hora (incluindo milissegundos) quando a transação atual é processada nesse relatório.
    - O elemento **Relatório\\Mensagem\\Resumo** não precisa estar associado a uma fonte de dados para gerar um único nó em um documento de saída.
    - O atributo **TotalTaxAmount** é associado a **model.Data.Summary.Total** para gerar a soma dos valores de imposto das transações de imposto processadas.
    - O atributo **ExecutionDateTime** gera a data e a hora (incluindo milissegundos) quando o nó de resumo é adicionado.

    ![Guia Mapeamento na página Designer de formato](./media/ER-DeferredXml-Format2.png)

### <a name="run-the-imported-format"></a>Executar o formato importado

1. Na página **Designer de formato**, selecione **Executar**.
2. Baixe o arquivo oferecido pelo navegador da Web e abra-o para revisão.

    ![Arquivo baixado](./media/ER-DeferredXml-Run.png)

Observe que o nó de resumo apresenta a soma dos valores de imposto para as transações processadas. Como o formato está configurado para usar a associação **model.Data.Summary.Total** de modo a retornar essa soma, a soma é calculada chamado a agregação **TotalSum** da fonte de dados **Agrupados** do tipo *GroupBy* no mapeamento de modelo. Para calcular essa agregação, o mapeamento de modelo itera em todas as transações que foram selecionadas na fonte de dados **Filtrados**. Ao comparar os tempos de execução do nó de resumo e do último nó de registro, você pode determinar que o cálculo da soma levou 12 milissegundos (ms). Ao comparar os tempos de execução do primeiro e do último nó de registro, você pode determinar que a geração de todos os nós de registro levou 9 ms. Portanto, foi necessário um total de 21 ms.

### <a name="modify-the-format-so-that-the-calculation-is-based-on-generated-output"></a>Modificar o formato para que o cálculo seja baseado na saída gerada

Se o volume de transação for muito maior do que o volume no exemplo atual, o tempo de cálculo poderá aumentar e causar problemas de desempenho. Ao alterar a configuração do formato, você pode ajudar a evitar esses problemas de desempenho. Como você acessa valores de impostos para incluí-los no relatório gerado, é possível reutilizar essas informações para calcular os valores de imposto. Para obter mais informações, consulte [Configurar o formato para contagem e soma](./tasks/er-format-counting-summing-1.md).

1. Na página **Designer de formato**, na guia **Formatar**, selecione o elemento de arquivo **Relatório** na árvore de formatos.
2. Defina a opção **Coletar detalhes de saída** como **Sim**. Agora você pode configurar esse formato usando o conteúdo de um relatório gerado como uma fonte de dados que pode ser acessada usando as funções internas de ER na categoria [Coleta de dados](er-functions-category-data-collection.md).
3. Na guia **Mapeamento**, selecione o elemento **Relatório\\Mensagem\\Registro**.
4. Configure a expressão **Nome da chave de dados coletada** como `WsColumn`.
5. Configure a expressão **Valor da chave de dados coletada** como `WsRow`.

    ![Elemento XML de registro na página Designer de formato](./media/ER-DeferredXml-Format3.png)

6. Selecione o atributo **Relatório\\Mensagem\\Registro\\TaxAmount**.
7. Configure a expressão **Nome da chave de dados coletada** como `SummingAmountKey`.

    ![Atributo TaxAmount na página Designer de formato](./media/ER-DeferredXml-Format4.png)

    Você pode considerar essa configuração o preenchimento de uma planilha virtual, em que o valor da célula A1 é acrescentado ao valor do imposto de cada transação de imposto processada.

8. Selecione o atributo **Relatório\\Mensagem\\Registro\\RunningTotal** e, em seguida, **Editar fórmula**.
9. Configure a expressão `SUMIF(SummingAmountKey, WsColumn, WsRow)` usando a função interna de ER [SUMIF](er-functions-datacollection-sumif.md) e selecione **Salvar**.

    ![Expressão SUMIF](./media/ER-DeferredXml-FormulaDesigner.png)

10. Feche a página **Designer de fórmulas**.
11. Selecione **Salvar** e **Executar**.
12. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado](./media/ER-DeferredXml-Run1.png)

    O último nó de registro contém o total acumulado de valores de imposto que é calculado para todas as transações processadas usando a saída gerada como uma fonte de dados. Essa fonte de dados é iniciada desde o começo do relatório e continua até a última transação de imposto. O nó de resumo contém a soma dos valores de imposto para todas as transações processadas que são calculadas no mapeamento de modelo usando a fonte de dados do tipo *GroupBy*. Observe que esses valores são iguais. Portanto, a soma baseada na saída pode ser usada no lugar de **GroupBy**. Ao comparar os tempos de execução do primeiro nó de registro e o nó de resumo, você pode determinar que a geração de todos os nós de registro e a soma levaram 11 ms. Portanto, no que diz respeito à geração de nós de registro e à soma dos valores de imposto, o formato modificado é aproximadamente duas vezes mais rápido do que o formato original.

13. Selecione o atributo **Relatório\\Mensagem\\Resumo\\TotalTaxAmount** e, em seguida, **Editar fórmula**.
14. Insira a expressão `SUMIF(SummingAmountKey, WsColumn, WsRow)` no lugar da expressão existente.
15. Selecione **Salvar** e **Executar**.
16. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado](./media/ER-DeferredXml-Run2.png)

    Observe que o total acumulado dos valores de imposto no último nó de registro agora é igual à soma no nó de resumo.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Colocar valores da soma baseada na saída no cabeçalho do relatório

Se você tiver que apresentar a soma dos valores de imposto no cabeçalho do relatório, por exemplo, é possível modificar o formato.

1. Na página **Designer de formato**, na guia **Formatar**, selecione o elemento XML **Relatório\\Mensagem\\Resumo**.
2. Selecione **Mover para cima**.
3. Selecione **Salvar** e **Executar**.
4. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado](./media/ER-DeferredXml-Run3.png)

    Observe que a soma dos valores de imposto no nó de resumo agora é igual a 0 (zero), pois a soma agora é calculada com base na saída gerada. Quando o primeiro nó de registro é gerado, a saída gerada ainda não contém nós de registro com detalhes da transação. É possível configurar esse formato para adiar a execução do elemento **Relatório\\Mensagem\\Resumo** até que o elemento **Relatório\\Mensagem\\Registro** tenha sido executado para todas as transações de imposto.

### <a name="defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used"></a>Adiar a execução do elemento XML de resumo para que o total calculado seja usado

1. Na página **Designer de formato**, na guia **Formatar**, selecione o elemento XML **Relatório\\Mensagem\\Resumo**.
2. Defina a opção **Execução adiada** como **Sim**.

    ![Opção Execução adiada do elemento XML Resumo na página Designer de formato](./media/ER-DeferredXml-Format5.png)

3. Selecione **Salvar** e **Executar**.
4. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado](./media/ER-DeferredXml-Run4.png)

    O elemento **Relatório\\Mensagem\\Resumo** agora é executado somente depois que todos os outros itens que estão aninhados sob seu elemento pai, **Relatório\\Mensagem**, tiverem sido executados. Portanto, ele é executado depois que o elemento **Relatório\\Mensagem\\Registro** tiver sido executado para todas as transações de imposto da fonte de dados **model.Data.List**. Os tempos de execução do primeiro e do último nó de registro, e dos nós de cabeçalho e resumo, revelam esse fato.

## <a name="additional-resources"></a>Recursos adicionais

- [Configurar o formato para contagem e soma](./tasks/er-format-counting-summing-1.md)
- [Rastrear a execução do formato ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md)
- [Adiar a execução de elementos de sequência nos formatos de ER](er-defer-sequence-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]