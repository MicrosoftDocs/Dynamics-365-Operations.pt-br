---
title: Utilizar o suplemento do Excel
description: "Este tópico explica como abrir dados da entidade no Microsoft Excel, e então visualizar, atualizar e editar os dados usando o suplemento do Microsoft Dynamics Office para Excel."
author: ChrisGarty
manager: AnnBe
ms.date: 11/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: f3ed06dbbce21ac093107953d3a72d8ab086af2a
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="use-the-excel-add-in"></a>Utilizar o suplemento do Excel

[!include[banner](../includes/banner.md)]

Este tópico explica como abrir dados da entidade no Microsoft Excel, e então visualizar, atualizar e editar os dados usando o suplemento do Microsoft Dynamics Office para Excel. Para abrir os dados da entidade, você pode começar pelo Excel ou pelo Microsoft Dynamics 365 for Finance and Operations.

Ao abrir os dados da entidade no Excel, é possível visualizar e editar facilmente os dados utilizando o suplemento do Excel. Este suplemento requer o Microsoft Excel 2016.

> [!NOTE]
> Se o seu inquilino do Microsoft Azure Active Directory (Azure AD) está configurado para usar o Active Directory Federation Services (AD FS), você deve garantir que a atualização de maio de 2016 do Office seja aplicada, para que o suplemento do Excel consiga realizar seu login corretamente.

## <a name="open-entity-data-in-excel-when-you-start-from-finance-and-operations"></a>Abrir dados da entidade no Excel ao iniciar do Finance and Operations
1. Em uma página no Finance and Operations, selecione **Abrir no Microsoft Office**.

    Se a fonte de dados raiz (tabela) da página for a mesma que a fonte de dados raiz de qualquer entidade, opções **Abrir no Excel** padrões são geradas para a página. Opções **Abrir no Excel** podem ser encontradas em páginas frequentemente usadas, como **Todos os fornecedores** e **Todos os clientes**.
 
2. Selecione uma opção **Abrir no Excel**, e abra a pasta de trabalho gerada. Essa pasta de trabalho possui informações obrigatórias da entidade, um indicador para seu ambiente e um indicador para o suplemento do Excel.
3. No Excel, selecione **Habilitar edição** para permitir que o suplemento do Excel seja executado. O suplemento do Excel funciona em um painel do lado direito da janela do Excel.
4. Caso esteja executando o suplemento do Excel pela primeira vez, selecione **Confiar nesse Suplemento**.
5. Se for solicitado a entrar, selecione **Entrar** e use as mesmas credenciais usadas para entrar no Finance and Operations. O suplemento do Excel usará um contexto de entrada anterior do Internet Explorer e conectará você automaticamente, se possível. Portanto, verifique o nome de usuário no canto superior direito do suplemento do Excel.

O suplemento do Excel lê automaticamente os dados da entidade selecionada. Observe que não haverá dados na pasta de trabalho até que o suplemento do Excel realize a leitura.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Abrir dados da entidade no Excel ao iniciar pelo Excel
1. No Excel, na guia **Inserir**, no grupo **Suplementos**, selecione **Loja** para abrir a Loja do Office.
2. Na Loja do Office, procure a palavra **Dynamics** e selecione **Adicionar** ao lado de **Suplemento do Microsoft Dynamics Office** (o suplemento do Excel).
3. Caso esteja executando o suplemento do Excel pela primeira vez, selecione **Confiar nesse suplemento** para permitir que o suplemento funcione. O suplemento do Excel funciona em um painel do lado direito da janela do Excel.
4. Selecione **Adicionar informações do servidor** para abrir o painel **Opções**.
5. No seu navegador, copie a URL da instância desejada do Finance and Operations, cole-a no campo **URL do Servidor** e, em seguida, exclua tudo após o nome do host. A URL resultante deve ter apenas o nome do host.

    Por exemplo, se a URL for `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`, exclua tudo, exceto `https://xxx.dynamics.com`.

6. Selecione **OK** e, depois, **Sim** para confirmar a alteração. O suplemento do Excel é reiniciado e carrega os metadados.

    O botão **Design** agora está disponível. Se o suplemento do Excel possuir um botão **Carregar applets**, você provavelmente não está conectado como o usuário correto. Para obter mais informações, consulte "O botão Carregar applets está aparecendo" na seção [Solução de Problemas"](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in#troubleshooting) desse tópico.

7. Selecionar **Design**. O suplemento do Excel recupera metadados da entidade.
8. Selecionar **Adicionar tabela**. Uma lista de entidades aparece. As entidades são listadas no formato "Nome - Rótulo".
9. Selecionar uma entidade da lista, como **Cliente - Clientes** e selecionar **Próximo**.
10. Para adicionar um campo da lista **Campos disponíveis** à lista **Campos selecionados**, selecione o campo e **Adicionar**. Outra opção é clicar duas vezes no campo na lista **Campos disponíveis**.
11. Após adicionar os campos desejados à lista **Campos selecionados**, verifique se o cursor está no lugar correto na planilha (por exemplo, célula A1), e selecione **Concluído**. Selecione **Concluído** para sair do designer.
12. Selecione **Atualizar** para obter um conjunto de dados.

## <a name="view-and-update-entity-data-in-excel"></a>Visualizar e atualizar dados da entidade no Excel
Depois que o suplemento do Excel ler os dados da entidade na planilha, você poderá atualizar os dados a qualquer momento, selecionando **Atualizar** no suplemento do Excel.

## <a name="edit-entity-data-in-excel"></a>Editar dados da entidade no Excel
É possível alterar os dados da entidade conforme necessário e publicá-los novamente selecionando **Publicar** no suplemento do Excel. Para editar um registro, selecione uma célula na planilha e então altere o valor da célula. Para adicionar um novo registro, siga uma dessas etapas:

- Clique em qualquer local na tabela de fontes de dados e selecione **Novo** no suplemento do Excel.
- Clique em qualquer ponto da última linha da tabela de fontes de dados, e pressione a tecla Tab até que o cursor se mova da última coluna dessa linha e uma nova linha seja criada.
- Clique em qualquer ponto na linha logo abaixo da tabela de fontes de dados e comece a inserir dados em uma célula. Ao mover o foco para fora da célula, a tabela se expande para incluir a nova linha.
- Para associações de campo dos registros do cabeçalho, selecione um dos campos e **Novo** no suplemento do Excel.

Observe que um novo registro pode ser criado apenas se todos os campos obrigatórios e de chave forem associados na planilha, ou se os valores padrão forem preenchidos usando a condição do filtro.

Para excluir um registro, siga uma dessas etapas:

- Clique com o botão direito no número da linha ao lado da linha da planilha a ser excluída e selecione **Excluir**.
- Clique com o botão direito em qualquer ponto da linha da planilha a ser excluída e selecione **Excluir** &gt; **Linhas da Tabela**.

Se as fontes de dados foram adicionadas como fontes de dados relacionadas, o cabeçalho será publicado antes das linhas. Se houver dependências entre outras fontes de dados, você terá que alterar a ordem de publicação padrão. Para alterar a ordem de publicação, no suplemento do Excel, selecione o botão **Opções** (o símbolo de engrenagem) e, na Guia Rápida **Connector de Dados**, selecione **Configurar ordem publicada**.

## <a name="add-or-remove-columns"></a>Adicionar ou remover colunas
Você pode usar o criador para ajustar as colunas que são automaticamente adicionadas à planilha.

> [!NOTE]
> Se o botão **Design** não aparecer abaixo do botão **Filtro** no suplemento do Excel, habilite o designer de fonte de dados. Selecione o botão **Opções** (o símbolo de engrenagem), e marque a caixa de seleção **Habilitar design**.

1. No suplemento do Excel, selecione **Design**. Todas as fontes de dados são listadas.
2. Ao lado da fonte de dados, selecione o botão **Editar** (o símbolo de lápis).
3. Na lista **Campos selecionados**, ajuste a lista de campos conforme necessário:

    - Para adicionar um campo da lista **Campos disponíveis** à lista **Campos selecionados**, selecione o campo e **Adicionar**. Outra opção é clicar duas vezes no campo na lista **Campos disponíveis**.
    - Para remover um campo da lista **Campos selecionados**, selecione o campo e **Remover**. Alternativamente, clique duas vezes no campo.
    - Para alterar a ordem dos campos na lista **Campos selecionados**, selecione um campo e, depois, **Para cima** ou **Para baixo**.

4. Para aplicar suas alterações à fonte de dados, selecione **Atualizar**. Selecione **Concluído** para sair do designer.
5. Se você adicionou um campo (coluna), selecione **Atualizar** para obter um conjunto de dados atualizados.

## <a name="copy-environment-data"></a>Copiar dados do ambiente

Os dados lidos na pasta de trabalho de um ambiente podem ser copiados para outro ambiente. Entretanto, você não pode apenas alterar a URL de conexão, pois o cache de dados na pasta de trabalho continuará a tratar os dados como dados existentes. Você deve usar a funcionalidade Copiar Dados do Ambiente para publicar os dados em um novo ambiente como novos dados.

1. Selecione o botão **Opções** (o símbolo de engrenagem) e, na Guia Rápida **Conector de Dados**, selecione **Copiar Dados do Ambiente**. 
2. Inserir a URL do servidor para o novo ambiente. 
3. Selecionar **OK** e, depois, **Sim** para confirmar a ação. O suplemento do Excel é reiniciado e conectado ao novo ambiente. Todos os dados existentes na pasta de trabalho são tratados como dados novos.

    Após o suplemento do Excel ser reiniciado, uma caixa de mensagem indica que a pasta de trabalho está no modo Cópia de ambiente.

4. Para copiar os dados no novo ambiente como novos dados, selecione **Publicar**. Para cancelar a operação de cópia do ambiente e rever os dados existentes no novo ambiente, selecione **Atualizar**.

## <a name="troubleshooting"></a>Solução de problemas
Existem alguns problemas que podem ser resolvidos através de algumas etapas simples.

- **O botão Carregar applets aparece** – Se o suplemento do Excel possui um botão **Carregar applets** depois do login, você provavelmente não está conectado como o usuário correto. Para resolver esse problema, verifique se o nome de usuário correto aparece no canto superior direito do suplemento do Excel. Caso um nome de usuário incorreto apareça, selecione-o, saia da sessão e entre novamente.
- **Você recebe uma mensagem "Proibido"** – Se receber uma mensagem "Proibido" enquanto o suplemento do Excel estiver carregando metadados, a conta conectada no suplemento não terá permissão para usar o serviço, a instância ou o banco de dados escolhido. Para resolver esse problema, verifique se o nome de usuário correto aparece no canto superior direito do suplemento do Excel. Caso um nome de usuário incorreto apareça, selecione-o, saia da sessão e entre novamente.
- **Uma página da Web em branco aparece no Excel** – Se uma página da Web em branco for aberta durante o processo de logon, a conta exigirá AD FS, mas a versão do Excel que estiver executando o suplemento do Excel não será recente o suficiente para carregar a caixa de diálogo do logon. Para resolver esse problema, atualize a versão do Excel utilizada. Para atualizar a versão do Excel em uma empresa que está no canal diferido, utilize a [ferramenta de implantação do Office](https://technet.microsoft.com/library/jj219422.aspx) para [mover do canal diferido para o canal atual](https://technet.microsoft.com/library/mt455210.aspx).

