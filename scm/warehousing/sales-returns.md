---
title: "Devoluções de vendas"
description: "Este tópico fornece informações sobre o processo para ordens de devolução. Ele Inclui informações sobre devoluções do cliente e o seu efeito na avaliação de custo e nas quantidades de estoque disponíveis."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: b66bf79413ad21f12f789eabafe8413af3f58c9c
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017


---

# <a name="sales-returns"></a>Devoluções de vendas

[!include[banner](../includes/banner.md)]


Este tópico fornece informações sobre o processo para ordens de devolução. Ele Inclui informações sobre devoluções do cliente e o seu efeito na avaliação de custo e nas quantidades de estoque disponíveis.

Os clientes podem devolver itens por diversos motivos. Por exemplo, um item pode apresentar defeito ou pode não ter atingido as expectativas do cliente. O processo de devolução se inicia quando um cliente emite uma solicitação para devolução de um item. Assim que a solicitação do cliente é recebida, uma ordem de devolução é criada no Microsoft Dynamics 365 for Finance and Operations.

## <a name="return-order-process"></a>Processo de ordem de devolução
A ilustração a seguir exibe um resumo do processo de ordem de devolução.  

[![salesreturns01](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Existem dois tipos de processos de ordens de devolução: devolução física e apenas crédito.

-   **Devolução física** – A ordem de devolução autoriza a devolução física de produtos.
-   **Apenas crédito** – A ordem de devolução autoriza um crédito ao cliente mas não exige que o cliente devolva os produtos fisicamente.

### <a name="physical-return-order-process"></a>Processo de ordem de devolução física

1.  **Criar uma ordem de devolução.** Documente formalmente a autorização para que o cliente devolva qualquer produto defeituoso ou indesejado. A ordem de devolução não exige que a empresa aceite os produtos devolvidos ou forneça um crédito ao cliente. Se a devolução for aceita, você pode autorizar o envio de um item de reposição antes que o item defeituoso seja devolvido.
2.  **Chegada ao depósito para inspeção.** Conclua uma inspeção e validação inicial sobre o documento da ordem de devolução. A ordem de devolução também oferece suporte à quarentena de itens devolvidos para inspeção e controle de qualidade adicionais.
3.  **Determinar disposição.** Finalize o processo de inspeção e decida o que deve ser feito com os produtos devolvidos. Como parte dessa etapa, decida se você irá creditar o cliente, rejeitar ou aceitar a devolução do produto, descartar o produto, e então envie um produto de reposição ao cliente.
4.  **Gerar uma guia de remessa.** Crie uma guia de remessa, e confirme a decisão de disposição tomada na etapa 3. Finalize o processo de logística.
5.  **Gerar uma fatura.** Feche a ordem de devolução.

### <a name="credit-only-process"></a>Processo para crédito apenas

1.  **Criar uma ordem de devolução.** Documente formalmente a autorização para que o cliente receba um crédito sem devolver os produtos defeituosos ou indesejados. O código de disposição **Apenas crédito** autoriza a decisão de creditar um cliente sem que ocorra devolução física.
2.  **Gerar uma fatura.** Gere a nota de crédito, e em seguida feche a ordem de devolução.

## <a name="return-material-authorization"></a>Autorização de Devolução de Mercadoria
O processamento da Autorização de Devolução de Mercadoria (ADM) se constrói pela funcionalidade da ordem de venda. Uma ADM é registrada como uma ordem de devolução, criada como uma ordem de venda, e pode ter outra ordem de venda associada à ela, chamada de ordem de substituição. Ambas as ordens de venda são vinculadas ao número ADM de origem.

-   **Ordem de devolução** – Para registrar uma ADM, você cria uma ordem de devolução, que é uma ordem de venda do tipo **Pedido devolvido.** Todas as alterações feitas às informações da ADM são atualizadas automaticamente na ordem de venda. Enquanto a ordem de devolução possuir o status **Aberta**, ela não aparecerá na lista de ordens de venda. Você utiliza a ADM para lidar com a chegada e o recebimento de itens devolvidos, bem como para autorizar uma ação de disposição de crédito apenas (consulte a seção **Códigos de disposição e ações de disposição**). Todos os demais processos complementares devem ser tratados na ordem de venda.
-   **Ordem de substituição** – Quando uma ordem de substituição deve ser enviada ao cliente, a ADM pode incluir uma segunda ordem de venda associada. Você pode criar manualmente a ordem de substituição para a ADM, facilitando o envio imediato. Alternativamente, a ordem de substituição pode ser criada automaticamente assim que a chegada, inspeção e recebimento forem concluídos, para o item da ADM que possui um código de disposição que indica substituição. A ordem de substituição possui a mesma funcionalidade associada a uma ordem de venda. Por exemplo, você pode usá-la para configurar um produto personalizado como item de substituição, criar uma ordem de produção para consertar um item devolvido, criar uma ordem de compra para entrega direta para enviar o substituto a partir de um fornecedor, ou auxiliar outros propósitos.

## <a name="create-a-return-order"></a>Criar uma ordem de devolução
O processo da ordem de devolução inicia quando um cliente entra em contato com sua organização para devolver um produto defeituoso ou indesejado e/ou ser creditado. Depois que sua organização aceitar a devolução, ela é documentada por uma ordem de devolução. Essa ordem de devolução se torna o foco do processamento interno do produto devolvido. A ilustração a seguir mostra o procedimento para criação de uma ordem de devolução.  

[![Procedimento para criação de uma ordem de devolução](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Criar um cabeçalho de ordem de devolução

Ao criar uma ordem de devolução, as informações da tabela a seguir devem estar inclusas.

| Campo              | descrição                                              | Comentários                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Conta de cliente   | Uma referência à tabela Clientes                       | Você deve fornecer uma conta de cliente existente.                                                                                                                                                                                                                                                                                                  |
| Endereço de entrega   | O endereço para o qual o item é devolvido                 | Por padrão, é usado o endereço da organização. Se um depósito específico for selecionado no cabeçalho, o endereço de entrega será alterado para o endereço de entrega do depósito. Você pode alterar esse endereço na página **Detalhes da ordem de devolução**.                                                                                                  |
| Local/depósito     | O local ou depósito que recebe o produto devolvido | O endereço de entrega da ordem de devolução é determinado com base no endereço de entrega do local ou depósito.                                                                                                                                                                                                                                 |
| Número de ADM         | A ID atribuída à ordem de devolução              | O número ADM é usado como uma chave alternativa ao longo do processo da ordem de devolução. O número ADM atribuído é baseado na sequência numérica da ADM, configurada na página **Parâmetros de contas a receber**.                                                                                                                              |
| Prazo final           | A última data em que um item pode ser devolvido               | O valor padrão é calculado como a data atual mais o período de validade. Por exemplo, se uma devolução for válida por 90 dias a partir da data em que a ordem de devolução foi criada, e a ordem foi criada em 1º de Maio, o valor no campo é **30-Julho**. O período de validade é definido na página **Parâmetros de contas a receber**. |
| Código de motivo de devolução | O motivo do cliente para devolução do produto          | O código do motivo é selecionado na lista de códigos de motivos definidos pelo usuário. Você pode atualizar esse campo a qualquer momento.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Criar linhas da ordem de devolução

Após concluir o cabeçalho de devolução, você pode criar linhas de devolução usando um dos seguintes métodos:

-   Inserir manualmente os detalhes do item, a quantidade, e outras informações para cada linha de devolução.
-   Criar uma linha de devolução usando a função **Encontrar ordem de venda**. Recomenda-se usar esta função ao criar uma ordem de devolução. A função **Encontrar ordem de venda** estabelece uma referência a partir da linha de devolução para a linha faturada da ordem de venda, e recupera detalhes da linha como número do item, quantidade, preço, desconto e valores de custo, a partir da linha de venda. A referência ajuda a garantir que, quando um produto for devolvido à empresa, ele será avaliado com o mesmo custo unitário com o qual foi vendido. A referência também verifica se ordens de devolução não serão criadas para quantidades que excedam a quantidade vendida na fatura.

**Observação:** Linhas de devolução que possuem uma referência a uma ordem de venda são tratadas como correções, ou inversões, da venda. Para obter mais informações, consulte a seção "Lançar no livro razão", posteriormente neste tópico.

### <a name="charges"></a>Encargos

Taxas e encargos podem ser adicionados à ordem de devolução utilizando um ou mais métodos a seguir:

-   Você pode adicionar encargos manualmente ao cabeçalho da ordem de devolução, à linha da ordem de devolução, ou ambos.
-   Encargos podem ser adicionados automaticamente ao cabeçalho da ordem de devolução em função do código de motivo de devolução.
-   Encargos podem ser adicionados automaticamente à linha da ordem de devolução, com base no código de disposição da linha.

Encargos são adicionados automaticamente depois que um código de motivo de devolução ou código de disposição for atribuído à linha. Se o código de motivo é alterado posteriormente, o encargo existente não será removido, mas um novo encargo pode ser adicionado, com base no novo código de motivo. Ao adicionar encargos às linhas da ordem de devolução, encargos calculados como uma porcentagem da linha ou do valor da ordem se tornam negativos quando a linha ou linha da ordem for negativa, a menos que a porcentagem também seja um número negativo. Um encargo que tem um valor negativo representa um crédito ao cliente.

### <a name="return-reason-codes"></a>Códigos de motivo de devolução

Ao aplicar códigos de motivo às devoluções, você pode ajudar a tornar os padrões de devoluções mais fáceis de analisar. Os códigos de motivo fornecem informações sobre o motivo pelo qual um cliente deseja devolver itens. Algumas organizações possuem muitos códigos de motivo. Essa organização pode agrupar os códigos de motivo em grupos de códigos para proporcionar uma melhor visão geral e comunicação acumulada.

### <a name="disposition-codes-and-disposition-actions"></a>Códigos de disposição e ações de disposição

Uma etapa importante no processo de ordem de devolução é a atribuição de um código de disposição à linha da ordem de devolução como parte do registro de chegada. O código de disposição determina as seguintes informações:

-   **As implicações financeiras** – O cliente deve ser creditado pelos itens devolvidos e os encargos devem ser adicionados à linha da ordem de devolução?
-   **A disposição do item devolvido** – O item pode ser adicionado de volta ao estoque, deve ser descartado ou deve ser devolvido ao cliente?
-   **A logística do item devolvido** – Deve-se enviar um item de substituição ao cliente?

Além de determinar como os bens devolvidos são eliminados, códigos de disposição podem fazer com que encargos sejam aplicados à linha de devolução. Eles também podem ser usados para agrupar devoluções para análise estatística. Códigos de disposição são definidos como parte da preparação das ordens de devolução. No entanto, cada código de disposição deve fazer referência a uma das ações de disposição integradas. A tabela a seguir lista os códigos de disposição integrados e suas ações. **Importante:** Se um item não deve ser devolvido, mas o cliente ainda deve ser creditado, atribua o código de disposição **Apenas crédito** à linha de devolução.

<table>
<thead>
<tr class="header">
<th>Código de disposição</th>
<th>Implicações financeiras</th>
<th>Implicações para a logística</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Somente crédito</td>
<td><ul>
<li>O cliente é creditado o preço de venda menos qualquer taxa ou encargo.</li>
<li>A perda por descartar um item é lançada no livro razão.</li>
</ul></td>
<td>O item não deve ser devolvido. Essa ação de disposição é usada nos seguintes casos:
<ul>
<li>Existe confiança suficiente entre as partes envolvidas.</li>
<li>O custo de devolução do item defeituoso é inviável.</li>
<li>Os itens não podem ser colocados de volta no estoque. Devido a outras condições, a devolução física não é necessária.</li>
</ul></td>
</tr>
<tr class="even">
<td>Crédito</td>
<td><ul>
<li>O cliente é creditado o preço de venda menos qualquer taxa ou encargo.</li>
<li>O valor de estoque é aumentado pelo custo do item devolvido.</li>
</ul></td>
<td>O item é devolvido e adicionado de volta ao estoque.</td>
</tr>
<tr class="odd">
<td>Substituir e creditar</td>
<td><ul>
<li>O cliente é creditado o preço de venda menos qualquer taxa ou encargo.</li>
<li>O valor do estoque é aumentado pelo custo do item devolvido.</li>
<li>Uma ordem de venda separada para substituição é criada e tratada separadamente.</li>
</ul></td>
<td>O item é devolvido e adicionado de volta ao estoque.</td>
</tr>
<tr class="even">
<td>Substituir e sucata</td>
<td><ul>
<li>O cliente é creditado o valor de venda, menos qualquer taxa ou encargo.</li>
<li>A perda por descartar um item é lançada no livro razão.</li>
<li>Uma ordem de venda separada para substituição é criada e tratada separadamente.</li>
</ul></td>
<td>O item é devolvido e descartado.</td>
</tr>
<tr class="odd">
<td>Devolver ao cliente</td>
<td>Nenhum, exceto qualquer taxa ou encargo.</td>
<td>O item é devolvido mas é enviado de volta para o cliente após a inspeção. Essa ação de disposição pode ser usada se o item foi danificado propositalmente, ou se a garantia foi anulada.</td>
</tr>
<tr class="even">
<td>Sucata</td>
<td><ul>
<li>O cliente é creditado o preço de venda menos qualquer taxa ou encargo.</li>
<li>A perda por descartar um item é lançada no livro razão.</li>
</ul></td>
<td>O item é devolvido ou descartado.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Chegada ao depósito para inspeção
Antes que seja possível retornar itens devolvidos fisicamente ao estoque com a postagem de uma guia de remessa, os itens devem passar por registro de chegada e uma inspeção opcional. A ilustração a seguir exibe um resumo do processo de entrada. As seções a seguir descrevem cada etapa mostrada na ilustração.  

[![processo de entrada](./media/salesreturn03.png)](./media/salesreturn03.png)  

O processo possui várias outras variações que não são abordadas nesse tópico. Estas são algumas das variações:

-   Não use a lista **Resumo de entrada** para criar um Diário de entrada. Em vez disso, crie manualmente o Diário de entrada. Ordens de devolução terão **Ordem de venda** como referência.
-   Se estiver usando o Gerenciamento de depósito, crie o transporte de paletes. A linha de devolução terá o status **Chegou** durante o transporte de paletes.
-   Registre a chegada do item devolvido diretamente a partir da linha da ordem de devolução, utilizando a função **Registro**.

Durante o processo de entrada, devoluções são integradas ao processo geral de entradas ao depósito. O processo de entrada também oferece suporte à criação de ordens de quarentena para itens devolvidos que devem ser submetidos a uma inspeção separada.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identificar produtos na lista de Resumo de entradas.

A página **Resumo de entradas** lista todas as próximas chegadas planejadas. **Observação:** Entradas de ordens de devolução devem ser processadas separadamente em relação a outros tipos de transações de entrada. Após identificar uma encomenda na página **Resumo de entradas** (por exemplo, utilizando o documento ADM acompanhante), no Painel de Ação, clique em **Iniciar entrada** para criar e inicializar um Diário de entrada que corresponda com a entrada.

### <a name="edit-the-arrival-journal"></a>Editar o Diário de entrada

Ao definir a opção **Gerenciamento de quarentena** como **Sim**, você pode criar uma ordem de quarentena para a linha de devolução. Se uma linha foi enviada para quarentena para inspeção, não é possível especificar um código de disposição. **Observação:** Se você definir a opção **Gerenciamento de quarentena** como **Sim** no grupo de modelo de estoque do item, a opção **Gerenciamento de quarentena** na página **Linhas do diário** será marcada para a linha do Diário de entradas e não poderá ser alterada. Se a linha é enviada para quarentena, você deve especificar o depósito de quarentena apropriado. Se a linha de entrada não for enviada para inspeção, o auxiliar de entrada do depósito deve especificar o código de disposição diretamente na linha do Diário de entrada e depois publicar o diário. Se o mesmo código de disposição não deve ser atribuído a toda a quantidade da linha de devolução, ou se a quantidade total da linha não foi recebida, você deve dividir a linha. Ao dividir uma linha do Diário de entrada, você também divide a linha de devolução (**SalesLine**) e cria uma nova ID de lote. Você pode dividir a linha reduzindo a quantidade da linha do Diário de entrada. Quando o diário é publicado, uma nova linha de devolução é criada com o status **Esperado** para a quantidade restante. Você também pode dividir a linha clicando em **Funções** &gt; **Dividir**.

### <a name="process-the-quarantine-order"></a>Processar a ordem de quarentena

Se os produtos devolvidos são enviados para inspeção no depósito de quarentena, qualquer processamento adicional é concluído na ordem de quarentena. Uma ordem de quarentena é criada para cada linha de entrada que é enviada para quarentena. O código de disposição indica o resultado do processo de inspeção. Você pode dividir uma ordem de quarentena, do mesmo jeito que pode dividir o Diário de entrada. Se você dividir a ordem de quarentena, você irá causar uma divisão correspondente na linha de devolução. Depois que o código de disposição foi inserido, complete a ordem de quarentena usando a função **Terminar** ou a função **Relatar como concluído**. Se você selecionar **Relatar como concluído**, uma nova entrada é criada no depósito designado. Você pode então processar essa entrada utilizando a página **Resumo de entradas**. Se a entrada se origina de uma ordem de quarentena, você não poderá alterar o código de disposição atribuído durante a inspeção. Se você completar a ordem de quarentena usando a função **Terminar**, o lote é registrado automaticamente. Ocasionalmente, um item pode ser enviado da quarentena de volta para o departamento de Envio e recebimento. Por exemplo, o inspetor da quarentena pode não saber onde armazenar o item no estoque. Nesse caso, a guia de remessa correspondente deve ser atualizada para registrar e agir corretamente sobre o código de disposição especificado devido à quarentena. A notificação de recebimento pode ser enviada ao cliente quando a linha de devolução for registrada. O relatório **Notificação de devolução** é parecido com o documento da ordem de devolução. O relatório **Notificação de devolução** não é lançado ao diário, ou registrado no sistema, além de não ser uma etapa necessária no processo de ordem de devolução.

## <a name="replace-a-product"></a>Substituir um produto
Existem dois métodos para gerenciar a substituição de produtos:

-   **Substituição imediata** – Substitua um produto antes que o produto devolvido seja recebido do cliente.
-   **Substituição por código de disposição** – Crie automaticamente uma nova linha da ordem de substituição.

### <a name="up-front-replacement"></a>Substituição adiantada

Na substituição imediata, o item de substituição pode ser entregue ao cliente antes que o item seja devolvido. Este método é útil se, por exemplo, o item é uma peça de uma máquina que não pode ser removida a menos que uma peça extra esteja disponível para substituí-la, ou se você apenas deseja que o seu cliente tenha o produto o quanto antes. A ordem de substituição imediata é uma ordem de venda independente. As informações do cabeçalho são iniciadas pelo cliente, e as informações da linha são iniciadas pela ordem de devolução. Você pode editar, processar e excluir a ordem de substituição de forma independente em relação à ordem de devolução. Ao excluir uma ordem de substituição, você receberá uma mensagem dizendo que a ordem foi criada como uma ordem de substituição. A ilustração a seguir mostra o processo para a substituição imediata.  

[![Processo de substituição imediata](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)  

A ordem de devolução contém uma referência à ordem de substituição. Se uma ordem de substituição imediata é criada para uma ordem de devolução antes que o item defeituoso seja devolvido, você não poderá selecionar códigos de disposição para substituição depois que o item defeituoso for devolvido.

### <a name="replacement-by-disposition-code"></a>Substituição por código de disposição

Se você enviar um item de substituição para o cliente, e utilizar a ação de disposição **Substituir e descartar** ou a ação **Substituir e creditar** na ordem de devolução, utilize o processo exibido na ilustração a seguir.  

[![Processo de substituição quando um código de disposição é utilizado](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)  

O item substituto será entregue usando uma ordem de venda independente, a ordem de venda de substituição. Essa ordem de venda é criada quando a guia de remessa para a ordem de devolução é gerada. O cabeçalho da ordem usa informações do cliente referenciadas no cabeçalho da ordem de devolução. As informações da linha são coletadas das informações inseridas na página **Item de substituição**. A página **Item de substituição** deve ser preenchida para linhas que possuem ações de disposição iniciadas pela palavra "substituir". No entanto, nem a quantidade nem a identidade do item de substituição é validada ou limitada. Esse comportamento permite casos em que o cliente deseja o mesmo item mas com uma configuração ou um tamanho diferente, além de casos em que os clientes desejam um item completamente diferente. Por padrão, um item idêntico é inserido na página **Item de substituição**. No entanto, você pode selecionar um item diferente, desde que a função tenha sido configurada. **Observação:** Você pode editar e excluir a ordem de venda de substituição após sua criação.

## <a name="generate-a-packing-slip"></a>Gerar uma guia de remessa
Antes que os itens devolvidos possam ser recebidos no estoque, você deve atualizar a guia de remessa para a ordem a qual os itens pertencem. Assim como o processo de atualização da fatura é a atualização da transação financeira, o processo de atualização da guia de remessa é a atualização física do registro do estoque. Em outras palavras, esse processo confirma as alterações do estoque. No caso de devoluções, as etapas atribuídas à ação de disposição são implementadas durante a atualização da guia de remessa. Ao gerar a guia de remessa, os seguintes eventos ocorrem:

-   No depósito, o processo padrão é usado para executar um recebimento físico. Publicações no livro razão são geradas se o grupo de modelo do estoque (**Lançar estoque físico**) e os parâmetros de Contas a receber (**Lançar guia de remessa no livro razão**) forem definidos de forma apropriada.
-   Os itens que foram marcados com uma ação de disposição que contém a palavra "descartar" são descartados, e a perda do estoque é publicada o livro razão.
-   Os itens que foram marcados com a ação de disposição **Devolver ao cliente** são recebidos e enviados ao cliente. Esses itens não afetam o estoque de maneira líquida.
-   Uma ordem de venda de substituição é criada. Essa ordem de venda é baseada em informações da página **Item de substituição**.

Você pode gerar a guia de remessa apenas para linhas com o status de devolução **Registrada**, e apenas para a quantidade total da linha de devolução. Se várias linhas da ordem de devolução possuem o status **Registrada**, você pode gerar a guia de remessa para um subconjunto de linhas, excluindo as outras linhas pela página **Lançar guia de remessa**. As devoluções parciais são definidas em termos das linhas da ordem de devolução, e não em termos dos envios da ordem de devolução. Portanto, se você receber a quantidade total indicada em uma linha da ordem de devolução, mas não receber nada das outras linhas, a entrega não é considerada uma entrega parcial. No entanto, se uma linha da ordem de devolução determina que 10 unidades de um item sejam devolvidos, mas você recebe apenas quatro unidades, a entrega é considerada uma entrega parcial. Se nem todos os itens de devolução esperados foram recebidos, você pode deixar a remessa de lado e esperar pela chegada da quantidade devolvida restante. Alternativamente, você pode registrar e lançar a quantidade parcial. Como parte do processo de lançamento das guias de remessa, é possível associar o número de referência da guia de remessa a partir dos documentos de envio do cliente com as linhas da ordem. Essa associação é opcional e serve somente como referência. Ela não cria nenhuma atualização transacional. Em geral, você pode pular o processo de guia de remessa e ir direto para o faturamento. Nesse caso, as etapas que você executaria durante a geração da guia de remessa são realizadas durante o faturamento.

## <a name="generate-an-invoice"></a>Gerar uma fatura
Embora a página **Ordem de devolução** contenha as informações e ações necessárias para tratar os aspectos logísticos especiais da ordem de devolução, você deve usar a página **Ordem de venda** para concluir o processo de faturamento. Sua organização poderá então faturar ordens de devolução e de venda ao mesmo tempo, e a mesma pessoa pode concluir o processo de faturamento, como solicitado. Para visualizar a ordem de devolução na página **Ordem de venda**, clique no link do número da ordem de venda para abrir a ordem de venda associada. Você também pode encontrar a ordem de devolução na página **Todas as ordens de venda**. Ordens de devolução são ordens de venda que possuem o tipo de ordem **Ordem devolvida**.

### <a name="credit-correction"></a>Correção de crédito

Como parte do processo de faturamento, verifique se todos os encargos diversos estão corretos. Para fazer com que os lançamentos no livro razão se tornem correções (Storno), considere usar a opção **Correção de crédito** na aba **Outros** da página **Lançar fatura** quando lançar a nota de crédito/fatura. **Observação:** Por padrão, a opção **Correção de crédito** é ativada se a opção **Nota de crédito como correção** na página **Parâmetros de contas a receber** foi habilitada. No entanto, recomendamos que você não lance devoluções com o Storno.

## <a name="create-intercompany-return-orders"></a>Criar ordens de devolução intercompanhia
Ordens de devolução podem ser concluídas entre duas empresas dentro da organização. Os seguintes cenários são suportados:

-   Devoluções intercompanhia simples entre duas empresas que participam de uma relação intercompanhia
-   Uma cadeia intercompanhia que é estabelecida quando uma ordem de devolução do cliente é criada na empresa de venda
-   Uma cadeia intercompanhia que é estabelecida quando uma ordem de devolução do fornecedor é criada na empresa de compra
-   Devoluções de remessa com entrega direta entre um cliente externo e duas empresas que participam de uma relação intercompanhia

### <a name="setup"></a>Instalação

A ilustração a seguir mostra a configuração mínima necessária para que duas empresas participem de uma relação intercompanhia e tirem proveito do comércio intercompanhia.  

[![Configuração mínima](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

No cenário seguinte, CompBuy é a empresa compradora, e CompSell é a empresa vendedora. Normalmente, a empresa vendedora envia mercadorias para a empresa compradora ou, em cenários de remessa de entrega direta, diretamente para o cliente final. Na CompBuy, o fornecedor IC\_CompSell é definido como uma empresa intercompanhia associado à empresa CompSell. Ao mesmo tempo, na CompSell, o cliente IC\_CompBuy é definido como uma empresa intercompanhia associado à empresa CompBuy. Os detalhes apropriados da política de ações e os mapeamentos de valor devem ser definidos nas duas empresas. Em um cenário de remessa de entrega direta, uma ordem de devolução intercompanhia, que também é uma ordem de venda intercompanhia, é criada na empresa vendedora. O número ADM da ordem de devolução intercompanhia pode ser obtido da sequência numérica da ADM na CompSell, ou pode ser copiado do número ADM atribuído à ordem de devolução original na CompBuy. As configurações do número ADM na política de ações **PurchaseRequisition** na CompBuy determina essas ações. Se o número ADM é sincronizado, você deve planejar atenuar o risco de conflitos numéricos se as duas empresas usam a mesma sequência numérica.

### <a name="simple-intercompany-returns"></a>Devoluções intercompanhia simples

Esse cenário envolve duas empresas na mesma organização, conforme mostrado na ilustração a seguir.  

[![Devolução intercompanhia simples](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)  

A cadeia de ordem pode ser estabelecida quando uma devolução de fornecedor é criada na empresa compradora ou quando uma ordem de devolução do cliente é criada na empresa vendedora. O Finanças e Operações cria a ordem correspondente na outra empresa e garante que as informações do cabeçalho e da linha na ordem de devolução do fornecedor reflitam as configurações na ordem de devolução do cliente. A ordem de devolução estabelecida pode tanto incluir como excluir a referência (**Encontrar ordem de venda**) a uma fatura de cliente existente. As guias de remessa e as faturas das duas ordens podem ser processadas individualmente. Por exemplo, não é necessário gerar uma guia de remessa para a ordem de devolução do fornecedor antes de gerar a guia de remessa para a ordem de devolução do cliente.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Devoluções de remessa de entrega direta entre três participantes

Esse cenário pode ser estabelecido se uma venda anterior do tipo **Entrega direta** foi concluída, e se existe uma fatura contra o cliente na empresa que interage com o cliente. Na ilustração seguinte, a empresa CompBuy vendeu e faturou produtos anteriormente ao cliente Extern. Os produtos foram enviados diretamente da empresa CompSell ao cliente através de uma cadeia de ordens intercompanhia.  

[![Devoluções de remessa de entrega direta entre três participantes](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)  

Se o cliente Extern deseja devolver os produtos, uma ordem de devolução (RMA02) será criada para o cliente na empresa CompBuy. Para estabelecer a cadeia intercompanhia, a ordem de devolução deve ser marcada para entrega direta. Quando você usa a função **Encontrar ordens de venda** para selecionar a fatura do cliente a ser devolvida, é estabelecida uma cadeia de ordem intercompanhia que consiste nos seguintes documentos:

-   **Ordem de devolução original:** RMA02 (empresa CompBuy)
-   **Ordem de compra:** PO02 (empresa CompBuy)
-   **Ordem de devolução intercompanhia:** RMA\_00032 (empresa CompSell)

Depois que a cadeia de entrega direta intercompanhia é criada, todo manuseio e processamento físico de devoluções deve ocorrer no contexto da ordem de devolução intercompanhia, RMA\_00032 na empresa CompSell. Os produtos não podem ser recebidos na empresa CompBuy. Quando um código de disposição é atribuído à ordem de devolução intercompanhia, ele é sincronizado com a ordem de devolução original para permitir o faturamento adequado da ordem original.

## <a name="post-to-the-ledger"></a>Lançar no livro razão
Os lançamentos no livro razão, gerados quando a ordem de devolução é faturada, são influenciados por algumas configurações e parâmetros importantes:

-   **Preço de custo da devolução** – Para modelos de estoque diferentes do **Custo padrão**, o parâmetro **Preço de custo da devolução** determina o custo do item quando ele é aceito de volta no estoque ou descartado. Para calcular uma previsão de estoque correta, é importante definir o parâmetro **Preço de custo da devolução** corretamente. Se você usar a função **Encontrar ordem de venda** para criar uma linha da ordem de devolução com uma referência a uma fatura de cliente, o valor **Preço de custo da devolução** é igual ao preço de custo do item vendido. Caso contrário, o preço de custo vem da configuração do item ou pode ser inserido manualmente.
-   **Correção de crédito/Storno** – O parâmetro **Correção de crédito** na página **Lançando fatura** determina se os lançamentos devem ser registrados como entradas positivas (DR/CR) ou como entradas corretoras, negativas.

Nos exemplos a seguir, o preço de custo da devolução é representado como **Preço de custo da fatura**.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Exemplo 1: A ordem de devolução não faz referência a uma fatura de cliente

A ordem de devolução não faz referência a uma fatura de cliente. O item devolvido é creditado. O parâmetro **Correção de crédito** não é selecionado quando a fatura da ordem de devolução, ou nota de crédito, é gerada.  

[![Ordem de devolução não faz referência a uma fatura de cliente](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)  

**Observação:** O preço mestre do item é usado como valor padrão para o parâmetro **Preço de custo da devolução**. O preço padrão difere do preço de custo no momento da saída de estoque. Portanto, a implicação é que uma perda de 3 foi sofrida. Além disso, a ordem de devolução não inclui o desconto dado ao cliente na ordem de compra. Portanto, ocorre um crédito em excesso.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Exemplo 2: Correção de crédito está selecionada para a ordem de devolução

O exemplo 2 é igual ao exemplo 1, mas o parâmetro **Correção de crédito** é selecionado quando a fatura da ordem de devolução é gerada.  

[![Ordem de devolução onde a correção de crédito está selecionada ](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)  

**Observação:** Os lançamentos no livro razão são inseridos como correções negativas.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Exemplo 3: A linha da ordem de devolução é criada utilizando a função Encontrar ordem de venda

Nesse exemplo, a linha da ordem de devolução é criada utilizando a função **Encontrar ordem de venda**. O parâmetro **Correção de crédito** não é selecionado quando a fatura é criada.  

[![Linha da ordem de devolução criada utilizando Encontrar ordem de venda ](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)  

**Observação:** **Desconto** e **Preço de custo da devolução** estão definidos corretamente. Portanto, ocorre uma inversão exata da fatura de cliente.




