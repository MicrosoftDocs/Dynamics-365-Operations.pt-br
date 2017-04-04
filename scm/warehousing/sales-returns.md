---
title: "Devoluções de vendas"
description: "Este tópico fornece informações sobre o processo de ordens de devolução. Inclui informações sobre devoluções do cliente e o efeito em quantidades de custos e de estoque disponível."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: b265a20a271230de5dba6df93900a24aad642885
ms.lasthandoff: 03/31/2017


---

# <a name="sales-returns"></a>Devoluções de vendas

Este tópico fornece informações sobre o processo de ordens de devolução. Inclui informações sobre devoluções do cliente e o efeito em quantidades de custos e de estoque disponível.

Os clientes podem retornar itens por diversas razões. Por exemplo, um item poderá ser defeituoso, ou pode não atender as expectativas de cliente. Inicia de processo ao emitir uma solicitação devolver um item. Depois da solicitação do cliente é recebida, uma ordem de devolução será criada no Microsoft Dynamics 365 para as operações.

## <a name="return-order-process"></a>Processo de ordem de devolução
A ilustração a seguir apresenta uma visão geral do processo de ordem de devolução.  

[![(salesreturns01]. /media/salesreturns01.jpg)](. /media/salesreturns01.jpg)  

Há dois tipos de processo de ordem de devolução: devolução e crédito de auditoria apenas.

-   ** O giro físicas ** – a ordem de devolução capacita físico devolução de produto.
-   ** O crédito apenas ** – a ordem de devolução autorizar um crédito de cliente mas não exige que a devolução de cliente fisicamente produtos.

### <a name="physical-return-order-process"></a>Processo de ordem de devolução de auditoria

1.  ** Criar uma ordem de devolução. ** Documento formalmente a autorização para o cliente que retorna todos os produtos ou defeituosos indesejados. A ordem de devolução não exige que a empresa aceite os bens devolvidos ou fornece um crédito do cliente. Se o total é aceito, você pode autorizar um item de substituição para ser enviada antes que o item seja devolvido. defeituoso
2.  ** Chegue no depósito para inspeção. ** Concluir uma inspeção inicial e uma validação no documento de ordem de devolução. A ordem de devolução também oferece suporte a quarentena de itens devolvidos para inspeção e o controle de qualidade adicionais.
3.  ** Determine a disposição. ** Para finalizar o processo de inspeção, e decida o que deve ser feito com os produtos devolvidos. Como parte da etapa, decida se você creditará substituirá o cliente, a devolução de produto, a devolução ou aceitará de produto, sucata de produto, e enviar-se em um produto de substituição para o cliente.
4.  ** Gerar uma guia de remessa. ** Gerar uma guia de remessa e confirme, a decisão de disposição que você fez na etapa 3. Finaliza processos de logística.
5.  ** Gerar uma nota fiscal. ** Fechar a ordem de devolução.

### <a name="credit-only-process"></a>Credite apenas o processo

1.  ** Criar uma ordem de devolução. ** Documento formalmente a autorização para que o cliente receba um crédito ou devolver o produto ou defeituosos indesejados. ** Somente crédito ** o código de disposição autoriza a decisão para creditar o cliente sem devolução físico.
2.  ** Gerar uma nota fiscal. ** Gerar para nota de crédito, e feche a ordem de devolução.

## <a name="return-material-authorization"></a>(Autorização de devolução
Processamento (RMA) de ADM (autorização de devolução cria em funcionalidade de ordem de venda. Um ADM é registrado como uma ordem de devolução, que seja criada como uma ordem de venda, e pode ter outra ordem de venda associado a ela, denominada uma ordem de substituição. Ambas as ordens de venda são vinculadas ao número de adm de origem.

-   ** A ordem de devolução ** – registre um ADM, criar uma ordem de devolução, que é uma ordem de venda tenha o tipo ordem, atribuído ** devolvido. ** Todas as alterações feitas às informações de adm são atualizadas automaticamente na ordem de venda. Até a ordem de devolução com o status ** ** aberto, não será exibido na lista de ordens de venda. Você usa ADM para tratar da chegada e o recebimento de itens devolvidos, e para autorizar uma ação de disposição de crédito apenas (consulte a seção ** códigos de disposição e ações de disposição **). Todos os outros processos acompanhares devem ser tratados na ordem de venda.
-   ** O ordem de substituição ** – quando uma ordem de substituição seja enviada ao cliente, o ADM pode incluir uma segunda ordem de venda associada. Você pode criar manualmente uma ordem de substituição para o titular ADM consignação instantânea. Alternativamente, a ordem de substituição pode ser criado automaticamente após a inspeção, entrada, o recebimento é preenchido para o item de adm que tenha um código de disposição que indique substituição. A ordem de substituição tem a mesma funcionalidade associada a uma ordem de venda. Por exemplo, você poderá usá-lo para configurar como um produto personalizado o item substituto, criar uma ordem de produção reparar item devolvido, criar uma ordem de compra de entrega direta enviar a substituição de um fornecedor ou de suporte, fins.

## <a name="create-a-return-order"></a>Criar uma ordem de devolução
Inicia de processo da ordem quando contatos da empresa cliente devolve um produto ou defeituosos indesejados e/ou serem creditadas. Depois que sua organização aceita a devolução, a devolução será documentado por uma ordem de devolução. Essa ordem de devolução será a de foco de processamento interno de bens devolvidos. A ilustração a seguir mostra o procedimento para criar uma ordem de devolução.  

[procedimento![para criar uma ordem de devolução (]. /media/salesreturn02.png)](. /media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Criar um cabeçalho de ordem de devolução

Quando você cria uma ordem de devolução, as informações na tabela deve ser incluída.

| Campo              | descrição                                              | Comentários                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Conta de cliente   | Referência à tabela clientes                       | Você deve fornecer uma conta de cliente existente.                                                                                                                                                                                                                                                                                                  |
| Endereço de entrega   | O endereço em que o item é devolvido a                 | Por padrão, o endereço da organização é usado. Se um depósito específico for selecionado no cabeçalho, o endereço de entrega será alterado para o endereço de entrega em depósito. Você pode alterar este endereço ** os detalhes da ordem de devolução ** na página.                                                                                                  |
| Site/depósito     | O local ou o depósito que recebem os bens devolvidos | O endereço de entrega da ordem de devolução é determinado com base no endereço de entrega local ou depósito.                                                                                                                                                                                                                                 |
| Número de ADM         | O identificador atribuído à ordem de devolução              | O número de adm é usado como uma chave alternativa todo o processo de ordem de devolução. O número de adm é atribuído com base na sequência numérica de adm configurada ** parâmetros de contas a receber ** na página.                                                                                                                              |
| Prazo final           | A última data em que um item pode ser devolvida               | O valor padrão é calculada como a data atual mais o período de validade. Por exemplo, se uma devolução for somente válido por 90 dias a data em que a ordem de devolução será criada, e a ordem de devolução foi criada o 1º de maio, o valor no campo é 30-July ** **. O período de validade será definido ** parâmetros de contas a receber ** na página. |
| Código de motivo de devolução | A razão do cliente devolver os produtos          | O código de motivo é selecionado na lista de códigos de razão definidos pelo usuário. Você pode atualizar este campo a qualquer momento.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Crie as linhas de ordem de devolução

Após concluir o cabeçalho de devolução, você pode criar linhas de devolução usando um destes métodos:

-   Insira manualmente os detalhes do item, a quantidade, e outras informações para cada linha de vendas.
-   Crie uma linha de devolução usando ** ordem de venda localizar ** a função. Recomenda-se usar esta função quando criar uma ordem de devolução. ** Ordem de venda localizar ** a função como uma referência da linha de volta à linha de ordem de venda faturada, e obtém a linha detalhes como número de item, quantidade, preços, descontos, os valores de custo de venda. Ajuda de referência garantem que, quando os bens forem devolvidos para a empresa, avaliou o mesmo custo unitário em que foi vendido. A referência também que valida as ordens de devolução não serão criadas para uma quantidade que excede a quantidade que foi vendido na nota fiscal.

** Observação: ** As linhas de devolução com uma referência a uma ordem de venda são tratadas como correções, reversões, ou de venda. Para obter mais informações, consulte a seção “lançar no razão,” posteriormente neste tópico.

### <a name="charges"></a>Encargos

As taxas e os encargos poderão ser adicionados à ordem de devolução com um ou mais destes métodos:

-   Você poderá adicionar manualmente encargos ao cabeçalho da ordem, a linha de ordem, ou a ambos.
-   Encargos podem ser adicionadas automaticamente ao cabeçalho de ordem de devolução em função do código de motivo de devolução.
-   Encargos podem ser adicionadas automaticamente à linha de ordem, com base no código de disposição da linha.

Os encargos serão adicionados automaticamente depois que um código de motivo de devolução ou o código de disposição são atribuídos à linha. Se o código de motivo é alterado posteriormente, a entrada de despesa existente não será removida, mas uma nova entrada de encargo pode ser adicionada, com base no novo código de motivo. Quando você adicionar encargos às linhas de ordem de devolução, encargos que é calculado como uma porcentagem da linha ou de ordem se tornem negativo quando a linha ou à ordem forem negativa, a menos que a porcentagem é também um número negativo. Um encargo que tem um valor negativo representa um crédito ao cliente.

### <a name="return-reason-codes"></a>Códigos de motivo de devolução

Aplicando códigos de motivo para devoluções, poderá ajudar a facilitar os padrões de devolução analisar. Os códigos de movito fornecem informações sobre como um cliente quer devolver itens. Algumas organizações têm muitos códigos de motivo. Este a organização pode agrupar códigos de motivo em grupos de códigos de motivo para ter uma visão geral melhor e acumulado para o relatório.

### <a name="disposition-codes-and-disposition-actions"></a>Códigos de disposição e ações de disposição

Importante uma etapa no processo de ordem de devolução é a atribuição de um código de disposição a linha da ordem como parte do registro de entrada. O código de disposição determina as seguintes informações:

-   ** As implicações financeiras ** – o cliente deve ser creditado para itens devolvidos, e algum encargo deve ser adicionado à linha de ordem?
-   ** A disposição de item devolvido deve ** – o item podem ser adicionadas novamente o estoque, deve ser sucateada, ou ele deverá ser devolvida ao cliente?
-   ** A logística de item devolvido deve ** – um item de substituição ser emitido a cliente?

Além da determinação como os bens devolvidos são dispostos, códigos de disposição podem causar encargos a ser aplicado à linha de devolução. Também podem ser usados para agrupar devoluções para análise estatística. Códigos de disposição é definido como parte da instalação das ordens de devolução. Entretanto, cada código de disposição pode fazer referência a uma das ações de disposição internos. A seguinte tabela lista os códigos de disposição internos e suas ações. ** Importante: ** Se um item é devolvido, mas o cliente deverá ainda ser creditado, atribui ** somente crédito ** o código de disposição a linha de devolução.

<table>
<thead>
<tr class="header">
<th>Código de disposição</th>
<th>Implicações financeiras</th>
<th>Implicações de logística</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Somente crédito</td>
<td><ul>
<li>O cliente é creditado o preço de venda menos todas as taxas ou encargos.</li>
<li>Perda de transformar o item é lançada no razão.</li>
</ul></td>
<td>O item não será devolvido. Esta ação de disposição for usada nos seguintes casos:
<ul>
<li>Há uma suficiente confiança entre participantes.</li>
<li>O custo de devolução do item são proibitivos defeituoso.</li>
<li>Os itens podem não ser permitidos de volta ao estoque. Devido as outras condições, devolução físico não é necessária.</li>
</ul></td>
</tr>
<tr class="even">
<td>Crédito</td>
<td><ul>
<li>O cliente é creditado o preço de venda menos todas as taxas ou encargos.</li>
<li>O valor de estoque aumenta os custos de item devolvido.</li>
</ul></td>
<td>O item é devolvido e adicionado de volta ao estoque.</td>
</tr>
<tr class="odd">
<td>Substituir e creditar</td>
<td><ul>
<li>O cliente é creditado o preço de venda menos todas as taxas ou encargos.</li>
<li>O valor de estoque aumenta os custos de item devolvido.</li>
<li>Uma ordem de venda separada para uma substituição é criada e são tratados separadamente.</li>
</ul></td>
<td>O item é devolvido e adicionado de volta ao estoque.</td>
</tr>
<tr class="even">
<td>Substituir e sucata</td>
<td><ul>
<li>O cliente é creditado o preço de venda menos, as taxas ou encargos.</li>
<li>Perda de transformar o item é lançada no razão.</li>
<li>Uma ordem de venda separada para uma substituição é criada e são tratados separadamente.</li>
</ul></td>
<td>O item é devolvido e sucateada.</td>
</tr>
<tr class="odd">
<td>Devolver ao cliente</td>
<td>Nenhum, exceto por taxas ou encargos.</td>
<td>O item é devolvido mas é enviado para o cliente após a inspeção. Esta ação de disposição pode ser usada se o item for danificado deliberadamente, ou se a garantia foi cancelada.</td>
</tr>
<tr class="even">
<td>Sucata</td>
<td><ul>
<li>O cliente é creditado o preço de venda menos todas as taxas ou encargos.</li>
<li>Perda de transformar o item é lançada no razão.</li>
</ul></td>
<td>O item é devolvido ou sucateado.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Entrada no depósito para inspeção
Antes do recebimento de itens devolvidos fisicamente no estoque para lançar uma guia de remessa, os itens devem partilhe o registro de entrada e uma inspeção opcional. A ilustração a seguir apresenta uma visão geral do processo de entrada. Seções que acompanham descrevem cada etapa que é mostrada na ilustração.  

[processo de entrada do![(]. /media/salesreturn03.png)](. /media/salesreturn03.png)  

O processo várias outras variações que não são abrangidas neste tópico. Veja a seguir algumas das variações:

-   Não use ** visão geral de entrada ** listam para criar um diário de entrada. Em vez disso, crie manualmente o diário de entrada. Ordens de devolução de ordem terão ** venda ** como referência.
-   Se estiver usando gerenciamento de depósito, gerenciar transportes de palete. A linha de devolução terá um status igual ** chegado ** durante o transporte de palete.
-   Registrar a entrada de itens seja devolvida diretamente de linha de ordem, usando ** registro ** a função.

Durante o processo de entrada, as devoluções são integrados com o processo geral para entradas de depósito. O processo de entrada também oferece suporte à criação de ordens de quarentena que os itens devolvidos devem se submeter a inspeção separada.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identifique produto na visão geral de entrada

** Visão geral de entrada ** o página lista todas as entradas de entrada planejadas. ** Observação: ** As entradas de ordens de devolução deve ser processadas separadamente de outros tipos de transações de entrada. Depois de identificar um pacote de entrada em ** visão geral de entrada ** (página por exemplo, usando o documento de rastreamento de adm), no painel de ações, clique ** entrada Inicial ** para inicializar e criar um diário de entrada que corresponda a entrada.

### <a name="edit-the-arrival-journal"></a>Editar o diário de entrada

Definindo Sim ** gerenciamento de quarentena ** padrão ** **, você pode criar uma ordem de quarentena a linha de devolução. Se uma linha é enviada a quarentena para inspeção, você não poderá especificar um código de disposição. ** Observação: ** Se você definir Sim ** gerenciamento de quarentena ** padrão ** ** o grupo modelo de estoque do item, ** gerenciamento de quarentena ** a opção ** ** linhas de diário na página será marcado para a linha de diário de entrada e não pode ser alterado. Se a linha é enviada para a quarentena, especifique o depósito apropriado de quarentena. Se a linha de entrada não for enviada para inspeção, o auxiliar de entrada de depósito deve especificar o código de disposição diretamente na linha de diário de entrada e depois lançar o diário de entrada. Se o mesmo código de disposição é atribuído à quantidade inteira da linha de vendas, ou se a quantidade total da linha não foi recebida, você deverá dividir a linha. Quando estiver dividido uma linha de diário de entrada, também divide a linha de devolução (SalesLine ** **) e criar uma nova ID de lote. Você pode dividir a linha reduzindo a quantidade da linha de diário de entrada. Quando o diário é lançado, uma nova linha de devolução será criada de com um status ** ** esperado para a quantidade pendente. Você também pode dividir a linha clicando ** funções ** &gt; ** ** a separação.

### <a name="process-the-quarantine-order"></a>Processar ordem de quarentena

Se os bens devolvidos são enviados para inspeção o depósito de quarentena, qualquer processamento adicional está concluído em uma ordem de quarentena. Uma ordem de quarentena é criada para cada linha de entrada que é enviada a quarentena. O código de disposição indica o resultado do processo de inspeção. Você pode dividir uma ordem de quarentena, assim como você pode dividir o diário de entrada. Se você dividido a ordem de quarentena, você uma causa separação de linha correspondentes de devolução. Depois que o código de disposição é inserido, conclua a ordem de quarentena ** ** empresa usando a função ou ** relatar como concluído ** a função. Se selecionar ** relatar como concluído **, uma nova entrada será criada no depósito destinadas. Você poderá então processar esta entrada usando ** visão geral de entrada ** a página. Se a entrada origina de uma ordem de quarentena, não poderá alterar o código de disposição atribuído durante a inspeção. Se você preencher a ordem de quarentena ** ** empresa usando a função, o lote registrado automaticamente. Ocasionalmente, pode ser um item devolvido da quarentena para o departamento de remessa e recebimento. Por exemplo, o inspetor de quarentena não pode saber onde armazenar o item em estoque. Nesse caso, a guia de remessa correspondente deve ser atualizada para registrar apropriadamente e agir no código de disposição especificado devido para a quarentena. O recebimento de aviso pode ser enviada ao cliente quando a linha de devolução é registrada. ** Confirmação de devolução ** o relatório se assemelha o documento de ordem de devolução. ** Confirmação de devolução ** o relatório não será lançado no diário ou não é registrado por outro motivo no sistema, e não é uma etapa obrigatória no processo de ordem de devolução.

## <a name="replace-a-product"></a>Substituir um produto
Há dois métodos para gerenciar a substituição de produtos:

-   ** Substituição honesto ** – substitua produto antes que os bens devolvidos sejam recebidos de clientes.
-   ** A substituição por código de disposição ** – cria automaticamente uma nova linha de ordem de substituição.

### <a name="up-front-replacement"></a>Substituição adiantada

A substituição honesto, o item substituto pode ser entregue ao cliente antes que o item seja devolvido. Este método é útil se, por exemplo, o item é uma parte do computador que não pode ser removida a menos que uma peça sobressalente estará disponível para executar sua localização, ou se você quiser apenas o cliente para que o produto de substituição o mais rápido possível. A ordem honesto substituição for uma ordem de venda independentes. Informações do cabeçalho é inicializada de cliente, e a linha é inicializada informações de ordem de devolução. Você pode editar, processamento, e excluir a ordem de substituição independentemente de ordem de devolução. Quando você exclui uma ordem de substituição, receberá uma mensagem de que a ordem foi criada como uma ordem de substituição. A ilustração a seguir mostra o processo para a substituição honesto.  

[] honesto processo (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)] substituição![(https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)  

A ordem de devolução contém uma referência à ordem de substituição. Se uma ordem honesto de substituição é criada para uma ordem de devolução antes que o item foi devolvido defeituoso, não poderá selecionar códigos de disposição para substituição depois que o item foi retornado defeituoso.

### <a name="replacement-by-disposition-code"></a>Substituição por código de disposição

Se você enviar um item de substituição para o cliente, e usa ** substituir se e desfaça ** ** ou substitua e credite ** a ação de disposição na ordem de devolução, use o processo que é mostrado na seguinte ilustração.  

[processo substituição![quando um código de disposição é usado (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)]] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)  

O item substituto será entregue usando uma ordem de venda independentes, a ordem de substituição. Essa ordem de venda é criado quando a guia de remessa da ordem de devolução é gerado. O cabeçalho de ordem usa informações de cliente que é referida no cabeçalho da ordem de devolução. A linha informações são coletadas das informações inseridas ** item substituto ** na página. ** Item substituto ** o página deve ser preenchido para linhas que possuem ações de disposição que começam com a palavra “substituir.” Contudo, nem a quantidade ou a identificação de item de substituição ou forem validadas limitadas. Esse comportamento permite casos em que o cliente deseja o mesmo item mas uma configuração ou um tamanho diferente, além casos em que os clientes desejam um item totalmente diferentes. Por padrão, um item é inserido idêntico ** item substituto ** na página. Entretanto, você pode selecionar um item diferente, desde que o formulário foi configurada. ** Observação: ** Você pode editar e excluir a ordem de substituição após criou.

## <a name="generate-a-packing-slip"></a>Gerar uma guia de remessa
Antes que os itens devolvidos possam ser recebidos no estoque, você deve atualizar a guia de remessa da ordem em que os itens pertencem. Assim como o processo de atualização da nota fiscal é a atualização da transação financeira, o processo de atualização da guia de remessa é a atualização física de estoque. Ou seja este processo confirma as alterações do estoque. No caso de devoluções, as etapas atribuídas à ação de disposição são implementadas durante a atualização da guia de remessa. Quando você gera o guia de remessa, os seguintes eventos ocorrerão:

-   No depósito, o processo padrão é usada para executar um recebimento físico. As postagens do razão geradas se o grupo modelo de estoque (** lançar estoque físico **) e os parâmetros de contas a receber (** lançar guias no razão **) são definidos apropriadamente.
-   Os itens que foram marcados com uma ação de disposição que a palavra “sem” sucata são sucateados, e perdas de estoque são lançadas no razão.
-   Os itens que foram marcados com ** ** cliente devolver para a ação de disposição são recebidos e entregues ao cliente. Esses itens não afetarão líquido no estoque.
-   Uma ordem de substituição é criada. Essa ordem de venda baseia-se em informações ** item substituto ** na página.

Você pode gerar a guia de remessa somente para as linhas de com um status de retorno ** registrado **, e somente para a quantidade total na linha de devolução. Se várias linhas na ordem de devolução têm ** registrado ** status, você pode gerar a guia de remessa de um subconjunto de linhas excluindo as outras linhas ** lançar guias ** de página. As devoluções parciais são definidas em termos de linhas de ordem de devolução, não em termos das remessas de ordem de devolução. Portanto, se você receber a quantidade total indicada em uma linha de ordem, mas você receber nada das outras linhas de ordem de devolução, a entrega não é uma entrega parcial. Entretanto, se uma linha de ordem de 10 unidades de um item são devolvidas, mas você receber apenas quatro unidades, entrega é uma entrega parcial. Se nem todos os itens de devolução esperados foram recebidos, você pode reservar a remessa e aguardar até o resto da quantidade devolvida para chegada. Alternativamente, você pode registrar e lançar a quantidade parcial. Como parte do processo lançar guias de remessa, você pode associar o número de referência da guia de remessa dos documentos de remessa de cliente com as linhas. Esta associação serve opcional e é apenas para referência. Não cria nenhuma atualização transacional. Geralmente, você pode ignorar o processo da guia de remessa e ir diretamente faturamento. Nesse caso, as etapas que você executaria durante a geração da guia de remessa são executadas durante o faturamento.

## <a name="generate-an-invoice"></a>Gerar uma fatura
Embora ** a ordem de devolução ** o página contém informações e as ações necessárias para tratar os aspectos logísticos especiais da ordem de devolução, você deve usar ** ** ordem de venda a página para concluir o processo de faturamento. Sua organização poderá faturar ordens e ordens de venda de devolução ao mesmo tempo, e a mesma pessoa poderá concluir o processo de faturamento, conforme necessário. Para exibir a ordem de devolução ** ** ordem de venda da página, clique no link do número de ordem de venda abra a ordem de venda associada. Também é possível localizar a ordem de devolução ** todas as ordens de venda na página. ** Ordens de devolução são ordens de venda com um tipo de ordem ** devolvido ** ordem.

### <a name="credit-correction"></a>Correção de crédito

Como parte do processo de faturamento, verifique se todos os encargos diversos estão corretos. Para fazer com que as postagens contábil transformem-se correções (Estorno), considere o uso ** correção de crédito a opção ** ** outro ** ** na fatura de postagem ** de páginas ao lançar a nota fiscal/nota de crédito. ** Observação: ** Por padrão, ** correção de crédito ** a opção se for ativada ** nota de crédito como correção ** a opção ** parâmetros de contas a receber em ** página foi habilitada. Entretanto, é recomendável que você não lançar devoluções com Estorno.

## <a name="create-intercompany-return-orders"></a>Criar ordens de devolução intercompanhia
Ordens de devolução podem ser preenchidos entre duas empresas dentro de sua organização. Os cenários a seguir são suportados:

-   Devoluções intercompanhia simples entre duas empresas que participam de uma relação intercompanhia
-   Um grupo intercompanhia que é estabelecida quando uma ordem de devolução de cliente é criado na empresa de venda
-   Um grupo intercompanhia que é estabelecida quando uma ordem do fornecedor for criada na empresa de compra
-   A remessa de entrega direta entre retorna um cliente externo e duas empresas que participa de uma relação intercompanhia

### <a name="setup"></a>Instalação

A ilustração a seguir o de instalação mínima necessária para que participa duas empresas em uma relação intercompanhia e se aproveitem de comércio intercompanhia.  

[![Minimum setup](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

Neste cenário, CompBuy é a empresa de compra, e CompSell é a empresa vendedora. Normalmente, a empresa vendedora envia mercadorias para a empresa ou de compra, em cenários de entrega, de remessa diretamente ao cliente final. Em CompBuy, fornecedor IC\_CompSell é definido como uma empresa intercompanhia associado à empresa CompSell. Simultaneamente, CompSell em, cliente IC\_CompBuy é definido como uma empresa intercompanhia associado à empresa CompBuy. Os detalhes diretiva de ações adequada e os mapeamentos de valor devem ser definidos nas duas empresas. Em um cenário direto de entrega, remessa de uma ordem de devolução intercompanhia, que também é uma ordem de venda intercompanhia, é criado na empresa vendedora. O número de ADM entre a ordem de devolução intercompanhia pode ser selecionado de sequência numérica de adm em CompSell, ou pode ser copiada de NÚMEROS de ADM atribuído à ordem de devolução originais em CompBuy. As configurações do número de adm ** PurchaseRequisition ** na diretiva de ação em CompBuy determinam essas ações. Se o número de adm é sincronizado, você deve planejar atenuar o risco de conflitos numérica se duas empresas usam a mesma sequência numérica.

### <a name="simple-intercompany-returns"></a>Devoluções intercompanhia simples

Esse cenário envolve duas empresas na mesma organização, conforme mostrado na ilustração.  

[] devolução intercompanhia simples (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)]![(https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)  

A cadeia de ordem pode ser liquidada durante uma ordem de devolução de fornecedor será criado na empresa de compra ou ordem de devolução de cliente será criado na empresa vendedora. O dynamics 365 operações para criar a ordem correspondente em outra empresa e garante que o cabeçalho e as informações de linha na ordem de devolução fornecedor refletem as configurações na ordem de devolução de cliente. A ordem de devolução que é liquidado pode incluir ou excluir a referência (** ordem de venda) localizar ** a uma nota fiscal de cliente existente. As guias de remessa e notas fiscais das duas ordens poderão ser processadas separadamente. Por exemplo, não é necessário gerar uma guia de remessa da ordem de devolução do fornecedor antes de gerar o guia de remessa da ordem de devolução de cliente.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>A remessa de entrega direta entre três retorna participantes

Esse cenário pode estabelecer se uma venda anterior ** entrega direta ** o tipo for concluído, e se uma nota fiscal ao cliente na empresa que interagem com o cliente. Nesta ilustração, a empresa tem CompBuy anteriormente produtos vendidos e faturados para o cliente Extern. O produto foram enviadas diretamente da empresa CompSell o cliente em uma cadeia de ordem intercompanhia.  

[a remessa de entrega direta do![sejam entre três] participantes (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)]  

Se o cliente Extern deseja devolver os produtos, uma ordem de devolução (RMA02) será criado para o cliente na empresa CompBuy. Para liquidar a cadeia intercompanhia, a ordem de devolução deve ser marcada para entrega direta. Quando você usa ** ordem de venda localizar ** funciona para escolher a nota fiscal do cliente devolver, uma cadeia de ordem intercompanhia que consiste nos seguintes documentos: é liquidada

-   ** Ordem de devolução original: ** RMA02 (empresa CompBuy)
-   ** Ordem de compra: ** PO02 (empresa CompBuy)
-   ** Ordem de devolução intercompanhia: ** ADM\_00032 (CompSell empresa)

Depois da cadeia de entrega direta intercompanhia é criada qualquer, físicas e manuseio de devoluções processamento devem ocorrer no contexto da ordem de devolução intercompanhia, ADM\_00032 na empresa CompSell. Produtos que não podem ser recebidos na empresa CompBuy. Quando um código de disposição é atribuído à ordem de devolução intercompanhia, sincronizou-se à ordem de devolução original adequada permitir o faturamento da ordem original.

## <a name="post-to-the-ledger"></a>Lançar no razão
As postagens do razão geradas quando a ordem de devolução é faturada são alguns influenciadas por configurações e parâmetros importantes:

-   ** O preço de custo estimado de devolução ** – de modelos de estoque de custo diferentes ** ** ** padrão, o preço de custo estimado de devolução ** o parâmetro determinará custos de item quando aceitou de volta ao estoque ou sucateado. Para calcular uma previsão de estoque correto, é importante que você definir ** o preço de custo estimado de devolução ** o parâmetro corretamente. Se usar ** ordem de venda localizar ** funciona para criar uma linha de ordem com uma referência à nota fiscal de cliente, ** o preço de custo estimado de devolução ** o valor é igual ao preço de custo estimado de itens vendidos. Caso contrário, o valor do preço de custo estimado ajuda de configuração de item ou podem ser inseridos manualmente.
-   ** Correção de crédito/Estorno ** – ** correção de crédito ** o parâmetro ** fatura de postagem ** o página determina se as postagens devem ser registradas como entradas (DR/CR) positivas ou como corrigindo, entradas negativas.

Nos exemplos que acompanham, o preço de custo estimado de devolução são representadas como Inv **. Preço de custo estimado **.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Exemplo 1: A ordem de devolução não faz referência uma nota fiscal de cliente

A ordem de devolução não faz referência uma nota fiscal de cliente. O item devolvido é creditada. ** Correção de crédito ** o parâmetro não estiver selecionada quando a nota fiscal de ordem de devolução, ou nota de crédito, serão gerados.  

[a ordem de devolução do![não faz referência um cliente invoic] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)]  

** Observação: ** O preço do item mestre será usado como valor padrão para ** o preço de custo estimado de devolução ** o parâmetro. O preço padrão for diferente do preço de custo estimado no momento da saída de estoque. Portanto, a implicação é que uma perda de 3 foi incorrida. Além disso, a ordem de devolução não incluir o desconto que foi atribuído ao cliente na ordem de venda. Portanto, um crédito em excesso ocorre.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Exemplo 2: Correção de crédito estiver marcada para a ordem de devolução

O exemplo 2 é igual ao exemplo 1, mas ** correção de crédito ** o parâmetro for selecionado quando a nota fiscal de ordem de devolução é gerada.  

[ordem de devolução do![na correção de crédito estiver marcada] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)]  

** Observação: ** As postagens contábil são inseridas como correções negativas.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Exemplo 3: A linha de ordem for criada com a função de localizar venda

Neste exemplo, a linha de ordem é criada usando-se ** ordem de venda localizar ** a função. ** Correção de crédito ** o parâmetro não estiver selecionada quando a nota fiscal é criada.  

[linha de ordem de devolução do![que é criada com a ordem de venda (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)]] localizar (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)  

** Observação: ** ** ** ** Desconto e o preço de custo estimado de devolução ** estão definidos corretamente. Portanto, uma reversão exata de cliente da nota fiscal ocorre.


