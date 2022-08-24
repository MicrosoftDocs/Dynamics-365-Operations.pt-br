---
title: Suporte a chamadas parametrizadas de modelos de dados de ER
description: Este artigo explica como implementar chamadas parametrizadas de modelos de dados de Relatório Eletrônico (ER).
author: kfend
ms.date: 03/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.custom: ''
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula, ERDataModelDesigner
ms.openlocfilehash: 5be189c19d963991ec012de189bbf7b721b88fef
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275978"
---
# <a name="support-parameterized-calls-of-er-data-models"></a>Suporte a chamadas parametrizadas de modelos de dados de ER

[!include [banner](../includes/banner.md)]

Para gerar documentos comerciais, configure uma solução de [Relatório Eletrônico (ER)](general-electronic-reporting.md) que contenha os seguintes componentes de ER:

- **[Formato](er-overview-components.md#format-component)** – esse componente especifica a estrutura de um documento comercial.
- **Mapeamento de formato** – esse componente controla como um documento comercial é preenchido no tempo de execução.
- **[Mapeamento de modelo](er-overview-components.md#model-mapping-component)** – esse componente especifica o que os dados extraem do aplicativo para um mapeamento de formato.
- **[Modelo de dados](er-overview-components.md#data-model-component)** – esse componente passa informações entre componentes individuais.

Quando você executa um formato ER, todo elemento de formato é executado, iniciando pelo elemento de formato raiz. Sempre que um elemento de formato executado contiver uma associação a uma [fonte de dados](general-electronic-reporting.md#configuring-data-model-mappings-for-outgoing-documents), a fonte de dados será executada para entregar os dados esperados e usá-la para preencher o elemento de formato. Quando uma fonte de dados do tipo *Modelo* é chamada, o mapeamento de modelo apropriado é chamado para extrair dados do aplicativo, com base nas configurações do mapeamento de modelo.

Anteriormente, essas chamadas de mapeamento de modelo não podiam ser parametrizadas para torná-las dependentes da lógica do formato executado. Só havia suporte ao fluxo de dados a seguir.

<table>
<tbody>
<tr align="center">
<td>
<b>Formato</b><br>
Elemento de&nbsp;formato<br>
&nbsp;
</td>
<td>
<i>Associação</i><br>
&gt;&nbsp;solicitação&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;&lt;
</td>
<td><b>Mapeamento de&nbsp;formato</b><br>
Fonte de dados<br>
&nbsp;
</td>
<td>
<i>Modelo de&nbsp;dados</i><br>
&gt;&nbsp;solicitação&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;&lt;
</td>
<td>
<b>Mapeamento de&nbsp;modelo</b><br>
Fonte de&nbsp;dados<br>
&nbsp;
</td>
<td>
<i>Associação</i><br>
&gt;&nbsp;solicitação&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;&lt;
</td>
<td>
<b>Tabela</b><br>
Gravar<br>
Campo
</td>
</tr>
</tbody>
</table>

No entanto, na versão 10.0.15 e posteriores, você pode configurar campos de modelo de dados que podem ser chamados somente quando os valores dos parâmetros configurados são fornecidos. Quando esse campo é configurado e chamado a partir de um componente de formato, os parâmetros necessários devem ser fornecidos em uma associação de formato como argumentos da chamada. Nesses casos, os valores dos argumentos podem ser especificados com base em valores específicos do formato. Portanto, você pode usar a **parametrização dinâmica de tempo de execução** para que chamadas de modelo de dados ofereçam suporte ao fluxo de dados a seguir.

<table>
<tbody>
<tr align="center">
<td>
<b>Formato</b><br>
Elemento de&nbsp;formato&nbsp;1<br>
<br>
Elemento de&nbsp;formato&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Associação</i><br>
&gt;&nbsp;solicitação&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;solicitação&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Mapeamento de&nbsp;formato</b><br>
Fonte de&nbsp;dados&nbsp;1<br>
&nbsp;<br>
<b>valor2=Func(valor1)</b><br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Modelo de&nbsp;dados</i><br>
&gt;&nbsp;campo1&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;1&nbsp;&lt;<br>
<b>&gt;&nbsp;campo2(valor2)&nbsp;&gt;</b><br>
&lt;&nbsp;valor&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Mapeamento de&nbsp;modelo</b><br>
Fonte de&nbsp;dados&nbsp;1<br>
<br>
Fonte de&nbsp;dados&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Associação</i><br>
&gt;&nbsp;solicitação&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;solicitação&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Tabela&nbsp;1</b><br>
Registro&nbsp;1<br>
Campo&nbsp;1<br>
<b>Tabela&nbsp;2</b><br>
Registro&nbsp;2<br>
Campo&nbsp;2
</td>
</tr>
</tbody>
</table>

A nova funcionalidade permite que você parametrize a chamada para qualquer campo de modelo de dados do tipo [*Registro*](er-formula-supported-data-types-composite.md#record) ou [*Lista de registros*](er-formula-supported-data-types-composite.md#record-list). Há suporte aos tipos de dados a seguir para os parâmetros de um campo de modelo de dados:

- [Booliano](er-formula-supported-data-types-primitive.md#boolean)
- [Contêiner](er-formula-supported-data-types-composite.md#container)
- [Data ](er-formula-supported-data-types-primitive.md#date)
- [Data e Hora](er-formula-supported-data-types-primitive.md#datetime)
- [GUID](er-formula-supported-data-types-primitive.md#guid)
- [Int64](er-formula-supported-data-types-primitive.md#int64)
- [Inteiro](er-formula-supported-data-types-primitive.md#integer)
- [Real](er-formula-supported-data-types-primitive.md#real)
- [Sequência de caracteres](er-formula-supported-data-types-primitive.md#string)

Você pode especificar cada parâmetro de um campo de modelo de dados para o qual o argumento pode ser fornecido como um valor único do tipo de dados definido e a [*lista*](er-formula-supported-data-types-composite.md#record-list) desses valores.

> [!NOTE]
> Não há suporte ao valor padrão do parâmetro de um campo de modelo de dados. Se você adicionar um parâmetro a um campo em um modelo de dados e a versão do modelo de dados já tiver sido lançada e publicada, será necessário [trocar a base](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) de todos os mapeamentos e formatos de modelos correspondentes para a nova versão deste modelo, pois essa alteração de modelo de dados não é compatível com versões anteriores.

Você pode configurar campos parametrizados de modelo de dados para fazer chamadas de mapeamento de modelo com formato específico. Essa abordagem pode ajudar a reduzir o número de mapeamentos de modelo que devem ser configurados para vários formatos de um único modelo de dados. Você também pode usar essa abordagem para melhorar o desempenho de execução dos formatos e reduzir o tempo necessário para gerar documentos comerciais. Para saber mais sobre este recurso, conclua o exemplo neste artigo.

## <a name="example-use-parameterized-calls-of-er-data-models"></a>Exemplo: usar chamadas parametrizadas de modelos de dados de ER

As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou de Desenvolvedor de Relatório Eletrônico pode criar uma solução de ER que contenham um modelo de dados, um mapeamento de modelo e um componente de formato de ER que estejam configurados para chamar um mapeamento de modelo a partir de um formato, fornecendo um argumento para a chamada, o valor que foi calculado no tempo de execução usando a fórmula do formato em execução 

Essas etapas podem ser concluídas na empresa **DEMF**. Nenhuma modificação de código é necessária. 

Neste exemplo, você criará as [configurações](general-electronic-reporting.md#Configuration) do ER necessárias para a empresa **Litware, Inc.** de exemplo. Verifique se o provedor de configuração da empresa **Litware, Inc.** (`http://www.litware.com`) de exemplo está listado na estrutura de ER e marcado como **Ativo**. Se esse provedor de configuração não estiver listado, ou se ele não estiver marcado como **Ativo**, siga as etapas em [Criar um provedor de configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="business-scenario"></a>Cenário de negócios

Você tem uma solução de ER que inclui um formato que pode ser executado para gerar um documento eletrônico para fins de auditoria. Esse formato contém transações de imposto relacionadas a ordens de venda e ordens de compra, e que têm os detalhes necessários, como a data da transação e o valor do imposto. A partir do novo ano fiscal, a estrutura desse documento foi alterada. Agora você deve enviar um documento estendido que inclua detalhes adicionais (nomes) de todas as partes (clientes e fornecedores) cujas transações são apresentadas nos relatórios gerados. Portanto, você deve modificar sua solução de ER para que ela gere documentos que cumpram essa nova exigência.

### <a name="configure-the-er-framework"></a>Configurar a estrutura de ER

Siga as etapas em [Configurar a estrutura de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar o conjunto mínimo de parâmetros de ER. Você deve concluir essa configuração antes de começar a usar a estrutura de ER para criar uma nova solução ER.

### <a name="design-a-domain-specific-data-model"></a>Criar um modelo de dados de domínio específico

Você deve criar uma nova configuração de ER que contenha o componente de modelo de dados necessário. Esse modelo de dados será usado como uma fonte de dados posteriormente, quando você criar um formato de ER para gerar um relatório de auditoria.

Siga estas etapas para importar o modelo de dados necessário de um arquivo XML fornecido pela Microsoft.

1. Baixe o arquivo [Exemplo de modelo de auditoria.versão.1.xml](https://download.microsoft.com/download/7/1/9/719b0132-fed7-4c73-8afa-90cac29c2fee/Sample-audit-model.version.1.xml) e salve-o no computador local.
2. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
4. Na página **Configurações**, no Painel de Ações, selecione **Trocar** \> **Carregar de arquivo XML**.
5. Selecione **Procurar** e, depois, encontre e selecione o arquivo **Exemplo de modelo de auditoria.versão.1.xml**.
6. Selecione **OK** para importar a configuração.

    ![Configuração do modelo de dados de ER importado na página Configurações.](./media/er-data-model-parameterized-calls-imported-model.png)

A ilustração a seguir mostra a versão editável do modelo de dados configurado na página **Designer de modelo de dados**.

![Estrutura do modelo de dados ER na página Designer de modelo de dados.](./media/er-data-model-parameterized-calls-model1.png)

No momento, o modelo foi projetado para expor somente as transações de impostos que têm os detalhes necessários.

### <a name="design-a-model-mapping-for-the-configured-data-model"></a>Criar um mapeamento de modelo para o modelo de dados configurado

Como usuário na função de Desenvolvedor de Relatório Eletrônico, você deve criar uma nova configuração de ER que contenha um componente de mapeamento de modelo para o modelo de dados de Exemplo de auditoria. Este componente implementa o modelo de dados configurado para o Microsoft Dynamics 365 Finance e é específico desse aplicativo. Você deve configurar o componente de mapeamento de modelos para especificar os objetos de aplicativo que devem ser usados para preencher o modelo de dados configurado com os dados do aplicativo no tempo de execução. Para concluir essa tarefa, você deve compreender como a estrutura de dados do domínio comercial de imposto é implementada no Finance.

Siga estas etapas para importar o mapeamento de modelo necessário de um arquivo XML fornecido pela Microsoft.

1. Baixe o arquivo [Exemplo de mapeamento de modelo de auditoria.versão.1.1.xml](https://download.microsoft.com/download/c/0/3/c03a4673-b1b1-4ef8-96d0-bf96518be6e0/Sample-audit-model-mapping.version.1.1.xml) e salve-o no computador local.
2. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
4. Na página **Configurações**, no Painel de Ações, selecione **Trocar** \> **Carregar de arquivo XML**.
5. Selecione **Procurar** e, depois, encontre e selecione o arquivo **Exemplo de mapeamento de modelo de auditoria.versão.1.1.xml**.
6. Selecione **OK** para importar a configuração.

    ![Configuração do mapeamento de modelo ER importado na página Configurações.](./media/er-data-model-parameterized-calls-imported-mapping.png)

A ilustração a seguir mostra a versão editável do mapeamento de modelo configurado na página **Designer de mapeamento de modelo**.

![Estrutura de mapeamento de modelo de ER na página Designer de mapeamento de modelo.](./media/er-data-model-parameterized-calls-mapping1.png)

No momento, o mapeamento de modelo foi projetado para expor as transações de impostos que têm os detalhes necessários. Ele busca essas informações na tabela de aplicativos `TaxTrans` usando as fontes de dados de ER configuradas `TaxTrans` e `TaxTransFiltered`.

### <a name="design-a-new-format"></a>Projetar um novo formato

Como usuário na função de consultor funcional de relatório eletrônico, você deve criar uma nova configuração do ER contendo um componente de formato. Você deve configurar o componente de formato para preencher os relatórios gerados com transações de impostos que tenham todos os detalhes necessários.

Siga estas etapas para importar o formato exigido de um arquivo XML fornecido pela Microsoft.

1. Baixe o arquivo [Exemplo de formato de auditoria.versão.1.1.xml](https://download.microsoft.com/download/e/b/7/eb7e126e-2bb3-4bbb-a735-ffd4c48920b1/Sample-audit-format.version.1.1.xml) e salve-o no computador local.
2. Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
3. No espaço de trabalho **Relatório eletrônico**, selecione **Configurações de relatórios**.
4. Na página **Configurações**, no Painel de Ações, selecione **Trocar** \> **Carregar de arquivo XML**.
5. Selecione **Procurar** e, depois, encontre e selecione o arquivo **Exemplo de formato de auditoria.versão.1.1.xml**.
6. Selecione **OK** para importar a configuração.

    ![Configuração do formato de ER importado na página Configurações.](./media/er-data-model-parameterized-calls-imported-format.png)

A ilustração a seguir mostra a versão editável do formato configurado na página **Designer de formato**.

![Estrutura do formato de ER na página Designer de formato.](./media/er-data-model-parameterized-calls-format1.png)

O formato de ER é configurado para gerar um relatório como um arquivo de texto no formato CSV (valores separados por vírgula).

### <a name="run-the-imported-format"></a>Executar o formato importado

1. Na página **Configurações**, selecione a configuração de **Exemplo de formato de auditoria** e, no Painel de Ações, selecione **Executar**.
2. Na caixa de diálogo **Parâmetros do relatório eletrônico**, na guia **Registros a serem incluídos**, selecione **Filtro**.
3. Especifique as condições para selecionar as transações de imposto dos comprovantes **PIV-110000004** e **INV-10000001**.
4. Selecione **OK**.
5. Selecione **OK**.
6. Revise o documento gerado que contém as transações de imposto dos comprovantes selecionados.

    ![Visualização do documento gerado com transações de imposto.](./media/er-data-model-parameterized-calls-output1.png)

### <a name="adjust-the-imported-er-solution"></a>Ajustar a solução de ER importada

De acordo com o novo requisito, o documento que deve ser enviado deve conter os nomes de clientes e fornecedores cujas transações estão incluídas. Portanto, você deve modificar a solução de ER importada para que ela gere um documento que cumpra essa nova exigência.

Decida como você deseja implementar as modificações necessárias dos componentes de ER importados.

A abordagem óbvia é implementar as seguintes modificações:

- Em seu modelo de dados, adicione o novo campo modelo de dados `Transaction.Party.Name` do tipo *Cadeia de caracteres*.
- No mapeamento do seu modelo, configure a associação com o novo campo de modelo de dados usando relações de tabela disponíveis para acessar o registro relevante da tabela de aplicativos `DirPartyTable` e obtenha o valor do campo `Name` que está nela.

Embora essa abordagem funcione, ela pode causar problemas de desempenho no banco de dados SQL, porque `TaxTrans` é a tabela de transações e, portanto, pode conter um grande volume de registros. Nesse caso, o número de chamadas para `DirPartyTable` deve ser igual ao número de registros na tabela `TaxTrans`, que podem causar problemas de desempenho.

Alternativamente, você pode implementar as seguintes modificações:

- No modelo de dados, adicione a nova raiz `Party` e o novo campo `Party.Name`.
- No mapeamento do seu modelo, adicione uma nova fonte de dados que associará todos os registros de tabelas usados em relações de tabela para acessar o registro relevante da tabela de aplicativos `DirPartyTable`, a partir da tabela `TaxTrans`.

Embora essa abordagem funcione, ela pode causar alguns problemas de consumo de memória. Mesmo quando uma nova fonte de dados [JOIN](er-join-data-sources.md) é executada como uma única solicitação SQL ao banco de dados do aplicativo para evitar problemas de desempenho do banco de dados, o resultado deve ser obtido para a memória do servidor de aplicativos. Como o número de registros e o número de campos nesses registros serão bem grandes, essa abordagem poderá causar um consumo de memória muito intenso. Uma exceção de tempo de execução de memória insuficiente poderá até ser lançada.

Você pode implementar as modificações quando um formato em execução coletar, na memória, os códigos de identificação exclusivos de clientes e fornecedores para todas as transações de impostos que serão apresentadas em um relatório gerado. Como somente os códigos exclusivos devem ser mantidos, o conjunto final de códigos não será grande o suficiente para afetar o consumo de memória. O conjunto de códigos será então passado ao mapeamento do modelo como o argumento de outra chamada da fonte de dados do tipo *Modelo*. Com base nessa chamada, o mapeamento de modelo executará uma nova fonte de dados ER que faz uma única solicitação SQL ao banco de dado do aplicativo para obter, a partir da tabela `DirPartyTable`, registros somente para as partes cujos códigos estejam presentes no conjunto de códigos fornecido.

### <a name="adjust-the-imported-data-model"></a>Ajustar o modelo de dados importados

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configurações no painel esquerdo, selecione **Exemplo de modelo de auditoria**.
3. Na Guia Rápida **Versões**, selecione a versão **2** com o status **Rascunho**.
4. Selecione a Guia Rápida **Componentes de configuração**.
5. Selecione **Designer** para abrir o modelo de dados para edição.
6. Na página **Modelo de dados**, verifique se o campo `Root` está selecionado e selecione **Novo**.
7. Na caixa de diálogo suspensa, siga estas etapas:

    1. No grupo de campos **Novo nó como**, selecione a opção **Filho de um nó ativo**.
    2. No campo **Nome**, insira **Participante**.
    3. No campo **Tipo de item**, selecione **Lista de registros**.
    4. Selecione **Adicionar** para concluir a adição do novo campo.

8. Verifique se o campo `Root.Party` está selecionado e, na guia **Nó**, e selecione **Parâmetros**.
9. Na caixa de diálogo **Parâmetros**, siga estas etapas:

    1. Na guia **Parâmetros**, selecione **Novo**.
    2. No campo **Nome**, insira **PartyRefRecId**.
    3. No campo **Tipo**, selecione **Int64**.
    4. Marque a caixa de seleção **Lista**.
    5. Selecione **OK** para concluir a inserção dos parâmetros.

    > [!NOTE]
    > Você acabou de configurar o campo do modelo de dados `Root.Party` como um campo que é chamado quando um valor é fornecido no parâmetro **PartyRefRecId**. Esse valor deve estar presente na lista de registros que contêm um campo `Value` do tipo de dados *Int64*.

    ![Caixa de diálogo Parâmetros.](./media/er-data-model-parameterized-calls-model2a.png)

10. Verifique se o campo `Root.Party` ainda está selecionado e, depois, selecione **Novo**.
11. Na caixa de diálogo suspensa, siga estas etapas:

    1. No grupo de campos **Novo nó como**, selecione a opção **Filho de um nó ativo**.
    2. No campo **Nome**, insira **Nome**.
    3. No campo **Tipo de item**, selecione **String**.
    4. Selecione **Adicionar** para concluir a adição do novo campo.

12. Selecione **Salvar** e feche a página **Modelo de dados**.

    ![Estrutura do modelo de dados ER ajustado na página Designer de modelo de dados.](./media/er-data-model-parameterized-calls-model2b.png)

13. Na Guia Rápida **Versões**, em versão **2**, selecione **Alterar status** \> **Concluir**. Em seguida, selecione **OK**.

    > [!NOTE]
    > As alterações no modelo de dados são armazenadas na segunda revisão do componente do modelo de dados **Exemplo de modelo de auditoria** que está localizado na segunda versão da configuração de ER **Exemplo de modelo de auditoria**.

![Configuração do modelo de dados de ER atualizado na página Configurações.](./media/er-data-model-parameterized-calls-updated-model.png)

### <a name="adjust-the-imported-model-mapping"></a>Ajustar o mapeamento do modelo importado

1. Na página **Configurações**, na árvore de configurações no painel esquerdo, expanda **Exemplo de modelo de auditoria**.
2. Selecione **Exemplo de mapeamento de modelo de auditoria** e, na Guia Rápida **Versões**, selecione a segunda versão do mapeamento que se baseia na primeira versão do modelo de dados (versão **1.2**) e que tem um status **Rascunho**.
3. Selecione **Trocar base**.
4. No campo **Versão de destino**, deixe a versão **2** do modelo base do **Exemplo de modelo de auditoria**.
5. Selecione **OK** para trocar a base e alinhar seu mapeamento de modelo com as alterações recentes do modelo de dados.

    Observe que o número de versão do seu mapeamento de modelo editável foi alterado de **1.2** para **2.2** para indicar que a segunda versão do modelo está sendo usada como base no momento.

6. Selecione **Designer**.
7. Na página **Modelo para mapeamento de fonte de dados**, selecione **Designer** para o mapeamento de modelo atual.
8. Siga estas etapas para adicionar uma nova fonte de dados para acessar a tabela de aplicativos `DirPartyTable`:

    1. No painel **Tipos de fonte de dados**, selecione **Dynamics 365 for Operations \> Registros de tabela**.
    2. No painel **Fontes de dados**, selecione **Adicionar raiz**.
    3. No campo **Nome**, insira **PartyTable**.
    4. No campo **Tabela**, insira **DirPartyTable**.
    5. Selecione **OK** para concluir a adição da nova fonte de dados.

9. Siga estas etapas para adicionar uma nova fonte de dados aos registros para solicitar records de `DirPartyTable`, com base na lista de códigos de identificação de registro fornecida:

    1. No painel **Tipos de fonte de dados**, selecione **Geral \> Contêiner vazio**.
    2. No painel **Fontes de dados**, selecione **Adicionar raiz**.
    3. No campo **Nome**, insira **Dados**.
    4. Selecione **OK** para concluir a adição da nova fonte de dados.
    5. No painel **Fontes de dados**, selecione a fonte de dados **Dados**.
    6. No painel **Tipo de fonte de dados**, selecione **Funções \> Campo calculado**.
    7. No painel **Fontes de dados**, selecione **Adicionar**.
    8. No campo **Nome**, insira **DirParty**.
    9. Selecione **Editar fórmula**.
    10. Na página **Designer de fórmulas**, selecione **Parâmetros**.
    11. Na caixa de diálogo **Parâmetros**, siga estas etapas:

        1. Na guia **Parâmetros**, selecione **Novo**.
        2. No campo **Nome**, insira **DirPartyId**.
        3. No campo **Tipo**, selecione **Int64**.
        4. Marque a caixa de seleção **Lista**.
        5. Selecione **OK**.

        > [!NOTE]
        > Você acabou de configurar esse campo calculado para que ele aceite, no tempo de execução, o argumento de um único parâmetro configurado como uma lista de registros que tem um único campo `Value` do tipo *Int64*.

    12. No campo **Fórmula**, insira a seguinte expressão:

        `FILTER(PartyTable, VALUEINLARGE(PartyTable.RecId, DirPartyId, DirPartyId.Value))`

        > [!NOTE]
        > Você acabou de configurar o campo calculado `DirParty` para obter somente registros de `DirPartyTable` nos quais os códigos de identificação de registro são incluídos na lista `DirPartyId` fornecida como um argumento quando o campo `DirParty` é chamado.

        ![Fórmula para obter os nomes de participante da tabela de aplicativos na página do Designer de fórmulas.](./media/er-data-model-parameterized-calls-formula1.png)

    13. Selecione **Salvar** e feche a página **Designer de fórmulas**.
    14. Selecione **Salvar** e **OK** para concluir a adição da nova fonte de dados.

10. Siga estas etapas para associar a nova fonte de dados ao novo campo de modelo de dados, de forma que o modelo de dados seja usado para expor os nomes dos participantes:

    1. No painel **Modelo de dados**, selecione o campo de modelo de dados `Root.Party`.
    2. No painel **Modelo de dados**, selecione **Editar**.
    3. Na página **Designer de fórmulas**, no campo **Fórmula**, insira a expressão `Data.DirParty(PartyRefRecId)`.
    4. Selecione **Salvar** e feche a página **Designer de fórmulas**.

        > [!NOTE]
        > Você acabou de configurar a associação para chamar a fonte de dados configurada `Data.DirParty` e fornecer a lista de códigos de identificação de registro que serão especificados no formato quando o campo de modelo de dados `Root.Party` for chamado.

    5. No painel **Modelo de dados**, selecione o campo de modelo de dados `Root.Party.Name`.
    6. No painel **Modelo de dados**, selecione **Editar**.
    7. Na página **Designer de fórmulas**, no painel **Fonte de dados**, expanda **Dados \> DirParty**, e selecione **Nome**.
    8. Selecione **Adicionar fonte de dados**.
    9. Selecione **Salvar** e feche a página **Designer de fórmulas**.

    ![Estrutura de mapeamento de modelo de ER ajustado na página Designer de mapeamento de modelo.](./media/er-data-model-parameterized-calls-mapping2.png)

11. Selecione **Salvar** e feche a página **Designer de mapeamento de modelo**.
12. Feche a página **Modelo para mapeamento de fonte de dados**.
13. Na Guia Rápida **Versões**, em versão **2.2**, selecione **Alterar status \> Concluir**. Em seguida, selecione **OK**.

### <a name="adjust-the-imported-format"></a>Ajustar o formato importado

1. Na página **Configurações**, selecione **Exemplo de formato de auditoria**.
2. Na Guia Rápida **Versões**, selecione a versão **1.2** com o status **Rascunho**.
3. Selecione **Trocar base**.
4. No campo **Versão de destino**, deixe a versão **2** do modelo base do **Exemplo de modelo de auditoria**.
5. Selecione **OK** para trocar a base e alinhar seu formato com as alterações recentes do modelo de dados.
6. Selecione **Designer**.
7. Na página **Designer de formato** na árvore de estrutura de formato no painel esquerdo, selecione **Expandir/Recolher**.
8. Siga estas etapas para adicionar um novo elemento de formato para coletar códigos de identificação de registro dos participantes cujas transações estão presentes nos relatórios gerados.

    1. Na árvore de estrutura de formato, selecione o elemento de sequência **Report.Row.Trans**.
    2. Selecione **Adicionar**.
    3. Na caixa de diálogo **Adicionar**, selecione **Fonte de dados \> Item**.
    4. Na caixa de diálogo **Propriedade do componente**, no campo **Nome**, insira **ID**.
    5. No campo **Tipo de dados**, selecione **Int64**.
    6. Selecione **OK**.

    > [!NOTE]
    > Um elemento de **Fonte de dados \> Item** pode ser usado para executar cálculos internos e transformação de dados somente no escopo do formato em execução. Portanto, ao adicionar esse elemento de formato, você não altera o conteúdo de um documento gerado.

9. Siga estas etapas para adicionar novos elementos de formato para inserir nomes de participantes nos relatórios gerados:

    1. Selecione o elemento de sequência **Report.Row**.
    2. Selecione **Adicionar**.
    3. Na caixa de diálogo **Adicionar**, selecione **Texto \> Sequência**.
    4. Na caixa de diálogo **Propriedade do componente**, no campo **Nome**, insira **Participante**.
    5. Selecione **OK**.
    6. Selecione o elemento de sequência **Report.Row.Party**.
    7. Selecione **Adicionar**.
    8. Na caixa de diálogo **Adicionar**, selecione **Texto \> Cadeia de caracteres**.
    9. Na caixa de diálogo **Propriedade do componente**, no campo **Nome**, insira **Nome**.
    10. Selecione **OK**.

10. Siga estas etapas para adicionar uma nova fonte de dados para coletar códigos de identificação de registro dos participantes cujas transações estão presentes nos relatórios gerados:

    1. Na guia **Mapeamento**, selecione **Adicionar raiz**.
    2. Na caixa de diálogo **Adicionar fonte de dados**, selecione **Funções \> Coleta de dados**.
    3. Na caixa de diálogo **Propriedades da fonte de dados da 'coleta de dados'**, no campo **Nome**, insira **PartyIds**.
    4. No campo **Tipo de item**, selecione **Int64**.
    5. Selecione **OK**.

11. Siga estas etapas para adicionar uma nova associação para coletar códigos de identificação de registro dos participantes cujas transações estão presentes nos relatórios gerados:

    1. Na árvore de estrutura de formato, selecione o elemento do item de dados **Report.Row.Trans.Id**.
    2. Selecione **Editar fórmula**.
    3. Na página **Designer de fórmulas**, insira a expressão `PartyIds.Collect(model.Transaction.Party.RecId)`.
    4. Selecione **Salvar** e feche a página **Designer de fórmulas**.

12. Siga estas etapas para adicionar novas associações para inserir nomes de participantes nos relatórios gerados:

    1. Na árvore de estrutura de formato, selecione o elemento de sequência **Report.Party**.
    2. Selecione **Editar fórmula**.
    3. Na página **Designer de fórmulas**, insira a expressão `model.Party(PartyIds.Result)`.
    4. Selecione **Salvar** e feche a página **Designer de fórmulas**.
    5. Na árvore de estrutura de formato, selecione o elemento de sequência **Report.Party.Name**.
    6. Na guia **Mapeamento**, selecione o campo do modelo de dados `model.Party.Name`.
    7. Selecione **Associar**.

    ![Estrutura do formato de ER ajustado na página Designer de formato.](./media/er-data-model-parameterized-calls-format2.png)

13. Selecione **Salvar** e feche a página **Designer de formato**.
14. Feche a página **Modelo para mapeamento de fonte de dados**.
15. Na Guia Rápida **Versões**, em versão **2.2**, selecione **Alterar status** \> **Concluir**. Em seguida, selecione **OK**.

### <a name="run-the-adjusted-format"></a>Executar o formato ajustado

1. Na página **Configurações**, selecione **Exemplo de formato de auditoria** e, no Painel de Ações, selecione **Executar**.
2. Na caixa de diálogo **Parâmetros do relatório eletrônico**, na guia **Registros a serem incluídos**, selecione **Filtro**.
3. Especifique as condições para selecionar as transações de imposto dos comprovantes **PIV-110000004** e **INV-10000001**.
4. Selecione **OK**.
5. Selecione **OK**.
6. Revise o documento gerado que contém as transações de imposto dos comprovantes selecionados e os nomes do cliente e do fornecedor correspondentes.

    ![Visualização do documento gerado com transações de imposto e nomes dos participantes.](./media/er-data-model-parameterized-calls-output2.png)

7. Acesse **Contas a pagar** \> **Fornecedores** \> **Todos os fornecedores** e revise os detalhes do comprovante selecionado **PIV-110000004**, incluindo o nome do fornecedor.

    ![Revisando os detalhes do comprovante de compra nas páginas Todos os fornecedores e Diário de faturas.](./media/er-data-model-parameterized-calls-review1.gif)

8. Acesse **Contas a receber** \> **Clientes** \> **Todos os clientes** e revise os detalhes do comprovante selecionado **INV-10000001**, incluindo o nome do cliente.

    ![Revisando os detalhes do comprovante de venda nas páginas Todos os clientes e Impostos lançados.](./media/er-data-model-parameterized-calls-review2.gif)

Para obter mais detalhes sobre a execução da solução de ER, use o analisador de [rastreamento de desempenho](trace-execution-er-troubleshoot-perf.md) interno.

## <a name="additional-resources"></a>Recursos adicionais

- [Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado](er-calculated-field-type.md)
- [Rastrear a execução de formatos de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md)
- [Usar fontes de dados de COLETA DE DADOS em formatos de relatório eletrônico](er-data-collection-data-sources.md)
- [Função ValueInLarge do ER](er-functions-logical-valueinlarge.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
