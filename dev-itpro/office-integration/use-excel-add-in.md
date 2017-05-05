---
title: Utilizar o suplemento do Excel
description: "Este tópico explica como abrir dados da entidade no Microsoft Excel, e então visualizar, atualizar e editar os dados usando o suplemento do Microsoft Dynamics Office para Excel. Para abrir os dados da entidade, você pode começar pelo Excel ou pelo Microsoft Dynamics 365 para Operações."
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

# <a name="use-the-excel-add-in"></a>Utilizar o suplemento do Excel

Este tópico explica como abrir dados da entidade no Microsoft Excel, e então visualizar, atualizar e editar os dados usando o suplemento do Microsoft Dynamics Office para Excel. Para abrir os dados da entidade, você pode começar pelo Excel ou pelo Microsoft Dynamics 365 para Operações.

Ao abrir os dados da entidade no Microsoft Excel, é possível visualizar e editar facilmente os dados utilizando o suplemento do Microsoft Dynamics Office para Excel. Este suplemento requer o Microsoft Excel 2016. **Observação:** Se o seu inquilino do Microsoft Azure Active Directory (Azure AD) está configurado para usar o Active Directory Federation Services (AD FS), você deve garantir que a atualização de maio de 2016 foi instalada, para que o suplemento do Excel consiga realizar seu login corretamente.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Abrir dados da entidade no Excel ao iniciar pelo Dynamics 365 para Operações
1.  Em uma página no Microsoft Dynamics 365 para Operações, clique em **Abrir no Microsoft Office**. Se a fonte de dados raiz (tabela) da página for a mesma que a fonte de dados raiz de qualquer entidade, opções **Abrir no Excel** padrões são geradas para a página. Opções **Abrir no Excel** podem ser encontradas em páginas frequentemente usadas, como **Todos os fornecedores** e **Todos os clientes**.
2.  Clique em uma opção **Abrir no Excel**, e abra a pasta de trabalho gerada. Essa pasta de trabalho possui informações obrigatórias da entidade, um indicador para seu ambiente e um indicador para o suplemento do Excel.
3.  No Excel, clique em **Habilitar edição** para permitir que o suplemento do Excel seja executado. O suplemento do Excel funciona em um painel do lado direito da janela do Excel.
4.  Caso esteja executando o suplemento do Excel pela primeira vez, clique em **Confiar nesse Suplemento**.
5.  Se estiver preparado para fazer o login, clique em **Iniciar sessão**, e então faça o login utilizando as mesmas credenciais usadas no login do Dynamics 365 para Operações. O suplemento do Excel usará um contexto de entrada anterior do Internet Explorer e conectará você automaticamente, se possível. Portanto, verifique o nome de usuário no canto superior direito do suplemento do Excel.

O suplemento do Excel lê automaticamente os dados da entidade selecionada. Observe que não haverá dados na pasta de trabalho até que o suplemento do Excel realize a leitura.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Abrir dados da entidade no Excel ao iniciar pelo Excel
1.  No Excel, na guia **Inserir**, no grupo **Suplementos**, clique em **Loja** para abrir a Loja do Office.
2.  Na Loja do Office, busque com a palavra "Dynamics" e clique em **Adicionar** próximo a **Suplemento do Microsoft Dynamics Office** (o suplemento do Excel).
3.  Caso esteja executando o suplemento do Excel pela primeira vez, clique em **Confiar nesse suplemento** para permitir que o suplemento funcione. O suplemento do Excel funciona em um painel do lado direito da janela do Excel.
4.  Clique em **Adicionar informações do servidor** para abrir o painel **Opções**.
5.  Copie a URL da instância desejada do Dynamics 365 para Operações, cole no campo **URL do servidor**, e em seguida apague tudo após o nome do host (por exemplo, apague **/?cmp=usmf&mi=CustTableListPage**). A URL resultante deve ter apenas o nome do host (por exemplo, **https://xxx.dynamics.com**).
6.  Clique em **OK**, e em seguida clique em **Sim** para confirmar a alteração. O suplemento do Excel reinicia e carrega os metadados. O botão **Design** agora está disponível. Se o suplemento do Excel possuir um botão **Carregar applets**, você provavelmente não está conectado como o usuário correto. Para obter mais informações, consulte "O botão Carregar applets está aparecendo" na seção "Solução de Problemas" desse tópico.
7.  Clique em **Design**. O suplemento do Excel recupera metadados da entidade.
8.  Clique em **Adicionar tabela**. Uma lista de entidades aparece. As entidades são listadas no formato "Nome - Rótulo".
9.  Selecione uma entidade da lista, como **Cliente - Clientes**, e em seguida clique em **Próximo**.
10. Para adicionar um campo da lista **Campos disponíveis** à lista **Campos selecionados**, clique no campo, e então clique em **Adicionar**. Alternativamente, clique duas vezes no campo.
11. Após adicionar os campos desejados à lista **Campos selecionados**, verifique se o cursor está no lugar correto na planilha (por exemplo, célula A1), e em seguida clique em **Concluído**. Então clique em **Concluído** para sair do criador.
12. Clique em **Atualizar** para puxar um conjunto de dados.

## <a name="view-and-update-entity-data-in-excel"></a>Visualizar e atualizar dados da entidade no Excel
Depois que o suplemento do Excel realizar a leitura dos dados da entidade para a planilha, é possível atualizar os dados a qualquer momento clicando em **Atualizar** no suplemento.

## <a name="edit-entity-data-in-excel"></a>Editar dados da entidade no Excel
É possível alterar os dados da entidade conforme necessário e então publicá-los novamente clicando em **Publicar** no suplemento do Excel. Para editar um registro, selecione uma célula na planilha e então altere o valor da célula. Para adicionar um novo registro, siga uma dessas etapas:

-   Clique em qualquer lugar na planilha, e em seguida clique em **Novo** no suplemento do Excel.
-   Clique na última linha da planilha, e em seguida pressione a tecla Tab até que o cursor se mova além da última coluna dessa linha e uma nova linha seja criada.
-   Clique na linha imediatamente abaixo da planilha, e comece a inserir dados em uma célula. Ao mover o foco para fora da célula, a planilha se expande para incluir a nova linha.

Para excluir um registro, siga uma dessas etapas:

-   Clique com o botão direito no número da linha ao lado da linha da planilha a ser excluída, e em seguida clique em **Excluir**.
-   Clique com o botão direito na linha da planilha a ser excluída, e em seguida clique em **Excluir** &gt; **Linhas da tabela**.

## <a name="add-or-remove-columns"></a>Adicionar ou remover colunas
Você pode usar o criador para ajustar as colunas que são automaticamente adicionadas à planilha.

1.  Inicie o criador de fonte de dados do suplemento do Excel clicando no botão **Opções** (o botão da engrenagem) e selecionando a caixa **Habilitar design**.
2.  Clique em **Design** no suplemento do Excel. Todas as fontes de dados são listadas.
3.  Ao lado da fonte de dados, clique no botão **Editar** (o símbolo de lápis).
4.  Ajuste essa lista com a lista de **Campos selecionados** conforme necessário:
    -   Para adicionar um campo da lista **Campos disponíveis** à lista **Campos selecionados**, clique no campo, e então clique em **Adicionar**. Alternativamente, clique duas vezes no campo.
    -   Para remover um campo da lista **Campos selecionados**, clique no campo, e em seguida clique em **Remover**. Alternativamente, clique duas vezes no campo.
    -   Para alterar a ordem dos campos, clique no campo na lista **Campos selecionados**, e em seguida clique em **Para cima** ou **Para baixo**.

5.  Aplique suas alterações à fonte de dados clicando em **Atualizar**. Então clique em **Concluído** para sair do criador. Se você adicionou um campo (coluna), clique em **Atualizar** para puxar um conjunto de dados atualizados.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Solução de problemas
Existem alguns problemas que podem ser resolvidos através de algumas etapas simples.

-   **O botão Carregar applets está aparecendo.** Se o suplemento do Excel possui um botão **Carregar applets** depois do login, você provavelmente não está conectado como o usuário correto. Para resolver esse problema, verifique se o nome de usuário correto aparece no canto superior direito do suplemento do Excel. Caso um nome de usuário incorreto apareça, clique nele, finalize a sessão, e em seguida faça o login novamente.
-   **Você recebe uma mensagem "Proibido".** Se receber uma mensagem "Proibido" enquanto o suplemento do Excel estiver carregando metadados, a conta conectada no suplemento não possui permissão para usar o serviço, estância ou base de dados escolhida. Para resolver esse problema, verifique se o nome de usuário correto aparece no canto superior direito do suplemento do Excel. Caso um nome de usuário incorreto apareça, clique nele, finalize a sessão, e em seguida faça o login novamente.
-   **Uma página da Web em branco é exibida sobre o Excel.** Se uma página da Web em branco abre durante o processo de logon, a conta requer AD FS, mas a versão do Excel que está executando o suplemento não é recente o suficiente para carregar a caixa de diálogo do logon. Para resolver esse problema, atualize a versão do Excel utilizada. Para atualizar a versão do Excel em uma empresa que está no canal diferido, utilize a [ferramenta de implantação do Office](https://technet.microsoft.com/library/jj219422.aspx) para [mover do canal diferido para o canal atual](https://technet.microsoft.com/library/mt455210.aspx).


