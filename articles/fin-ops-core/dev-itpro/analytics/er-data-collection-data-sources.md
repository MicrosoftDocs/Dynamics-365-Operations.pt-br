---
title: Usar fontes de dados de COLETA DE DADOS em formatos de relatório eletrônico
description: Este artigo explica como você pode usar fontes de dados de COLETA DE DADOS nos formatos do Relatório eletrônico (ER).
author: kfend
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.16
ms.custom: 58771
ms.assetid: ''
ms.search.form: EROperationDesigner
ms.openlocfilehash: 221cefc1880cdd88a952140424daf24975a575aa
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286169"
---
# <a name="use-data-collection-data-sources-in-electronic-reporting-formats"></a>Usar fontes de dados de COLETA DE DADOS em formatos de relatório eletrônico

[!include [banner](../includes/banner.md)]

Você pode usar o Designer de operações da estrutura do [Relatório Eletrônico (ER)](general-electronic-reporting.md) para configurar o componente de formato de uma solução de ER usada para gerar documentos de saída em diferentes formatos. A estrutura hierárquica do componente de formato configurado consiste em vários tipos de elementos de formato. Esses elementos de formato são usados para preencher documentos gerados com as informações necessárias no tempo de execução. Por padrão, quando você executa um formato de ER, os elementos de formato são executados na mesma ordem em que são apresentados na hierarquia de formato: um por um, de cima para baixo.

Quando o ER executa um elemento de formato que contém uma associação, a fórmula dessa associação é executada e o elemento de formato adiciona o valor a um documento gerado. Por exemplo, a associação pode passar o valor de um campo do modelo de dados para um elemento de formato. Você pode configurar uma fonte de dados de coleta de dados para coletar valores de campos de modelo de dados no tempo de execução, somar valor e preencher um documento gerado com os valores obtidos. Para usar essa abordagem, altere a associação inicial de forma que a fonte de dados configurada da coleta de dados seja usada para passar o valor de um campo de modelo de dados para um elemento de formato. Ao passar valores por meio da fonte de dados da coleta de dados, você pode coletar detalhes necessários para uso futuro.

Ao configurar uma fonte de dados de coleta de dados, especifique um tipo de valor que será gerenciado na fonte de dados. Os seguintes [tipos de dados](er-formula-supported-data-types-primitive.md) são atualmente aceitos para coletar valores:

- Booleano
- Data 
- Data e Hora
- Guid
- Int64
- Inteiro
- Real
- Sequência de caracteres
- Horário

Você pode usar o método `Collect(Value)` de uma fonte de dados de coleta de dados para passar um valor para uma fonte de dados para cobrança. Neste método, o argumento `Value` é uma constante ou o caminho válido de um campo de fonte de dados do tipo de dados relevante.

Use a propriedade `Result` de uma fonte de dados de coleta de dados para acessar a lista de valores coletados. Esta propriedade retorna uma [lista de registros](er-formula-supported-data-types-composite.md#record-list). Os registros da lista de registros contêm o campo `Value` que pode ser usado para acessar os valores coletados.

Por padrão, uma fonte de dados de coleta de dados coleta somente valores exclusivos.

Para coletar todos os valores, defina o campo **Coletar todos os valores** da fonte de dados de coleta de dados configurada como **Sim**. Quando o campo **Coletar todos os valores** estiver definido como **Sim**, a propriedade `Sum(Flag)` com parâmetros ficará disponível. Você pode usar esta propriedade para obter o valor total de todos os valores coletados no momento. Nessa propriedade, o argumento `Flag` é um [valor booliano](er-formula-supported-data-types-primitive.md#boolean) usado para indicar se o valor total deve ser redefinido.

- Quando o valor **Falso** é fornecido, a soma continua do valor coletado anteriormente.
- Quando o valor **Verdadeiro** é fornecido, uma nova soma é iniciada.

Os seguintes tipos de dados são atualmente aceitos para soma:

- Int64
- Inteiro
- Real

Para saber mais sobre este recurso, conclua o exemplo que segue.

## <a name="example-configure-an-er-format-to-do-counting-and-summing-by-using-a-data-collection-data-source"></a>Exemplo: configurar um formato de ER para contabilizar e somar usando uma fonte de dados de coleta de dados

Este exemplo mostra como um usuário na função de Administrador do sistema ou de Consultor funcional do relatório eletrônico pode configurar um formato de ER que tem uma fonte de dados de coleta de dados que é usada para calcular totais de execução e coletar valores somados.

Os procedimentos neste exemplo podem ser concluídos na empresa USMF no Microsoft Dynamics 365 Finance.

### <a name="upload-and-use-the-provided-er-solution"></a>Carregar e usar a solução de ER fornecida

1. [Importar o exemplo de configurações de ER](er-defer-sequence-element.md#import-the-sample-er-configurations).
2. [Ativar um provedor de configuração](er-defer-sequence-element.md#activate-a-configurations-provider).
3. [Revise o mapeamento do modelo importado](er-defer-sequence-element.md#review-the-imported-model-mapping).
4. [Examinar o formato importado](er-defer-sequence-element.md#review-the-imported-format).
5. [Executar o formato importado](er-defer-sequence-element.md#run-the-imported-format).

### <a name="run-the-format-of-the-provided-er-solution"></a>Execute o formato da solução de ER fornecida

1. Na página **Designer de formato**, selecione **Executar**.
2. Na caixa de diálogo **Parâmetros de relatório eletrônico**, selecione **OK**.
3. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado que contém os resultados da execução de formato inicial](./media/er-data-collection-data-sources-01.png)

### <a name="modify-the-format-of-the-er-solution-to-calculate-the-running-tax-total"></a>Modificar o formato da solução de ER para calcular o total do imposto em execução

Se o volume de transações for muito maior do que o volume no exemplo atual, o tempo que a soma requer pode aumentar e causar problemas de desempenho. Ao alterar as configurações do formato, você pode ajudar a evitar esses problemas de desempenho. Como você acessa valores de impostos para incluí-los no relatório gerado, é possível reutilizar essas informações para somar os valores de imposto.

1. Na página **Designer de formato**, na guia **Mapeamento**, selecione **Adicionar raiz**.
2. Na caixa de diálogo **Adicionar fonte de dados**, selecione **Funções** \> **Coleta de dados**.
3. Na caixa de diálogo **Propriedades da fonte de dados da coleção de dados**, siga estas etapas:

    1. No campo **Nome**, digite **CollectedTaxValues**.
    2. No campo **Tipo de item**, selecione **Real**.
    3. No campo **Coletar todos os valores**, selecione **Sim**.
    4. Selecione **OK**.

4. Selecione o elemento de formato numérico **Relatório\\Linhas\\Registro\\ValorImposto**.

    > [!NOTE]
    > No momento, a associação `@.Value` está configurada para esse elemento. Portanto, um documento gerado se for preenchido com valores de imposto no campo `model.Data.List.Value`.

5. Selecione **Editar fórmula**.
6. Na página **Designer de fórmulas**, siga estas etapas:

    1. No campo **Fórmula**, substitua `@.Value` por `CollectedTaxValues.Collect(@.Value)`.
    2. Salve suas alterações e feche a página.

    > [!NOTE]
    > A nova associação passará os mesmos valores de imposto para um documento gerado. No entanto, esses valores também serão coletados na fonte de dados **CollectedTaxValues**.

7. Selecione o elemento de formato numérico **Relatórios\\Linhas\\Registro\\TotalExecução**.
8. Selecione **Editar fórmula**.
9. Na página **Designer de fórmulas**, siga estas etapas:

    1. No campo **Fórmula**, digite `CollectedTaxValues.Sum(false)`.
    2. Salve suas alterações e feche a página.

    > [!NOTE]
    > A nova associação passará para um documento gerado, o valor total dos valores de imposto que já foram inseridos.

    ![Elementos numéricos que têm associações atualizadas na página Designer de formato](./media/er-data-collection-data-sources-02.png)

10. Selecione **Salvar** e **Executar**.
11. Na caixa de diálogo **Parâmetros de relatório eletrônico**, selecione **OK**.
12. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado que contém os resultados da execução de formato modificado](./media/er-data-collection-data-sources-03.png)

### <a name="modify-the-format-to-evaluate-the-list-of-collected-tax-values"></a>Modificar o formato para avaliar a lista de valores de imposto coletados

1. Na página **Designer de formato**, na guia **Formato**, selecione o elemento de formato numérico **Relatório\\Linhas\\Registro\\TotalExecução** e depois siga estas etapas:

    1. No campo **Tipo numérico**, altere o valor de **Real** para **Inteiro**.
    2. No campo **Formato numérico**, altere o valor de **F2** para **F0**.

3. Na guia **Mapeamento**, selecione **Editar fórmula**.
4. Na página **Designer de fórmulas**, siga estas etapas:

    1. No campo **Fórmula**, digite `COUNT(CollectedTaxValues.Result)`.
    2. Salve suas alterações e feche a página.

    > [!NOTE]
    > A nova associação passará, para um documento gerado, o número de registros na lista em que os valores de imposto são coletados.

5. Selecione **Salvar** e **Executar**.
6. Na caixa de diálogo **Parâmetros de relatório eletrônico**, selecione **OK**.
7. Baixe e revise o arquivo oferecido pelo navegador da Web.

    ![Arquivo baixado que contém os resultados de outra execução de formato modificado](./media/er-data-collection-data-sources-04.png)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions"></a>Se eu precisar calcular os totais de execução e coletar dados, qual é a diferença entre usar uma fonte de dados de coleção de dados e usar as funções de coleta de dados internas?

Uma fonte de dados de coleta de dados e as funções de [coleta de dados](er-functions-category-data-collection.md) internas podem ser usadas para coleta de dados, soma e contagem, com base nas informações passadas para um documento de saída gerado. No entanto, ao tentar decidir qual técnica usar, você deve considerar os pontos a seguir.

| Fonte de dados | Funções internas |
|-------------| ------------------ |
| Somente os valores são coletados. | <p>Valores nomeados são coletados. Portanto, os totais podem ser calculados para grupos de valores separados.</p><p>Além disso, os grupos podem ser extraídos como uma lista.</p><p>Os valores de texto também podem ser obtidos.</p> |
| Os valores exclusivos são coletados automaticamente. | Configurações adicionais são necessárias para extrair uma lista de valores exclusivos dos valores coletados. |
| O desempenho depende do volume de valores coletados. | Na prática, o desempenho depende do volume de valores coletados. |
| Essa técnica funciona para todos os tipos de documentos de saída. | Esta técnica só funciona em documentos de texto e XML. |

## <a name="additional-resources"></a>Recursos adicionais

- [Configurar o formato para contagem e soma](./tasks/er-format-counting-summing-1.md)
- [Adiar a execução de elementos de sequência nos formatos ER](er-defer-sequence-element.md#Example)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
