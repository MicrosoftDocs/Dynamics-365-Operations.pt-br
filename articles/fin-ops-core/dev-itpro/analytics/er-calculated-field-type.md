---
title: Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado
description: Este artigo fornece informações sobre como usar o tipo Campo calculado de fontes de dados de ER.
author: NickSelin
ms.date: 01/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4a4933c429982d1371c7c9a9412789ae08e08f43
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8934695"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a>Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado

[!include [banner](../includes/banner.md)]

Este artigo explica como você pode criar uma fonte de dados relatório eletrônico (ER) usando o tipo **Campo calculado**. Essa fonte de dados pode conter uma expressão de ER que, quando executada, pode ser controlada pelos valores de argumentos do parâmetro configurados em uma associação que chama essa fonte de dados. Ao configurar chamadas parametrizadas dessa fonte de dados, você pode reutilizar uma única fonte de dados em muitas associações, o que reduz o número total de fontes de dados que devem ser configuradas em mapeamentos de modelos de ER ou em formatos de ER. Isso também simplifica o componente de ER configurado, o que reduz os custos de manutenção e os custos de utilização por outros consumidores.

## <a name="prerequisites"></a>Pré-requisitos
Para concluir os exemplos neste artigo, você deve ter o seguinte acesso:

- Acesso a uma destas funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

- Acesso ao Regulatory Configuration Services (RCS) que foi provisionado para o mesmo locatário como Finance and Operations para uma das seguintes funções:

    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

Você também deve baixar e armazenar localmente os arquivos a seguir.

| **Conteúdo**                           | **Nome do arquivo**                                        |
|---------------------------------------|------------------------------------------------------|
| Configuração do modelo de dados de ER de exemplo    | [Modelo para conhecer chamadas parametrizadas.versão.1.xml](https://download.microsoft.com/download/e/5/c/e5c0d3f9-1818-47c7-ae75-46efcbb1314f/Modeltolearnparameterizedcallsversion.1.xml)     |
| Configuração de metadados de ER de exemplo      | [Metadados para conhecer chamadas parametrizadas.versão.1.xml](https://download.microsoft.com/download/8/3/a/83a910a5-bf65-4509-bec4-6737a81ecc45/Metadatatolearnparameterizedcalls.version.1.xml)  |
| Configuração do mapeamento do modelo de ER de exemplo | [Mapeamento para conhecer chamadas parametrizadas.versão.1.1.xml](https://download.microsoft.com/download/b/f/d/bfd8cbd8-0370-44d1-a1b1-66d021c580ca/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Configuração de formato de ER de exemplo        | [Formato para conhecer chamadas parametrizadas.versão.1.1.xml](https://download.microsoft.com/download/8/1/d/81deb6d8-a768-4fcf-bbbe-8f84d2dac3eb/Formattolearnparameterizedcalls.version.1.1.xml)  |

## <a name="sign-in-to-your-rcs-instance"></a>Entrar em sua instância do RCS
Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Primeiro, no RCS, você deve concluir as etapas do procedimento [Criar provedores configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md):

1. No painel padrão, selecione **Relatório eletrônico**.
2. Selecione **Configurações de relatórios**.
3. Importe as configurações baixadas para o RCS nesta sequência: modelo de dados, metadados, mapeamento do modelo, formato. Execute as seguintes etapas para cada configuração de ER:

    1. Selecione **Troca**.
    2. Selecione **Carregar do arquivo XML**.
    3. Selecione **Procurar** e selecione a configuração de ER necessária em formato XML.
    4. Selecione **OK**.

## <a name="review-the-provided-er-solution"></a>Revisar a solução de ER fornecida

### <a name="review-model-mapping"></a>Revisar o mapeamento de modelos

1. Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.
2. Selecione **Mapeamento para conhecer chamadas parametrizadas**.
3. Selecione **Designer**.
4. Selecione **Designer**.  
   
    Esse mapeamento de modelos de ER foi criado para fazer o seguinte:

    - Obtenha a lista de códigos de imposto (fonte de dados **Imposto**) na tabela **TaxTable**.
    - Obtenha a lista de transações de imposto (fonte de dados **Trans**) na tabela **TaxTrans**:
    
        - Agrupar a lista de transações obtidas (fonte de dados **Gr**) por código de imposto.
        - Calcular transações agrupadas seguindo os valores agregados de acordo com o código de imposto:

            - Soma dos valores de base do imposto.
            - Soma dos valores do imposto.
            - Valor mínimo da taxas de impostos aplicada.

    O mapeamento de modelos nesta configuração implementa o modelo de dados de base para qualquer dos formatos de ER criados para esse modelo e executados no Finance and Operations. Consequentemente, o conteúdo das fontes de dados **Imposto** e **Gr** é exposto para formatos de ER, como fontes de dados abstratos.

    ![Página do Designer de mapeamento de modelos mostrando as fontes de dados Imposto e Gr.](media/er-calculated-field-type-01.png)

5.  Feche a página **Designer de mapeamento de modelo**.
6.  Feche a página **Mapeamento de modelos**.

### <a name="review-format"></a>Revisar o formato

1. Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.
2. Selecione **Formato para conhecer chamadas parametrizadas**.
3. Selecione **Designer**. Esse formato de ER foi criado para fazer o seguinte:

    - Gerar um demonstrativo de imposto em formato XML.
    - Apresentar os seguintes níveis de tributação no demonstrativo de imposto: normal, reduzido e nenhum.
    - Apresentar vários detalhes em cada nível de tributação, com um número de detalhes diferente em cada nível.

    ![Página do designer de formatos.](media/er-calculated-field-type-02.png)

4. Selecione **Mapeamento**.
5. Expanda os itens **Modelo**, **Dados** e **Resumo**. 

    O campo calculado **Model.Data.Summary.Level** contém a expressão que retorna o código do nível de tributação (**Normal**, **Reduzido**, **Nenhum** ou **Outro**) como um valor de texto para qualquer código de imposto que possa ser recuperado da fonte de dados **Model.Data.Summary** em tempo de execução.

    ![Página do designer de formatos mostrando detalhes do modelo de dados Modelo para conhecer chamadas parametrizadas.](media/er-calculated-field-type-03.png)

6. Expanda o item **Model**.**Data2**.
7. Expanda o item **Model**.**Data2.Summary2**.
   
    A fonte de dados **Model**.**Data2.Summary2** é configurada para agrupar os detalhes de transações da fonte de dados **Model.Data.Summary** por nível de tributação (retornado pelo campo calculado **Model.Data.Summary.Level**) e calcular as agregações.

    ![Página do designer de formatos mostrando detalhes da fonte de dados Model.Data2.Summary2.](media/er-calculated-field-type-04.png)

8. Examine os campos calculados **Model**.**Data2.Level1**, **Model**.**Data2.Level2** e **Model**.**Data2.Level3**. Esses campos calculados são usados para filtrar a lista de registros **Model**.**Data2.Summary2** e retornar apenas os registros que representam um nível de tributação específico.
9. Feche a página **Designer de formato**.

## <a name="create-a-derived-format"></a>Criar um formato derivado
Você pode aperfeiçoar o formato fornecido adicionando um campo calculado para filtrar o nível de tributação necessário em vez de usar os três campos existentes: **Model**.**Data2.Level1**, **Model**.**Data2.Level2** e **Model**.**Data2.Level3**. O nível de tributação necessário pode ser especificado no local em que esse novo campo calculado será chamado.

1. Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.
2. Selecione **Formato para conhecer chamadas parametrizadas**.
3. Selecione **Criar configuração**.
4. Selecione **Derivar do Nome: Formato para conhecer chamadas parametrizadas, Microsoft**.
5. No campo **Nome**, insira **Formato para conhecer chamadas parametrizadas (personalizado)**.
6. Selecione **Criar configuração**.

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a>Configurar um campo calculado parametrizado que retorna uma lista de registros

### <a name="start-adding-a-new-calculated-field"></a>Começar a adicionar um novo campo calculado

1. Selecione **Designer**.
2. Selecione **Expandir/recolher** para expandir todos os itens de formato.
3. Selecione **Mapeamento**.
4. Expanda o item **Modelo**.
5. Selecione o item **Model.Data2**.
6. Selecione **Adicionar**.
7. Selecione **Funções\\Campo calculado**.
8. No campo **Nome**, insira **Níveis**.
9. Selecione **Editar fórmula**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definir um parâmetro para adicionar um campo calculado

1. Selecione **Parâmetros**.
2. Selecione **Novo**.
3. No campo **Nome**, insira **Nível de Tributação**.
4. No campo **Tipo**, selecione **Cadeia de caracteres**.

    Somente os tipos de dados primitivos podem ser usados para especificar o tipo de argumento do parâmetro. Portanto, não é possível usar os tipos **Lista de registros**, **Registro** e **Enumeração** com essa finalidade.

    O número máximo de parâmetros que podem ser especificados para um único campo calculado é 8.

    ![Lista de fontes de dados do parâmetro.](media/er-calculated-field-type-05.png)

5. Selecione **OK**.

Ao adicionar esse parâmetro, você especifica a condição que deve estar em vigor para chamar esse campo calculado. Quando você chama esse campo calculado, precisa especificar o argumento do parâmetro **Nível de Tributação** como um valor com o formato **Cadeia de caracteres**.

   Verifique se você definiu parâmetros apenas para os campos calculados que residem em um contêiner (**Lista de registros**, **Registro** ou **Contêiner**).

   O parâmetro configurado está disponível na lista de fontes de dados do campo calculado. Você pode adicionar o parâmetro à expressão configurada selecionando **Adicionar fonte de dados**.

   ![Campos da fonte de dados.](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definir uma expressão para adicionar um campo calculado

1. No campo **Fórmula**, insira: 

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level =**
    
2. Selecione o parâmetro **Nível de Tributação** na lista de fontes de dados.
3. Selecione **Adicionar fonte de dados**.
4. No campo **Fórmula**, finalize a expressão como:  

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Nível de Tributação')**

5. Selecione **Salvar**.

    ![Informações do campo da fonte de dados.](media/er-calculated-field-type-07.png)

6. Feche a página **Designer de fórmulas**.

### <a name="finish-adding-a-new-calculated-field"></a>Concluir a adição de um novo campo calculado

- Selecione **OK**.

Na página **Designer de formato**, o campo calculado parametrizado configurado **Níveis** exige um argumento **Cadeia de caracteres**.

![Lista expandida de níveis do campo calculado.](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a>Usar o campo calculado configurado para associar elementos de formato

1. Selecione **Model.Data2.Levels** para selecionar o campo calculado configurado.
2. Selecione o elemento de formato **Statement.Taxation.Regular**.
3. Selecione **Associar**.
4. Selecione **Sim** para confirmar a substituição da fonte de dados usada atualmente, **Level1**, pela nova fonte de dados, **Níveis**, em todos os elementos de formato aninhados do elemento de formato selecionado.

    A associação aplicada foi criada como uma chamada do campo calculado parametrizado. Por padrão, o nome do elemento de formato associado é usado como argumento para o campo calculado parametrizado nas seguintes condições:

      - O campo calculado é configurado para usar um único parâmetro.
      - O tipo de dados deste parâmetro é definido como **Cadeia de caracteres**.

    Quando o nome do elemento de formato associado estiver em branco, o nome da fonte de dados do elemento será usada na associação aplicada.

5. Selecione o elemento de formato **Statement.Taxation.Reduced**.
6. Selecione **Associar**.
7. Selecione **Sim** para confirmar a substituição da fonte de dados usada atualmente, **Level2**, pela nova fonte de dados, **Níveis**, em todos os elementos de formato aninhados sob o elemento de formato selecionado.
8. Selecione o elemento de formato **Statement.Taxation.None**.
9. Selecione **Associar**.
10. Selecione **Sim** para confirmar a substituição da fonte de dados usada atualmente, **Level3**, pela nova fonte de dados, **Níveis**, em todos os elementos de formato aninhados sob o elemento de formato selecionado.

   Quando você especificar o argumento do campo calculado parametrizado do elemento XML que representa o nível de tributação (por exemplo, **Model.Data2.Levels("Reduzido")** como um valor de texto), não será necessário fazer o mesmo para atributos XML aninhados; suas associações herdarão automaticamente o valor do argumento definido no nível pai (**Model.Data2.Levels.aggregated.Base**, não **Model.Data2.Levels("Reduzido").aggregated.Base**).

Não há suporte para chamadas recorrentes de qualquer campo calculado parametrizado.

Você pode selecionar **Editar fórmula** e alterar o argumento aplicado por padrão do campo calculado parametrizado na associação selecionada. Se esse argumento estiver ausente, poderão ocorrer erros em tempo de execução. Os usuários serão informados sobre essa situação quando o formato atual for validado.

![Notificação de aviso de validação.](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a>Configurar um campo calculado parametrizado para retornar um registro
Quando um campo calculado parametrizado retorna um registro, você precisa dar suporte à associação de campos individuais desse registro para elementos de formato. Nesses casos, não haverá nenhuma associação pai que contém o valor de um argumento para chamar um campo calculado parametrizado. Esse valor deve ser definido na associação do campo de um único registro.

### <a name="start-adding-a-new-calculated-field"></a>Começar a adicionar um novo campo calculado

1. Selecione o item **Model.Data2**.
2. Selecione **Adicionar**.
3. Selecione **Funções\\Campo calculado**.
4. No campo **Nome**, insira **LevelRecord**.
5. Selecione **Editar fórmula**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definir um parâmetro para adicionar um campo calculado

1. Selecione **Parâmetros**.
2. Selecione **Novo**.
3. No campo **Nome**, insira **Nível de Tributação**.
4. No campo **Tipo**, selecione **Cadeia de caracteres**.
5. Selecione **OK**.

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definir uma expressão para adicionar um campo calculado

1. No campo **Fórmula**, insira o seguinte:  
    
    **FIRSTORNULL(\@.Levels(**

2. Selecione o parâmetro **Nível de Tributação**.
3. Selecione **Adicionar fonte de dados**.
4. No campo **Fórmula**, acrescente **'Nível de Tributação'))** ao que você inseriu na Etapa 1 para finalizar a expressão como:  
    
    **FIRSTORNULL(\@.Levels('Nível de Tributação'))**

5. Selecione **Salvar**.
6. Feche a página **Designer de fórmulas**.

### <a name="finish-adding-a-new-calculated-field"></a>Concluir a adição de um novo campo calculado

-   Selecione **OK**.

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a>Usar o campo calculado configurado para associar elementos de formato

1. Expanda **Model.Data2.LevelRecord** para selecionar o campo calculado configurado.
2. Expanda o contêiner **Model.Data2.LevelRecord.aggregated** do campo calculado configurado.
3. Selecione o campo **Model.Data2.LevelRecord.aggregated.Base**.
4. Selecione o elemento de formato **Statement.Taxation.None**.
5. Selecione **Desassociar**.
6. Selecione o elemento de formato **Statement.Taxation.None.Base**.
7. Selecione **Associar**.
8. Selecione **Editar fórmula**.
9. Altere a expressão para **Model.Data2.LevelRecord("Nenhum").aggregated.Base**.

![Expressão atualizada.](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a>Remover campos calculados que não são usados

1. Selecione **Model.Data2.Level1**.
2. Selecione **Excluir**.
3. Selecione **Model.Data2.Level2**.
4. Selecione **Excluir**.
5. Selecione **Model.Data2.Level3**.
6. Selecione **Excluir**.
7. Selecione **Salvar**.

  > [!NOTE]
  > Você reutilizou o mesmo campo calculado **Model.Data2.Levels** várias vezes em associações de formato. É muito mais fácil usar e manter um único campo calculado em vez de fazer isso para vários campos semelhantes.

8. Feche a página **Designer de formato**.

## <a name="complete-adjusted-version-of-a-derived-format"></a>Concluir a versão ajustada de um formato de derivado

1. Na Guia Rápida **Versões**, selecione **Alterar status**.
2. Selecione **Concluir**.

## <a name="export-completed-version-of-a-derived-format"></a>Exportar a versão concluída de um formato de derivado

1. Selecione o formato **Formato para conhecer chamadas parametrizadas (personalizado)** na árvore de configurações.
2. Na Guia Rápida **Versões**, selecione a versão 1.1.1 concluída.
3. Selecione **Taxa de câmbio**.
4. Selecione **Exportar como arquivo XML**.
5. Armazene a configuração baixada localmente no formato XML.

## <a name="test-er-formats"></a>Testar formatos de ER 
Você pode executar os formatos de ER inicial e aprimorados para garantir que os campos calculados parametrizados funcionam corretamente.

### <a name="import-er-configurations"></a>Importar configurações de ER
Você pode importar configurações revisadas do RCS usando o repositório de ER do tipo **RCS**. Se você já passou pelas etapas do artigo [Importar configurações de ER (Relatórios eletrônicos) do RCS (Regulatory Configuration Services)](rcs-download-configurations.md), use o repositório de ER configurado para importar as configurações discutidas anteriormente neste artigo para o seu ambiente. Caso contrário, siga estas etapas:

1. Selecione a empresa **DEMF** e, no painel padrão, selecione **Relatório eletrônico**.
2. Selecione **Configurações de relatórios**.
3. Importe as configurações do Centro de Download da Microsoft nesta sequência: modelo de dados, mapeamento do modelo, formato. Execute as seguintes etapas para cada configuração de ER:

    1. Selecione **Troca**.
    2. Selecione **Carregar do arquivo XML**.
    3. Selecione **Procurar** para selecionar a configuração de ER necessária em formato XML.
    4. Selecione **OK**.

4. Importe a exportação do RCS versão 1.1.1 concluída do formato **Formato para conhecer chamadas parametrizadas (personalizado)**:

    1. Selecione **Troca**.
    2. Selecione **Carregar do arquivo XML**.
    3. Selecione **Procurar** para selecionar o arquivo **Formato para conhecer chamadas parametrizadas (personalizado)** armazenado localmente em formato XML.
    4. Selecione **OK**.

### <a name="run-er-formats"></a>Executar formatos de ER

1. Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.
2. Selecione **Formato para conhecer chamadas parametrizadas**.
3. Selecione **Executar** na faixa de opções mais superior.
4. Salve a saída gerada localmente.
5. Selecione o item **Formato para conhecer chamadas parametrizadas (personalizado)**.
6. Selecione **Executar** na faixa de opções mais superior.
7. Salve a saída gerada localmente. 
8. Compare o conteúdo das saídas geradas.

## <a name="additional-resources"></a>Recursos adicionais

- [Designer de fórmulas no relatório eletrônico (ER)](general-electronic-reporting-formula-designer.md)
- [Melhorar o desempenho das soluções ER adicionando fontes de dados de CAMPOS CALCULADOS parametrizados](er-calculated-field-ds-performance.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
