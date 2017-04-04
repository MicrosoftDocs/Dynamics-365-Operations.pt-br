---
title: Use manuais suplementam o Excel
description: "Este tópico explica como os dados de entidade em aberto no Microsoft Excel e, depois, exibe, edita e atualiza os dados usando o manuais suplementam o Microsoft Dynamics para O Office Excel. Para abrir os dados da entidade, poderá começar Excel ou o Microsoft Dynamics 365 para as operações."
author: ChrisGarty
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: af7e7288f741b3c519227e2778c4c4311c3a2012
ms.openlocfilehash: 8af663b47117759ed3b2e2ed8eee85ae4df100d1
ms.lasthandoff: 03/31/2017


---

# <a name="use-the-excel-add-in"></a>Use manuais suplementam o Excel

Este tópico explica como os dados de entidade em aberto no Microsoft Excel e, depois, exibe, edita e atualiza os dados usando o manuais suplementam o Microsoft Dynamics para O Office Excel. Para abrir os dados da entidade, poderá começar Excel ou o Microsoft Dynamics 365 para as operações.

Abrindo dados de entidade no Microsoft Excel, é possível com rapidez e facilidade para exibir e editar os dados usando o manuais suplementam o Microsoft Dynamics para O Office Excel. Este manuais suplementam requer Microsoft Excel 2016. ** Observação: ** Se o inquilino do Active Directory do Microsoft Azure AD (de Azure) for configurado para usar Active Directory Federation Services (FS AD), será necessário garantir que a atualização de maio de 2016 foi aplicada, assim o Excel manuais suplementam possa corretamente o assinar em.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Dados entidade aberta Excel a partir de operações para dynamics 365
1.  Em uma página no Microsoft Dynamics 365 para operações, clique em abrir ** Microsoft Office **. Se a fonte de dados raiz (tabela) para a página é igual à fonte de dados de todas as entidades, standard raiz ** aberto Excel ** opções é gerada para a página. ** Aberto Excel ** opções pode ser encontrado em páginas frequentemente usados, como todas ** fornecedores ** e ** ** todos os clientes.
2.  Clicar ** abra Excel ** padrão, e abra a pasta de trabalho que é gerada. Essa pasta de trabalho tem vinculativa informações para a entidade, um ponteiro a seu ambiente, e um ponteiro manuais suplementam o Excel.
3.  Excel, clique ** habilitar edição ** para habilitar manuais suplementam o Excel para obtê-las. Executa manuais suplementam o Excel em um painel do lado direito janela Excel.
4.  Se você estiver executando o Excel manuais suplementam pela primeira vez, clique confie ** este manuais suplementam **.
5.  Se você for solicitado a conexão, clique ** conectar **, e conecte em usando as mesmas credenciais usado para conectar o dynamics 365 para as operações. Manuais suplementam o Excel do contexto anterior de logon do Internet Explorer e assinar-o-&z automaticamente dentro, se possível. Portanto, verifique o nome de usuário no canto superior direito de manuais suplementam Excel.

Manuais suplementam o Excel leia os dados automaticamente para a entidade selecionada. Observe que não haverá dados na pasta de trabalho o Excel manuais suplementam a leitura em.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Dados entidade aberta Excel a partir Excel
1.  Excel, em ** inserção ** guia, ** suplementos ** no grupo, clique ** armazenamento ** para abrir o armazenamento de O Office.
2.  No armazenamento de O Office, pesquisar em palavra-chave “>o”, e clique em adicionar ** ** próximo de manuais suplementam ** Dynamics ao Microsoft Office (** manuais suplementam o Excel).
3.  Se você estiver executando o Excel manuais suplementam pela primeira vez, clique confie ** este manuais suplementam ** para habilitar manuais suplementam o Excel para obtê-las. Executa manuais suplementam o Excel em um painel do lado direito janela Excel.
4.  Clique ** adicionar informações de servidor ** para abrir opções ** ** o painel.
5.  Copiar o navegador a URL de sua dynamics 365 de destino para operações cita como exemplo, em colar-lo ** URL do servidor ** campo, exclua todos e depois após o nome do host (por exemplo, ** de exclusão/? cmp=usmf&mi=CustTableListPage **). URL resultante ter apenas o nome do host (por exemplo, ** https://xxx.dynamics.com**).
6.  Clique em OK ** **, clique em Sim ** ** para confirmar a alteração. Os os é Excel e os metadados de cargas. ** Design ** o botão está disponível. Se tiver manuais suplementam o Excel a applet ** ** grade de carga, não estão conectados como o usuário provavelmente correto. Para obter mais informações, consulte “os applet carga do botão é exibido na seção “canal de solução de problemas” este tópico.
7.  Clique ** ** Design. Manuais suplementam o Excel recupera metadados entidade.
8.  Clique ** adicionar ** a tabela. Uma lista das entidades aparece. As entidades são listadas no nome “-” rotular o formato.
9.  Selecione uma entidade na lista, como cliente - ** ** clientes, e clique em Avançar ** **.
10. Para adicionar um campo ** campos disponíveis ** ** a lista de campos selecionados ** lista, clique no campo, e clique em adicionar. ** ** Alternativamente, clique duas vezes no campo.
11. Depois que você adicionar os campos desejados ** campos selecionados ** a lista, verifique se está o cursor no local correto na planilha (por exemplo, A1 de célula), além clicar-se em ** ** feito. Clique em ** feito ** para sair do designer.
12. Clique ** atualização ** para recebimento em um conjunto de dados.

## <a name="view-and-update-entity-data-in-excel"></a>Dados de entidade de exibição e do Excel
Depois do Excel manuais suplementam lê dados de entidade na pasta de trabalho, poderá atualizar os dados a qualquer hora clicando ** atualização ** manuais suplementam o Excel.

## <a name="edit-entity-data-in-excel"></a>Dados entidade editar Excel
Você pode alterar os dados da entidade que requer e publica em separado clicando ** publicar ** manuais suplementam o Excel. Para editar um registro, selecionar uma célula na planilha, e depois alterar o valor da célula. Para adicionar um novo registro, rastrear uma dessas etapas:

-   Clique em qualquer lugar na planilha, e clique em novo ** ** manuais suplementam o Excel.
-   Clique na última linha planilha, e pressionar na chave de guia o cursor se move fora de coluna a última dessa linha e uma nova linha for criada.
-   Clique na linha da planilha, e inicie para inserir dados em uma célula. Ao mover o foco fora da célula, expandir a planilha para incluir a nova linha.

Para excluir um registro, rastrear uma dessas etapas:

-   Clique no número de linha ao lado da linha da planilha para excluir, clique em excluir ** **.
-   Clique com o botão direito do mouse na linha da planilha para excluir, clique em excluir ** ** &gt; ** ** linhas da tabela.

## <a name="add-or-remove-columns"></a>Adicionar ou remover colunas
Você pode usar o designer ajustar colunas adicionada automaticamente a planilha.

1.  Inicie o designer de fonte de dados manuais suplementam Excel ** opções clicando ** botão (o símbolo de engrenagem) e selecionando ** habilitar o design ** a caixa de seleção.
2.  Clique ** Design ** manuais suplementam o Excel. Todas as fontes de dados são listadas.
3.  Próximas a fonte de dados, clique ** edição ** o botão (o símbolo de lápis).
4.  Ajuste a lista em ** campos selecionados ** listam como você precisa:
    -   Para adicionar um campo ** campos disponíveis ** ** a lista de campos selecionados ** lista, clique no campo, e clique em adicionar. ** ** Alternativamente, clique duas vezes no campo.
    -   Para remover um campo de ** campos selecionados ** lista, clique no campo, e clique em remover ** **. Alternativamente, clique duas vezes no campo.
    -   Para alterar a ordem dos campos, clique no campos selecionados ** ** lista, e em ** ** ** acima ou abaixo **.

5.  Aplique as alterações à fonte de dados clicando ** ** atualização. Clique em ** feito ** para sair do designer. Se você adicionou um campo (coluna), clique ** atualização ** para recebimento em um conjunto atualizado de dados.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Troubleshooting
Há alguns saídas que podem ser feitos em algumas fáceis etapas.

-   ** O botão de applet de carga é exibido. ** Se tiver manuais suplementam o Excel a applet ** de carga ** grade após o logon, não estão conectados como o usuário provavelmente correto. Para resolver esse problema, verifique o nome do usuário atual aparece no canto superior direito de manuais suplementam Excel. Se um nome de usuário incorreto aparece, clique desconectar-lo, e assinar-lo na parte traseira em.
-   ** Você receberá uma mensagem “proibida”. ** Se receber uma mensagem “proibida” quando manuais suplementam o Excel e metadados, a conta que está conectada ao Excel manuais suplementam não tiver permissão para usar o serviço, a instância ou, o base de dados de destino. Para resolver esse problema, verifique o nome do usuário atual aparece no canto superior direito de manuais suplementam Excel. Se um nome de usuário incorreto aparece, clique desconectar-lo, e assinar-lo na parte traseira em.
-   ** Uma página da Web em branco é mostrado sobre Excel. ** Se uma página da Web em branco abre durante o processo de logon, conta requer AD FS, mas a versão De que está executando manuais suplementam o suficiente recente não é cobrado a caixa de diálogo de logon. Para resolver esse problema, atualização Da versão usada. Para atualizar a versão Excel quando você está em uma empresa que foi adiado no canal, use ferramenta [] de implementação de O Office (https://technet.microsoft.com/library/jj219422.aspx) [movimento de canal adiado o canal atual] (https://technet.microsoft.com/library/mt455210.aspx).



