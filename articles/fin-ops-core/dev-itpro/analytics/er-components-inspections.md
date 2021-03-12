---
title: Inspecionar o componente de ER configurado para evitar problemas de runtime
description: Este tópico explica como inspecionar os componentes de Relatório Eletrônico (ER) configurados para evitar problemas de runtime.
author: NickSelin
manager: AnnBe
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4ba696fb7a8d9083d11cc29953cf1340a581afcf
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797332"
---
# <a name="inspect-the-configured-er-component-to-prevent-runtime-issues"></a>Inspecionar o componente de ER configurado para evitar problemas de runtime

[!include[banner](../includes/banner.md)]

Cada componente de [mapeamento de modelo](general-electronic-reporting.md#data-model-and-model-mapping-components) e [formato](general-electronic-reporting.md#FormatComponentOutbound) de [Relatório Eletrônico (ER)](general-electronic-reporting.md) configurado pode ser [validado](er-fillable-excel.md#validate-an-er-format) durante o design. Durante essa validação, uma verificação de consistência é realizada para ajudar a evitar problemas de runtime, como erros de execução e degradação de desempenho. O caminho de um elemento problemático é fornecido para cada problema encontrado. Alguns problemas têm uma correção automática.

Por padrão, a validação é aplicada automaticamente nos seguintes casos para uma configuração de ER que contém os componentes de ER mencionados acima:

- Ao [importar](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) uma nova [versão](general-electronic-reporting.md#component-versioning) de uma configuração de ER para sua instância do Microsoft Dynamics 365 Finance.
- Ao alterar o [status](general-electronic-reporting.md#component-versioning) da configuração de ER editável de **Rascunho** para **Concluída**.
- Ao [trocar a base](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) de uma configuração de ER editável aplicando uma nova versão base.

É possível executar essa validação de forma explícita. Selecione uma das três opções a seguir e siga as etapas fornecidas:

- Opção 1:

    1. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
    2. Na árvore de configurações no painel esquerdo, selecione a configuração de ER desejada que contém o componente de mapeamento de formato ou modelo de ER.
    3. Na FastTab **Versões**, selecione a versão desejada da configuração de ER selecionada.
    4. No Painel de Ações, selecione **Validar**.

- Opção 2, para um formato de ER:

    1. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
    2. Na árvore de configurações no painel esquerdo, selecione a configuração de ER desejada que contém o componente do formato de ER.
    3. Na FastTab **Versões**, selecione a versão desejada da configuração de ER selecionada.
    4. No Painel de Ação, selecione **Designer**.
    5. Na página **Designer de formato**, no Painel de Ações, selecione **Validar**.

- Opção 3, para um mapeamento de modelo de ER:

    1. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
    2. Na árvore de configurações no painel esquerdo, selecione a configuração de ER desejada que contém o componente de mapeamento de modelo de ER.
    3. Na FastTab **Versões**, selecione a versão desejada da configuração de ER selecionada.
    4. No Painel de Ação, selecione **Designer**.
    5. Na página **Modelo para mapeamento de fonte de dados**, no Painel de Ações, selecione **Designer**.
    6. Na página **Designer de mapeamento de modelo**, no Painel de Ações, selecione **Validar**.

Para ignorar a validação quando a configuração for importada, siga estas etapas:

1. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Defina a opção **Validar a configuração após a importação** como **Não**.

Para ignorar a validação quando você alterar o status ou a base da versão, siga estas etapas:

1. Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Defina a opção **Ignorar validação na alteração e troca do status de configuração** como **Sim**.

O ER usa as seguintes categorias para agrupar inspeções de verificação de consistência:

- **Capacidade de execução** – inspeções que detectam problemas críticos que podem ocorrer no runtime. Geralmente, esses problemas são classificados como **Erro**. 
- **Desempenho** – inspeções que detectam problemas que podem causar execução ineficiente de componentes de ER configurados. Geralmente, esses problemas são classificados como **Aviso**.
- **Integridade de dados** – inspeções que detectam problemas que podem causar perda de dados ou problemas de runtime. Geralmente, esses problemas são classificados como **Aviso**.

## <a name="list-of-inspections"></a>Lista de inspeções

A tabela a seguir fornece uma visão geral das inspeções fornecidas pelo ER. Para obter mais informações sobre essas inspeções, use os links na primeira coluna para acessar as seções relevantes deste tópico. Essas seções explicam os tipos de componentes para os quais o ER fornece inspeções e como você pode reconfigurar componentes de ER para ajudar a evitar problemas.

<table>
<thead>
<tr>
<th>Organização</th>
<th>Categoria</th>
<th>Nível</th>
<th>Mensagem</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href='#i1'>Conversão de tipo</a></td>
<td>Capacidade de execução</td>
<td>Erro</td>
<td>
<p>Não é possível converter a expressão do tipo &lt;type&gt; em um campo do tipo &lt;type&gt;.</p>
<p><b>Erro de runtime:</b> execução para o tipo</p>
</td>
</tr>
<tr>
<td><a href='#i2'>Compatibilidade de tipo</a></td>
<td>Capacidade de execução</td>
<td>Erro</td>
<td>
<p>A expressão configurada não pode ser usada como a associação do elemento de formato atual a uma fonte de dados, já que essa expressão retorna o valor de tipo de dados &lt;type&gt; que está além do escopo dos tipos de dados suportados pelo elemento de formato atual do tipo &lt;type&gt;.</p>
<p><b>Erro de runtime:</b>execução de tipo</p>
</td>
</tr>
<tr>
<td><a href='#i3'>Elemento de configuração ausente</a></td>
<td>Capacidade de execução</td>
<td>Erro</td>
<td>
<p>Caminho &lt;path&gt; não encontrado.</p>
<p><b>Erro de runtime:</b>elemento do &lt;path&gt; de configuração não encontrado</p>
</td>
</tr>
<tr>
<td><a href='#i4'>Capacidade de execução de uma expressão com função FILTER</a></td>
<td>Capacidade de execução</td>
<td>Erro</td>
<td>
<p>A expressão de lista da função FILTER não pode ser consultada.</p>
<p><b>Erro de runtime:</b> não há suporte para filtragem. Valide a configuração para obter mais detalhes sobre esse erro.</p>
</td>
</tr>
<tr>
<td rowspan='2'><a href='#i5'>Capacidade de execução de uma fonte de dados GROUPBY</a></td>
<td>Capacidade de execução</td>
<td>Erro</td>
<td>O caminho de &lt;path&gt; não oferece suporte à consulta.</td>
</tr>
<tr>
<td>Capacidade de execução</td>
<td>Erro</td>
<td>
<p>A função "Group by" não pode ser executada na consulta.</p>
<p><b>Erro de runtime: </b>a função "Group by" não pode ser executada na consulta.</p>
</td>
</tr>
<tr>
<td><a href='#i6'>Capacidade de execução de uma fonte de dados JOIN</a></td>
<td>Capacidade de execução</td>
<td>Erro</td>
<td>
<p>Não é possível associar um &lt;path&gt; de lista que não seja um filtro na consulta.</p>
<p><b>Erro de runtime:</b>a fonte de dados associada da função deve ser um campo calculado de expressão de filtro chamado incorretamente.</p>
</td>
</tr>
<tr>
<td><a href='#i7'>Preferência da função FILTER x WHERE</a></td>
<td>Desempenho</td>
<td>Aviso</td>
<td>É preferível usar a função FILTER para a expressão do que WHERE do ponto de vista do desempenho. Selecione Corrigir para substituí-la automaticamente.</td>
</tr>
<tr>
<td><a href='#i8'>Preferência da função ALLITEMSQUERY x ALLITEMS</a></td>
<td>Desempenho</td>
<td>Aviso</td>
<td>É preferível usar a função ALLITEMSQUERY para a expressão do que ALLITEMS do ponto de vista do desempenho. Selecione Corrigir para substituí-la automaticamente.</td>
</tr>
<tr>
<td><a href='#i9'>Consideração dos casos de lista vazia</a></td>
<td>Capacidade de execução</td>
<td>Aviso</td>
<td>
<p>O &lt;caminho&gt; da lista não tem nenhuma verificação para caso de lista vazia, o que pode resultar em um erro no runtime. Adicione uma verificação para caso de lista vazia.</p>
<p><b>Erro de runtime:</b> a lista está vazia no &lt;caminho&gt;</p>
<p><b><a href='#i9a'>Possível problema</a>:</b> a fonte de dados que está preenchendo a linha contém vários registros</p>
</td>
</tr>
<tr>
<td><a href='#i10'>Capacidade de execução de uma expressão com função FILTER (armazenamento em cache)</a></td>
<td>Capacidade de execução</td>
<td>Erro</td>
<td>
<p>A função FILTER não pode ser aplicada ao tipo de fonte de dados selecionado. Uma fonte de dados de tipo de registros de Tabela é aplicável somente quando não é armazenada em cache e não tem fontes de dados aninhadas adicionadas manualmente.</p>
<p><b>Erro de runtime:</b> não há suporte para filtragem. Valide a configuração para obter mais detalhes sobre esse erro.</p>
</td>
</tr>
<tr>
<td><a href='#i11'>Associação ausente</a></td>
<td>Capacidade de execução</td>
<td>Aviso</td>
<td>
<p>O &lt;path&gt; do caminho não tem associação a nenhuma fonte de origem ao usar o mapeamento do modelo.</p>
<p><b>Erro de runtime:</b>o &lt;path&gt; do caminho não está associado</p>
</td>
</tr>
<tr>
<td><a href='#i12'>Modelo não vinculado</a></td>
<td>Integridade dos dados</td>
<td>Aviso</td>
<td>O &lt;nome&gt; do arquivo não está vinculado a nenhum componente de arquivo e será removido após a alteração do status da versão de configuração.</td>
</tr>
<tr>
<td><a href='#i13'>Formato não sincronizado</a></td>
<td>Integridade dos dados</td>
<td>Aviso</td>
<td>O nome definido para &lt;nome do componente&gt; não existe no &lt;nome da planilha&gt; do Excel</td>
</tr>
</tbody>
</table>

## <a name="type-conversion"></a><a id="i1"></a>Conversão de tipo

O ER verifica se o tipo de dados de um campo de modelo de dados é compatível com o tipo de dados de uma expressão que está configurada como a associação desse campo. Se os tipos de dados forem incompatíveis, ocorrerá um erro de validação no designer de mapeamento de modelo de ER. A mensagem recebida informa que o ER não pode converter uma expressão do tipo A em um campo de tipo B.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar os componentes de mapeamento de modelo de ER e de modelo de dados de ER simultaneamente.
2. Na árvore do modelo de dados, adicione um campo denominado **X** e selecione **Inteiro** como o tipo de dados.

    ![O campo X e o tipo de dados Inteiro são adicionados à árvore de modo de dados na página Modelo de dados](./media/er-components-inspections-01.png)

3. No painel de fontes de dados do mapeamento de modelo, adicione uma fonte de dados do tipo **Campo calculado**.
4. Nomeie a nova fonte de dados como **Y** e configure-a para que contenha a expressão `INTVALUE(100)`.
5. Associe **X** a **Y**.
6. No designer de modelos de dados, altere o tipo de dados do campo **X** de **Inteiro** para **Int64**.
7. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo**.

    ![Validando o componente de mapeamento de modelo editável na página Designer de mapeamento de modelo](./media/er-components-inspections-01.gif)

8. Selecione **Validar** para inspecionar o componente de mapeamento de modelo da configuração de ER selecionada na página **Configurações**.

    ![Validar para inspecionar o componente de mapeamento de modelo na página Configurações](./media/er-components-inspections-01a.png)

9. Observe que ocorre um erro de validação. A mensagem informa que o valor do tipo **Inteiro** retornado pela expressão `INTVALUE(100)` da fonte de dados **Y** não pode ser armazenado no campo de modelo de dados **X** do tipo **Int64**.

A ilustração a seguir mostra o erro de runtime exibido se você ignorar o aviso e selecionar **Executar** para executar um formato configurado para usar o mapeamento de modelo.

![Erros de runtime na página Designer de formato](./media/er-components-inspections-01b.png)

### <a name="automatic-resolution"></a>Resolução automática

Nenhuma opção para corrigir esse problema automaticamente está disponível.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Atualize a estrutura do modelo de dados alterando o tipo de dados do campo de modelo de dados de forma que ele corresponda ao tipo de dados da expressão que está configurada para a associação desse campo. Para o exemplo anterior, o tipo de dados do campo **X** deve ser alterado novamente para **Inteiro**.

#### <a name="option-2"></a>Opção 2

Atualize o mapeamento de modelo alterando a expressão da fonte de dados associada ao campo de modelo de dados. Para o exemplo anterior, a expressão da fonte de dados **Y** deve ser alterada para `INT64VALUE(100)`.

## <a name="type-compatibility"></a><a id="i2"></a>Compatibilidade de tipo

O ER verifica se o tipo de dados de um elemento de formato é compatível com o tipo de dados de uma expressão que está configurada como esse elemento de formato. Se os tipos de dados forem incompatíveis, ocorrerá um erro de validação no designer de operações de ER. A mensagem recebida informa que expressão configurada não pode ser usada como a associação do elemento de formato atual a uma fonte de dados, já que a expressão retorna um valor de tipo de dados A que está além do escopo dos tipos de dados suportados pelo elemento de formato atual do tipo B.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar os componentes de formato de ER e o modelo de dados de ER simultaneamente.
2. Na árvore do modelo de dados, adicione um campo denominado **X** e selecione **Inteiro** como o tipo de dados.
3. Na árvore de estrutura de formato, adicione um elemento de formato do tipo **Numérico**.
4. Nomeie o novo elemento de formato **Y**. No campo de **tipo Numérico**, selecione **Inteiro** como o tipo de dados.
5. Associe **X** a **Y**.
6. Na árvore de estrutura de formato, altere o tipo de dados do elemento de formato **Y** de **Inteiro** para **Int64**.
7. Selecione **Validar** para inspecionar o componente de formato editável na página **Designer de formato**.

    ![Validando compatibilidade de tipo na página Designer de formato](./media/er-components-inspections-02.gif)

8. Observe que ocorre um erro de validação. A mensagem informa que a expressão configurada pode aceitar somente valores **Int64**. Portanto, o valor do campo de modelo de dados **X** do tipo **Inteiro** não pode ser inserido no elemento de formato **Y**.

### <a name="automatic-resolution"></a>Resolução automática

Nenhuma opção para corrigir esse problema automaticamente está disponível.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Atualize a estrutura do formato alterando o tipo de dados do elemento de formato **Numérico** de forma que ele corresponda ao tipo de dados da expressão que está configurada para a associação desse elemento. No exemplo anterior, o valor de **tipo Numérico** do elemento de formato **X** deve ser alterado novamente para **Inteiro**.

#### <a name="option-2"></a>Opção 2

Atualize o mapeamento de formato do elemento de formato **X** alterando a expressão de `model.X` para `INT64VALUE(model.X)`.

## <a name="missing-configuration-element"></a><a id="i3"></a>Elemento de configuração ausente

O ER verifica se as expressões de associação contêm somente fontes de dados configuradas no componente de ER editável. Para cada associação que contém uma fonte de dados ausente no componente de ER editável, ocorre um erro de validação no Designer de operações de ER ou no Designer de mapeamento de modelo de ER.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar os componentes de mapeamento de modelo de ER e de modelo de dados de ER simultaneamente.
2. Na árvore do modelo de dados, adicione um campo denominado **X** e selecione **Inteiro** como o tipo de dados.

    ![A árvore do modelo de dados com campo X e o tipo de dados Inteiro na página Modelo de dados](./media/er-components-inspections-01.png)

3. No painel de fontes de dados do mapeamento de modelo, adicione uma fonte de dados do tipo **Campo calculado**.
4. Nomeie a nova fonte de dados como **Y** e configure-a para que contenha a expressão `INTVALUE(100)`.
5. Associe **X** a **Y**.
6. No designer de mapeamento de modelo, no painel de fontes de dados, exclua a fonte de dados **Y**.
7. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo**.

    ![Verifique o componente de mapeamento de modelo de ER editável na página Designer de mapeamento de modelo](./media/er-components-inspections-03.gif)

8. Observe que ocorre um erro de validação. A mensagem informa que a associação do campo de modelo de dados **X** contém o caminho referente à fonte de dados **Y**, mas essa fonte não foi encontrada.

### <a name="automatic-resolution"></a>Resolução automática

Selecione **Desvincular** para corrigir automaticamente esse problema removendo a associação de fonte de dados ausente.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Desassocie o campo de modelo de dados **X** para que ele pare de referenciar a fonte de dados **Y** inexistente.

#### <a name="option-2"></a>Opção 2

No painel de fontes de dados do designer de mapeamento de modelo de ER, adicione a fonte de dados **Y** novamente.

## <a name="executability-of-an-expression-with-filter-function"></a><a id="i4"></a>Capacidade de execução de uma expressão com função FILTER

A função de ER [FILTER](er-functions-list-filter.md) incorporada é usada para acessar tabelas de aplicativos, exibições ou entidades de dados, fazendo uma única chamada SQL para obter os dados necessários como uma lista de registros. Uma fonte de dados do tipo **Lista de registros** é usada como um argumento dessa função e especifica a origem do aplicativo para a chamada. O ER verifica se uma consulta SQL direta pode ser estabelecida com uma fonte de dados referenciada na função `FILTER`. Se uma consulta direta não puder ser estabelecida, ocorrerá um erro de validação no designer de mapeamento de modelo de ER. A mensagem recebida informa que a expressão de ER que inclui a função `FILTER` não pode ser executada no runtime. 

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar o componente de mapeamento de modelo de ER.
2. Adicione uma fonte de dados do tipo **Registros de tabela** \\ do Dynamics 365 for Operations.
3. Nomeie a nova fonte de dados como **Vendor**. No campo **Tabela**, selecione **VendTable** para especificar que essa fonte de dados solicitará a tabela VendTable.
4. Adicione uma fonte de dados do tipo **Campo calculado**.
5. Nomeie a nova fonte de dados como **FilteredVendor** e configure-a para que contenha a expressão `FILTER(Vendor, Vendor.AccountNum="US-101")`.
6. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo** e verifique se a expressão `FILTER(Vendor, Vendor.AccountNum="US-101")` na fonte de dados **Vendor** pode ser consultada.
7. Modifique a fonte de dados **Vendor** adicionando um campo aninhado do tipo **Campo calculado** para obter o número da conta do fornecedor resumido.
8. Nomeie o novo campo aninhado **$AccNumber** e configure-a para que contenha a expressão `TRIM(Vendor.AccountNum)`.
9. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo** e verifique se a expressão `FILTER(Vendor, Vendor.AccountNum="US-101")` na fonte de dados **Vendor** pode ser consultada.

    ![Verificando se a expressão pode ser consultada na página Designer de mapeamento de modelo](./media/er-components-inspections-04.gif)

10. Observe que ocorre um erro de validação, porque a fonte de dados **Vendor** contém um campo aninhado do tipo **Campo calculado** que não permite que a expressão da fonte de dados **FilteredVendor** seja convertida na instrução SQL direta.

A ilustração a seguir mostra o erro de runtime exibido se você ignorar o aviso e selecionar **Executar** para executar um formato configurado para usar o mapeamento de modelo.

![Erros de runtime que ocorrem quando você executa o formato editável na página Designer de formato](./media/er-components-inspections-04a.png)

### <a name="automatic-resolution"></a>Resolução automática

Nenhuma opção para corrigir esse problema automaticamente está disponível.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Em vez de adicionar um campo aninhado do tipo **Campo calculado** à fonte de dados **Vendor**, adicione o campo aninhado **$AccNumber** à fonte de dados **FilteredVendor** e configure-a para que ela contenha a expressão `TRIM(FilteredVendor.AccountNum)`. Dessa forma, a expressão `FILTER(Vendor, Vendor.AccountNum="US-101")` pode ser executada no nível do SQL e pode calcular o campo aninhado **$AccNumber** posteriormente.

#### <a name="option-2"></a>Opção 2

Altere a expressão da fonte de dados **FilteredVendor** de `FILTER(Vendor, Vendor.AccountNum="US-101")`para `WHERE(Vendor, Vendor.AccountNum="US-101")`. Não recomendamos que você altere a expressão para uma tabela que tenha um grande volume de dados (tabela transacional), pois todos os registros serão buscados e a seleção dos registros necessários será feita na memória. Portanto, essa abordagem pode causar um baixo desempenho. Para obter mais informações, consulte [Função de ER WHERE](er-functions-list-where.md).

## <a name="executability-of-a-groupby-data-source"></a><a id="i5"></a>Capacidade de execução de uma fonte de dados GROUPBY

A fonte de dados **GROUPBY** divide o resultado da consulta em grupos de registros, geralmente com a finalidade de executar uma ou mais agregações em cada grupo. Cada fonte de dados **GROUPBY** pode ser configurada de forma que seja executada no nível do banco de dados ou na memória. Quando uma fonte de dados **GROUPBY** é configurada para ser executada no nível do banco de dados, o ER verifica se uma consulta SQL direta pode ser estabelecida com uma fonte de dados referenciada nessa fonte. Se uma consulta direta não puder ser estabelecida, ocorrerá um erro de validação no designer de mapeamento de modelo de ER. A mensagem recebida informa que a fonte de dados **GROUPBY** configurada não pode ser executada no runtime.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar o componente de mapeamento de modelo de ER.
2. Adicione uma fonte de dados do tipo **Registros de tabela** \\ do Dynamics 365 for Operations.
3. Nomeie a nova fonte de dados como **Trans**. No campo **Table**, selecione **VendTrans** para especificar que essa fonte de dados solicite a tabela VendTrans.
4. Adicione uma fonte de dados do tipo **Agrupar por**.
5. Nomeie a nova fonte de dados como **GroupedTrans** e configure-a da seguinte maneira:

    - Selecione a fonte de dados **Trans** como a fonte de registros que devem ser agrupados.
    - No campo **Local de execução**, selecione **Consulta** para especificar que você deseja executar essa fonte de dados no nível do banco de dados.

    ![Configurando a fonte de dados na página de parâmetros Editar "Agrupar por"](./media/er-components-inspections-05a.gif)

6. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo** e verifique se a fonte de dados **GroupedTrans** pode ser consultada.
7. Modifique a fonte de dados **Trans** adicionando um campo aninhado do tipo **Campo calculado** para obter o número da conta do fornecedor resumido.
8. Nomeie a nova fonte de dados como **$AccNumber** e configure-a para que contenha a expressão `TRIM(Trans.AccountNum)`.

    ![Configurando a fonte de dados na página Designer de mapeamento de modelo](./media/er-components-inspections-05a.png)

9. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo** e verifique se a fonte de dados **GroupedTrans** pode ser consultada.

    ![Valide o componente de mapeamento de modelo de ER e verifique se a fonte de dados GroupedTrans configurada pode ser consultada na página Designer de mapeamento de modelo](./media/er-components-inspections-05b.png)

10. Observe que ocorre um erro de validação, porque a fonte de dados **Trans** contém um campo aninhado do tipo **Campo calculado** que não permite que a chamada para a fonte de dados **GroupedTrans** seja convertida na instrução SQL direta.

A ilustração a seguir mostra o erro de runtime exibido se você ignorar o aviso e selecionar **Executar** para executar um formato configurado para usar o mapeamento de modelo.

![Erros de runtime que ocorrem quando o aviso é ignorado na página Designer de formato](./media/er-components-inspections-05c.png)

### <a name="automatic-resolution"></a>Resolução automática

Nenhuma opção para corrigir esse problema automaticamente está disponível.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Em vez de adicionar um campo aninhado do tipo **Campo calculado** à fonte de dados **Trans**, adicione o campo aninhado **$AccNumber** para o item **GroupedTrans.lines** da fonte de dados **GroupedTrans** e configure-a para que ela contenha a expressão `TRIM(GroupedTrans.lines.AccountNum)`. Dessa forma, a fonte de dados **GroupedTrans** pode ser executada no nível do SQL e pode calcular o campo aninhado **$AccNumber** posteriormente.

#### <a name="option-2"></a>Opção 2

Altere o valor do campo **Local de execução** da fonte de dados **GroupedTrans** de **Consulta** para **Na memória**. Não recomendamos que você altere o valor para uma tabela que tenha um grande volume de dados (tabela transacional), pois todos os registros serão buscados e o agrupamento e a agregação serão feitos na memória. Portanto, essa abordagem pode causar um baixo desempenho.

## <a name="executability-of-a-join-data-source"></a><a id="i6"></a>Capacidade de execução de uma fonte de dados JOIN

A fonte de dados [JOIN](er-join-data-sources.md) combina registros de duas ou mais tabelas de banco de dados com base nos campos relacionados. Cada fonte de dados **JOIN** pode ser configurada de forma que seja executada no nível do banco de dados ou na memória. Quando uma fonte de dados **JOIN** é configurada para ser executada no nível do banco de dados, o ER verifica se uma consulta SQL direta pode ser estabelecida com fontes de dados referenciadas nessa fonte. Se uma consulta SQL não puder ser estabelecida com pelo menos uma fonte de dados referenciada, ocorrerá um erro de validação no designer de mapeamento de modelo de ER. A mensagem recebida informa que a fonte de dados **JOIN** configurada não pode ser executada no runtime.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar o componente de mapeamento de modelo de ER.
2. Adicione uma fonte de dados do tipo **Registros de tabela** \\ do Dynamics 365 for Operations.
3. Nomeie a nova fonte de dados como **Vendor**. No campo **Tabela**, selecione **VendTable** para especificar que essa fonte de dados solicitará a tabela VendTable.
4. Adicione uma fonte de dados do tipo **Registros de tabela** \\ do Dynamics 365 for Operations.
5. Nomeie a nova fonte de dados como **Trans**. No campo **Table**, selecione **VendTrans** para especificar que essa fonte de dados solicite a tabela VendTrans.
6. Adicione uma fonte de dados do tipo **Campo calculado** como o campo aninhado da fonte de dados **Vendor**.
7. Nomeie a nova fonte de dados como **FilteredTrans** e configure-a para que contenha a expressão `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`.
8. Adicione uma fonte de dados do tipo **Junção**.
9. Nomeie a nova fonte de dados como **JoinedList** e configure-a da seguinte maneira:

    1. Adicione a fonte de dados **Vendor** como o primeiro conjunto de registros a unir.
    2. Adicione a fonte de dados **Vendor.FilteredTrans** como o segundo conjunto de registros a unir. Selecione **INTERNO** como o tipo.
    3. No campo **Executar**, selecione **Consulta** para especificar que você deseja executar essa fonte de dados no nível do banco de dados.

    ![Configurando a fonte de dados na página Designer de junção](./media/er-components-inspections-06a.gif)

10. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo** e verifique se a fonte de dados **JoinedList** pode ser consultada.
11. Altere a expressão da fonte de dados **Vendor.FilteredTrans** de `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`para `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)`.
12. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo** e verifique se a fonte de dados **JoinedList** pode ser consultada.

    ![Valide o componente de mapeamento de modelo editável e verifique se a fonte de dados JoinedList pode ser consultada na página Designer de mapeamento de modelo](./media/er-components-inspections-06b.png)

13. Observe que ocorre um erro de validação, pois a expressão da fonte de dados **Vendor.FilteredTrans** não pode ser convertida na chamada SQL direta. Além disso, a chamada SQL direta não permite que a chamada da fonte de dados **JoinedList** seja traduzida para a instrução SQL direta.

    ![Erros de runtime de falha na validação da fonte de dados JoinedList na página Designer de mapeamento de modelo](./media/er-components-inspections-06c.png)

A ilustração a seguir mostra o erro de runtime exibido se você ignorar o aviso e selecionar **Executar** para executar um formato configurado para usar o mapeamento de modelo.

![Executando o formato editável na página Designer de formato](./media/er-components-inspections-06e.png)

### <a name="automatic-resolution"></a>Resolução automática

Nenhuma opção para corrigir esse problema automaticamente está disponível.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Altere a expressão da fonte de dados **Vendor.FilteredTrans** de `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)`Voltar para `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`, conforme indicado no aviso.

![Expressão atualizada da fonte de dados na página Designer de mapeamento de modelo](./media/er-components-inspections-06d.png)

#### <a name="option-2"></a>Opção 2

Altere o valor do campo **Executar** da fonte de dados **JoinedList** de **Consulta** para **Na memória**. Não recomendamos que você altere o valor para uma tabela que tenha um grande volume de dados (tabela transacional), pois todos os registros serão buscados e a união ocorre na memória. Portanto, essa abordagem pode causar um baixo desempenho. Um aviso de validação é exibido para informar sobre esse risco.

## <a name="preferability-of-filter-vs-where-function"></a><a id="i7"></a>Preferência da função FILTER x WHERE

A função de ER [FILTER](er-functions-list-filter.md) incorporada é usada para acessar tabelas de aplicativos, exibições ou entidades de dados, fazendo uma única chamada SQL para obter os dados necessários como uma lista de registros. A função [WHERE](er-functions-list-where.md) busca todos os registros da origem específica e faz a seleção de registro na memória. Uma fonte de dados do tipo **Lista de registros** é usada como um argumento dessas duas funções e especifica um origem para obter os registros. O ER verifica se uma chamada SQL direta pode ser estabelecida com uma fonte de dados referenciada na função **WHERE**. Se uma chamada direta não puder ser estabelecida, será exibido um aviso de validação no Designer de mapeamento de modelo de ER. A mensagem recomenda que você use a função **FILTER** em vez da função **WHERE** para melhorar a eficiência.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar o componente de mapeamento de modelo de ER.
2. Adicione uma fonte de dados do tipo **Registros de tabela** \\ do Dynamics 365 for Operations.
3. Nomeie a nova fonte de dados como **Trans**. No campo **Table**, selecione **VendTrans** para especificar que essa fonte de dados solicite a tabela VendTrans.
4. Adicione uma fonte de dados do tipo **Campo calculado** como o campo aninhado da fonte de dados **Vendor**.
5. Nomeie a nova fonte de dados como **FilteredTrans** e configure-a para que contenha a expressão `WHERE(Trans, Trans.AccountNum="US-101")`.
6. Adicione uma fonte de dados do tipo **Registros de tabela** \\ do Dynamics 365 for Operations.
7. Nomeie a nova fonte de dados como **Vendor**. No campo **Tabela**, selecione **VendTable** para especificar que essa fonte de dados solicitará a tabela VendTable.
8. Adicione uma fonte de dados do tipo **Campo calculado**.
9. Nomeie a nova fonte de dados como **FilteredVendor** e configure-a para que contenha a expressão `WHERE(Vendor, Vendor.AccountNum="US-101")`.
10. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo**.

    ![Valide para inspecionar o componente de mapeamento de modelo editável na página Designer de mapeamento de modelo](./media/er-components-inspections-07a.png)

11. Observe que os avisos de validação recomendam que você use a função **FILTER** em vez da função **WHERE** para as fontes de dados **FilteredVendor** e **FilteredTrans**.

    ![Avisos de validação recomendando a função Filter em vez da função Where na página Designer de mapeamento de modelo](./media/er-components-inspections-07b.png)

### <a name="automatic-resolution"></a>Resolução automática

Selecione **Corrigir** para substituir automaticamente a função **WHERE** pela função **FILTER** na expressão de todas as fontes de dados que aparecem na grade, na guia **Avisos**, para esse tipo de inspeção.

Como alternativa, você pode selecionar a linha para um único aviso na grade e depois **Corrigir selecionados**. Nesse caso, somente a expressão mencionada no aviso selecionado é alterada automaticamente na fonte de dados.

![Selecione Corrigir para substituir automaticamente a função Where pela função Filter na página Designer de mapeamento de modelo](./media/er-components-inspections-07c.png)

### <a name="manual-resolution"></a>Resolução manual

Você pode ajustar manualmente as expressões de todas as fontes de dados na grade de validação substituindo a função **WHERE** pela função **FILTER**.

## <a name="preferability-of-allitemsquery-vs-allitems-function"></a><a id="i8"></a>Preferência da função ALLITEMSQUERY x ALLITEMS

As funções incorporadas de ER [ALLITEMS](er-functions-list-allitems.md)e [ALLITEMSQUERY](er-functions-list-allitemsquery.md) obtêm um valor de **Lista de registro** simplificado que consiste em uma lista de registros que representam todos os itens correspondentes ao caminho especificado. O ER verifica se uma chamada SQL direta pode ser estabelecida com uma fonte de dados referenciada na função **ALLITEMS**. Se uma chamada direta não puder ser estabelecida, será exibido um aviso de validação no Designer de mapeamento de modelo de ER. A mensagem recomenda que você use a função **ALLITEMSQUERY** em vez da função **ALLITEMS** para melhorar a eficiência.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar o componente de mapeamento de modelo de ER.
2. Adicione uma fonte de dados do tipo **Registros de tabela** \\ do Dynamics 365 for Operations.
3. Nomeie a nova fonte de dados como **Vendor**. No campo **Tabela**, selecione **VendTable** para especificar que essa fonte de dados solicitará a tabela VendTable.
4. Adicione uma fonte de dados do tipo **Campo calculado** para obter registros de vários fornecedores.
5. Nomeie a nova fonte de dados como **FilteredVendor** e configure-a para que contenha a expressão `FILTER(Vendor, OR(Vendor.AccountNum="US-101",Vendor.AccountNum="US-102"))`.
6. Adicione uma fonte de dados do tipo **Campo calculado** para obter as transações de todos os fornecedores filtrados.
7. Nomeie a nova fonte de dados como **FilteredVendorTrans** e configure-a para que contenha a expressão `ALLITEMS(FilteredVendor.'<Relations'.'VendTrans.VendTable_AccountNum')`.
8. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo**.

    ![Página Designer de mapeamento de modelo, botão Validar](./media/er-components-inspections-08a.png)

9. Observe que ocorre um aviso de validação. A mensagem recomenda que você use a função **ALLITEMSQUERY** em vez da **ALLITEMS** para a fonte de dados **FilteredVendorTrans**.

    ![Aviso de validação para usar a função ALLITEMSQUERY em vez da ALLITEMS no componente de mapeamento de modelo de ER na página Designer de mapeamento de modelo](./media/er-components-inspections-08b.png)

### <a name="automatic-resolution"></a>Resolução automática

Selecione **Corrigir** para substituir automaticamente a função **ALLITEMS** pela função **ALLITEMSQUERY** na expressão de todas as fontes de dados que aparecem na grade, na guia **Avisos**, para esse tipo de inspeção.

Como alternativa, você pode selecionar a linha para um único aviso na grade e depois **Corrigir selecionados**. Nesse caso, somente a expressão mencionada no aviso selecionado é alterada automaticamente na fonte de dados.

![Designer de mapeamento de modelo, selecione Corrigir selecionados](./media/er-components-inspections-08c.png)

### <a name="manual-resolution"></a>Resolução manual

Você pode ajustar manualmente as expressões de todas as fontes de dados mencionadas na grade de validação substituindo a função **ALLITEMS** pela função **ALLITEMSQUERY**.

## <a name="consideration-of-empty-list-cases"></a><a id="i9"></a>Consideração dos casos de lista vazia

Você pode configurar o componente de mapeamento de modelo ou formato de ER para obter o valor do campo de uma fonte de dados do tipo **Lista de registros**. O ER verifica se o seu design considera o caso em que uma fonte de dados chamada não contém registros (ou seja, está vazia) para evitar erros de runtime quando um valor é obtido a partir de um campo de um registro inexistente.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar os componentes de mapeamento de modelo e formato de ER e de modelo de dados de ER simultaneamente.
2. Na árvore do modelo de dados, adicione um item raiz chamado **Root3**.
3. Modifique o item **Root3** adicionando um item aninhado do tipo **Lista de registros**.
4. Nomeie o novo item aninhado **Vendor**.
5. Modifique o item **Vendor** da seguinte maneira:

    - Adicione um campo aninhado do tipo **Cadeia de caracteres** e nomeie-o como **Name**.
    - Adicione um campo aninhado do tipo **Cadeia de caracteres** e nomeie-o como **AccountNumber**.

    ![Adicionando campos aninhados na página de modelo de dados](./media/er-components-inspections-09a.png)

6. No painel de fontes de dados do mapeamento de modelo, adicione uma fonte de dados do tipo **Registros de tabela \\ do Dynamics 365 for Operations**.
7. Nomeie a nova fonte de dados como **Vendor**. No campo **Tabela**, selecione **VendTable** para especificar que essa fonte de dados solicitará a tabela VendTable.
8. Adicione uma fonte de dados do tipo **Parâmetro de entrada de usuário \\ geral** para procurar uma conta de fornecedor na caixa de diálogo do runtime.
9. Nomeie a nova fonte de dados como **RequestedAccountNum**. No campo **Rótulo**, digite o **número da conta do fornecedor**. No campo **Nome do tipo de dados de operações**, deixe o valor padrão, **Descrição**.
10. Adicione uma fonte de dados do tipo **Campo calculado** para filtrar um fornecedor que é consultado.
11. Nomeie a nova fonte de dados como **FilteredVendor** e configure-a para que contenha a expressão `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Associe os itens do modelo de dados às fontes de dados configuradas da seguinte maneira:

    - Associe **FilteredVendor** a **Vendor**.
    - Associe **FilteredVendor.AccountNum** a **Vendor.AccountNumber**.
    - Associe **FilteredVendor.'name()'** a **Vendor.Name**.

    ![Associando itens de modelo de dados na página Designer de mapeamento de modelo](./media/er-components-inspections-09b.png)

13. Na árvore de estrutura de formato, adicione os itens a seguir para gerar um documento de saída no formato XML que contém os detalhes do fornecedor:

    1. Adicione o elemento XML da raiz **Statement**.
    2. Para o elemento XML **Statement**, adicione o elemento XML **Party**.
    3. Para o elemento XML **Party**, adicione os seguintes atributos de XML aninhados:

        - Organização
        - AccountNum

14. Associe elementos de formato às fontes de dados fornecidas da seguinte maneira:

    - Associe o elemento de formato **Statement\\Party\\Name** ao campo de fonte de dados **model.Vendor.Name**.
    - Associe o elemento de formato **Statement\\Party\\Name** ao campo de fonte de dados **model.Vendor.Name**.

15. Selecione **Validar** para inspecionar o componente de formato editável na página **Designer de formato**.

    ![Validar os elementos de formato associados às fontes de dados na página Designer de formato](./media/er-components-inspections-09c.png)

16. Observe que ocorre um erro de validação. A mensagem informa que um erro poderá ocorrer para os componentes de formato **Statement\\Party\\Name** e **Statement\\Party\\AccountNum** no runtime se a lista de `model.Vendor` estiver vazia.

    ![Erro de validação que informa sobre um possível erro nos componentes de formato configurados](./media/er-components-inspections-09d.png)

A ilustração a seguir mostra o erro de runtime exibido se você ignorar o aviso, selecionar **Executar** para executar o formato e escolher o número de conta de um fornecedor inexistente. Como o fornecedor solicitado não existe, a lista de `model.Vendor` estará vazia (ou seja, não conterá registros).

![Erros de runtime, porque isso aconteceu durante a execução do mapeamento de formato](./media/er-components-inspections-09e.png)

### <a name="automatic-resolution"></a>Resolução automática

Para a linha selecionada na grade, na guia **Avisos**, você pode selecionar **Desvincular**. A associação que é apontada na coluna **Caminho** é automaticamente removida dos elementos de formato.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Você pode associar o elemento de formato **Statement\\Party\\Name** ao item de fonte de dados `model.Vendor`. No runtime, essa associação chama a fonte de dados `model.Vendor` primeiro. Quando o `model.Vendor` retorna uma lista de registros vazia, os elementos de formato aninhados não são executados. Portanto, nenhum aviso de validação ocorre para essa configuração de formato.

![Associar o elemento de formato ao item da fonte de dados na página Designer de formato](./media/er-components-inspections-09e.gif)

#### <a name="option-2"></a>Opção 2

Altere a associação do elemento de formato **Statement\\Party\\Name** de `model.Vendor.Name` para `FIRSTORNULL(model.Vendor).Name`. A associação atualizada condicionalmente converte o primeiro registro da fonte de dados `model.Vendor` do tipo **Lista de registros** para uma nova fonte de dados do tipo **Registro**. Essa nova fonte de dados contém o mesmo conjunto de campos.

- Se pelo menos um registro estiver disponível na fonte de dados `model.Vendor`, os campos desse registro serão preenchidos com os valores dos campos do primeiro registro da fonte de dados `model.Vendor`. Nesse caso, a associação atualizada retorna o nome do fornecedor.
- Caso contrário, cada campo do registro criado será preenchido com o valor padrão para o tipo de dados do campo. Nesse caso, a cadeia de caracteres em branco é retornada como o valor padrão do tipo de dados **Cadeia de caracteres**.

Portanto, nenhum aviso de validação ocorre no elemento de formato **Statement\\Party\\Name** quando ele está associado à expressão `FIRSTORNULL(model.Vendor).Name`.

![Alterar a associação resolve os avisos de validação na página Designer de formato](./media/er-components-inspections-09f.gif)

#### <a name="option-3"></a>Opção 3

Se você deseja especificar explicitamente os dados inseridos em um documento gerado quando a fonte de dados `model.Vendor` do tipo **Lista de registros** não retornar registros (texto **Não disponível** neste exemplo), altere a associação do elemento de formato **Statement\\Party\\Name** de `model.Vendor.Name` para `IF(NOT(ISEMPTY(model.Vendor)), model.Vendor.Name, "Not available")`. Você também pode usar a expressão `IF(COUNT(model.Vendor)=0, model.Vendor.Name, "Not available")`.

### <a name="additional-consideration"></a><a id="i9a"></a>Configuração adicional

A inspeção também avisa sobre outro problema em potencial. Por padrão, ao vincular os elementos de formato **Statement\\Party\\Name** e **Statement\\Party\\AccountNum** aos campos adequados da fonte de dados `model.Vendor` de tipo **Lista de registros**, essas associações serão executadas e receberão os valores dos campos apropriados do primeiro registro da fonte de dados `model.Vendor` se essa lista não estiver vazia.

Como você não associou o elemento de formato **Statement\\Party** à fonte de dados `model.Vendor`, o elemento **Statement\\Party** não será iterado para cada registro da fonte de dados `model.Vendor` durante a execução de formato. Em vez disso, se essa lista contiver vários registros, o documento gerado será preenchido com informações somente do primeiro registro da lista. Portanto, poderá ocorrer um problema se o formato se destinar a preencher um documento com informações sobre todos os fornecedores da fonte de dados `model.Vendor`. Para corrigir esse problema, associe o elemento **Statement\\Party** à fonte de dados `model.Vendor`.

## <a name="executability-of-an-expression-with-filter-function-caching"></a><a id="i10"></a>Capacidade de execução de uma expressão com função FILTER (armazenamento em cache)

Várias funções incorporadas de ER, incluindo [FILTER](er-functions-list-filter.md) e [ALLITEMSQUERY](er-functions-list-allitemsquery.md), são usadas para acessar tabelas de aplicativos, exibições ou entidades de dados, fazendo uma única chamada SQL para obter os dados necessários como uma lista de registros. Uma fonte de dados do tipo **Lista de registros** é usada como um argumento de cada uma dessas funções e especifica uma origem de aplicativo para a chamada. O ER verifica se uma chamada SQL direta pode ser estabelecida com uma fonte de dados referenciada em uma dessas funções. Se uma chamada direta não puder ser estabelecida porque uma fonte de dados foi marcada como [armazenada em cache](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace), ocorrerá um erro de validação no designer de mapeamento de modelo de ER. A mensagem recebida informa que a expressão de ER que contém uma dessas funções não pode ser executada no runtime.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar o componente de mapeamento de modelo de ER.
2. Adicione uma fonte de dados do tipo **Registros de tabela** \\ do Dynamics 365 for Operations.
3. Nomeie a nova fonte de dados como **Vendor**. No campo **Tabela**, selecione **VendTable** para especificar que essa fonte de dados solicitará a tabela VendTable.
4. Adicione uma fonte de dados do tipo **Parâmetro de entrada de usuário \\ geral** para procurar uma conta de fornecedor na caixa de diálogo do runtime.
5. Nomeie a nova fonte de dados como **RequestedAccountNum**. No campo **Rótulo**, digite o **número da conta do fornecedor**. No campo **Nome do tipo de dados de operações**, deixe o valor padrão, **Descrição**.
6. Adicione uma fonte de dados do tipo **Campo calculado** para filtrar um fornecedor que é consultado.
7. Nomeie a nova fonte de dados como **FilteredVendor** e configure-a para que contenha a expressão `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
8. Marque a fonte de dados **Vendor** como armazenada em cache.

    ![Configure o componente de mapeamento de modelo na página Designer de mapeamento de modelo](./media/er-components-inspections-10a.gif)

9. Selecione **Validar** para inspecionar o componente de mapeamento de modelo editável na página **Designer de mapeamento de modelo**.

    ![Validar a função Filter aplicada à fonte de dados Vendor armazenada em cache na página Designer de mapeamento de modelo](./media/er-components-inspections-10a.png)

10. Observe que ocorre um erro de validação. A mensagem informa que a função **FILTER** não pode ser aplicada à fonte de dados **Vendor** armazenada em cache.

A ilustração a seguir mostra o erro de runtime exibido se você ignorar o aviso e selecionar **Executar** para executar um formato.

![Erro de runtime que ocorre durante a execução do mapeamento de formato na página Designer de formato](./media/er-components-inspections-10b.png)

### <a name="automatic-resolution"></a>Resolução automática

Nenhuma opção para corrigir esse problema automaticamente está disponível.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Remova o sinalizador **Cache** da fonte de dados **Vendor**. A fonte de dados **FilteredVendor** se tornará executável, mas a fonte de dados **Vendor** referenciada na tabela VendTable será acessada toda vez que **FilteredVendor** for chamada.

#### <a name="option-2"></a>Opção 2

Altere a expressão da fonte de dados **FilteredVendor** de `FILTER(Vendor, Vendor.AccountNum="US-101")`para `WHERE(Vendor, Vendor.AccountNum="US-101")`. Nesse caso, a fonte de dados **Vendor** referenciada na tabela VendTable será acessada somente durante a primeira chamada da fonte **Vendor**. No entanto, a seleção de registros será feita na memória. Portanto, essa abordagem pode causar um baixo desempenho.

## <a name="missing-binding"></a><a id="i11"></a>Associação ausente

Quando você configura um componente de formato de ER, o modelo de dados de ER base é oferecido como uma fonte de dados padrão para o formato de ER. Quando o formato de ER configurado é executado, o [mapeamento de modelo padrão](er-country-dependent-model-mapping.md) para o modelo base é usado para preencher o modelo de dados com os dados do aplicativo. O Designer de formato de ER mostrará um aviso se você associar um elemento de formato a um item de modelo de dados que não esteja vinculado a nenhuma fonte de dados no mapeamento de modelo selecionado como o padrão para o formato editável. Esse tipo de associação não pode ser executado no runtime, pois o formato executado não pode preencher um elemento de associação com dados de aplicativo. Portanto, ocorre um erro no runtime.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar os componentes de mapeamento de modelo e formato de ER e de modelo de dados de ER simultaneamente.
2. Na árvore do modelo de dados, adicione um item raiz chamado **Root3**.
3. Modifique o item **Root3** adicionando um novo item aninhado do tipo **Lista de registros**.
4. Nomeie o novo item aninhado **Vendor**.
5. Modifique o item **Vendor** da seguinte maneira:

    - Adicione um campo aninhado do tipo **Cadeia de caracteres** e nomeie-o como **Name**.
    - Adicione um campo aninhado do tipo **Cadeia de caracteres** e nomeie-o como **AccountNumber**.

    ![Adicionar campos aninhados ao item de fornecedor na página Modelo de dados](./media/er-components-inspections-11a.png)

6. No painel de fontes de dados do mapeamento de modelo, adicione uma fonte de dados do tipo **Registros de tabela \\ do Dynamics 365 for Operations**.
7. Nomeie a nova fonte de dados como **Vendor**. No campo **Tabela**, selecione **VendTable** para especificar que essa fonte de dados solicitará a tabela VendTable.
8. Adicione uma fonte de dados do tipo **Parâmetro de entrada de usuário \\ geral** para consultar uma conta de fornecedor na caixa de diálogo do runtime.
9 Nomeie a nova fonte de dados como **RequestedAccountNum**. No campo **Rótulo**, digite o **número da conta do fornecedor**. No campo **Nome do tipo de dados de operações**, deixe o valor padrão, **Descrição**.
10. Adicione uma fonte de dados do tipo **Campo calculado** para filtrar um fornecedor que é consultado.
11. Nomeie a nova fonte de dados como **FilteredVendor** e configure-a para que contenha a expressão `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Associe os itens do modelo de dados às fontes de dados configuradas da seguinte maneira:

    - Associe **FilteredVendor** a **Vendor**.
    - Associe **FilteredVendor.AccountNum** a **Vendor.AccountNumber**.

    > [!NOTE]
    > O campo do modelo de dados **Vendor.Name** permanece não associado.

    ![Itens do modelo de dados associados a fontes de dados configuradas e um item de modo de dados na página Designer de mapeamento de modelo](./media/er-components-inspections-11b.png)

13. Na árvore de estrutura de formato, adicione os itens a seguir para gerar um documento de saída no formato XML que contém os detalhes dos fornecedores da consulta:

    1. Adicione o elemento XML da raiz **Statement**.
    2. Para o elemento XML **Statement**, adicione o elemento XML **Party**.
    3. Para o elemento XML **Party**, adicione os seguintes atributos de XML aninhados:

        - Organização
        - AccountNum

14. Associe os elementos de formato às fontes de dados fornecidas da seguinte maneira:

    - Associe o elemento de formato **Statement\\Party** ao item de fonte de dados `model.Vendor`.
    - Associe o elemento de formato **Statement\\Party\\Name** ao campo de fonte de dados **model.Vendor.Name**.
    - Associe o elemento de formato **Statement\\Party\\Name** ao campo de fonte de dados **model.Vendor.Name**.

15. Selecione **Validar** para inspecionar o componente de formato editável na página **Designer de formato**.

    ![Validando o componente de formato de ER na página Designer de formato](./media/er-components-inspections-11c.png)

16. Observe que ocorre um aviso de validação. A mensagem informa que o campo da fonte de dados **model.Vendor.Name** não está associado a nenhuma fonte de dados no mapeamento de modelo configurado para uso pelo formato. Portanto, o elemento de formato **Statement\\Party\\Name** pode não ser preenchido no runtime, e um erro de runtime pode ocorrer.

    ![Validando o componente de formato de ER na página Designer de formato](./media/er-components-inspections-11d.png)

A ilustração a seguir mostra o erro de runtime exibido se você ignorar o aviso e selecionar **Executar** para executar um formato.

![Executar o formato editável na página Designer de formato](./media/er-components-inspections-11e.png)

### <a name="automatic-resolution"></a>Resolução automática

Nenhuma opção para corrigir esse problema automaticamente está disponível.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Modifique o mapeamento de modelo configurado adicionando uma associação ao campo da fonte de dados **model.Vendor.Name**.

#### <a name="option-2"></a>Opção 2

Modifique o formato configurado removendo uma associação do elemento de formato **Statement\\Party\\Name**.

## <a name="not-linked-template"></a><a id="i12"></a>Modelo não vinculado

Quando você [configurar manualmente](er-fillable-excel.md#manual-entry) um componente de formato de ER para usar um modelo de modo a gerar um documento de saída, adicione o elemento **Excel\\File** de forma manual, inclua o modelo necessário como anexo do componente editável e selecione o anexo no elemento **Excel\\File** adicionado. Dessa forma, você indica que o elemento adicionado preencherá o modelo selecionado no runtime. Ao configurar uma versão de componente de formato no [status](general-electronic-reporting.md#component-versioning) **Rascunho**, você pode adicionar vários modelos ao componente editável e selecionar cada modelo no elemento **Excel\\File** para executar o formato de ER. Dessa forma, você pode ver como os modelos diferentes são preenchidos no runtime. Se você tem modelos que não estão selecionados em nenhum elemento **Excel\\File**, o Designer de formato de ER avisa que esses modelos serão excluídos da versão do componente de formato de ER editável quando o status for alterado de **Rascunho** para **Concluído**.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar o componente de formato de ER.
2. Na árvore de estrutura de formato, adicione o elemento **Excel\\File**.
3. Adicione um arquivo de pasta de trabalho do Excel, **A.xlsx**, como anexo para o elemento **Excel\\File** que você acabou de incluir. Use o tipo de documento configurado nos [parâmetros de ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) para especificar o armazenamento dos modelos de formato de ER.
4. Adicione outro arquivo de pasta de trabalho do Excel, **B.xlsx**, como anexo para o elemento **Excel\\File**. Use o mesmo tipo de documento usado para o arquivo de pasta de trabalho A.
5. No elemento **Excel\\File**, selecione arquivo de pasta de trabalho A.
6. Selecione **Validar** para inspecionar o componente de formato editável na página **Designer de formato**.

    ![Validando o componente de formato editável do arquivo de pasta de trabalho na página Designer de formato](./media/er-components-inspections-12a.gif)

7. Observe que ocorre um aviso de validação. A mensagem informa que o arquivo de pasta de trabalho **B.xlsx** não está vinculado a nenhum componente e será removido quando o status da versão da configuração mudar.

### <a name="automatic-resolution"></a>Resolução automática

Nenhuma opção para corrigir esse problema automaticamente está disponível.

### <a name="manual-resolution"></a>Resolução manual

Modifique o formato configurado removendo todos os modelos que não estão vinculados a nenhum elemento **Excel\\File**.

## <a name="not-synced-format"></a><a id="i13"></a>Formato não sincronizado

Quando você [configurar](er-fillable-excel.md) um componente de formato de ER para usar um modelo do Excel de modo a gerar um documento de saída, adicione o elemento **Excel\\File** de forma manual, inclua o modelo necessário como anexo do componente editável e selecione o anexo no elemento **Excel\\File** adicionado. Dessa forma, você indica que o elemento adicionado preencherá o modelo selecionado no runtime. Como o modelo do Excel adicionado foi criado externamente, o formato de ER editável pode conter nomes do Excel que estão faltando no modelo incluído. O Designer de formato de ER avisa sobre as inconsistências entre as propriedades dos elementos de formato de ER que referenciam nomes não incluídos no modelo do Excel adicionado.

As etapas a seguir mostram como esse problema pode ocorrer.

1. Comece a configurar o componente de formato de ER.
2. Na árvore de estrutura de formato, adicione do elemento **Report** do **Excel\\File**.
3. Adicione um arquivo de pasta de trabalho do Excel, **A.xlsx**, como anexo para o elemento **Excel\\File** que você acabou de incluir. Use o tipo de documento configurado nos [parâmetros de ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) para especificar o armazenamento dos modelos de formato de ER.

    > [!IMPORTANT]
    > Verifique se a pasta de trabalho do Excel adicionada não contém o nome **ReportTitle**.

4. Adicione o elemento **Title** do **Excel\\Cell** a seguir como elemento aninhado do elemento **Report**. No campo **Intervalo do Excel**, insira **ReportTitle**.
5. Selecione **Validar** para inspecionar o componente de formato editável na página **Designer de formato**.

    ![Validar elementos e campos aninhados na página Designer de formato](./media/er-components-inspections-13a.png)

6. Observe que ocorre um aviso de validação. A mensagem informa que o nome **ReportTitle** não existe na planilha **Sheet1** do modelo do Excel que você está usando.

    ![Aviso de validação de que o nome ReportTitle não existe na Sheet1 do modelo do Excel](./media/er-components-inspections-13b.png)

### <a name="automatic-resolution"></a>Resolução automática

Nenhuma opção para corrigir esse problema automaticamente está disponível.

### <a name="manual-resolution"></a>Resolução manual

#### <a name="option-1"></a>Opção 1

Modifique o formato configurado removendo todos os elementos que referenciam nomes do Excel que estão faltando no modelo.

#### <a name="option-2"></a>Opção 2

[Atualize](er-fillable-excel.md#template-import) o formato de ER editável importando um modelo do Excel. A estrutura do formato de ER editável será [sincronizado](modify-electronic-reporting-format-reapply-excel-template.md) com a estrutura do modelo do Excel importado.

### <a name="additional-consideration"></a>Configuração adicional

Para saber como a estrutura de formato pode ser sincronizada com um modelo de ER no editor de modelos do [Gerenciamento de documentos comerciais ](er-business-document-management.md), consulte [Atualizar a estrutura de um modelo de documento comercial](er-bdm-update-structure.md).

## <a name="additional-resources"></a>Recursos adicionais

[Função de ER ALLITEMS](er-functions-list-allitems.md)

[Função de ER ALLITEMSQUERY](er-functions-list-allitemsquery.md)

[Função de ER INT64VALUE](er-functions-conversion-int64value.md)

[Função de ER INTVALUE](er-functions-conversion-intvalue.md)

[Função de ER FILTER](er-functions-list-filter.md)

[Função de ER WHERE](er-functions-list-where.md)

[Usar as fontes de dados JOIN para obter dados de várias tabelas de aplicativos em mapeamentos de modelo de ER](er-join-data-sources.md)

[Rastrear a execução de formatos de ER para solucionar problemas de desempenho](trace-execution-er-troubleshoot-perf.md)

[Visão geral de gerenciamento de documentos comerciais](er-business-document-management.md)
