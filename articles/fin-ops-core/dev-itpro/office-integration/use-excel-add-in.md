---
title: Exibir e atualizar dados da entidade com o Excel
description: Este artigo explica como abrir dados da entidade no Microsoft Excel e, em seguida, exibir, atualizar e editar esses dados usando o suplemento do Excel do Microsoft Dynamics.
author: jasongre
ms.date: 05/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 388be651164af622dbabd7b2c7b3437233454bea
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108591"
---
# <a name="view-and-update-entity-data-with-excel"></a>Exibir e atualizar dados da entidade com o Excel 

[!include [applies to](../includes/applies-to-commerce-finance-scm.md)]

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]


Este artigo explica como abrir dados da entidade no Microsoft Excel e, em seguida, exibir, atualizar e editar esses dados usando o suplemento do Excel do Microsoft Dynamics. Para abrir os dados da entidade, você pode iniciar pelo Excel ou pelos aplicativos de finanças e operações.

Ao abrir os dados da entidade no Excel, é possível visualizar e editar facilmente os dados utilizando o suplemento do Excel. Esse suplemento requer o Microsoft Excel 2016 ou posterior.

> [!NOTE]
> Se o seu locatário do Microsoft Azure Active Directory (Azure AD) estiver configurado para usar o Active Directory Federation Services (AD FS), você deverá garantir que a atualização de maio de 2016 para o Office tenha sido aplicada para que o suplemento do Excel consiga realizar seu logon corretamente.

Para saber mais sobre como usar o suplemento do Excel, assista ao breve vídeo [Criar um modelo do Excel para padrões de cabeçalho e de linha](https://youtu.be/RTicLb-6dbI).

## <a name="open-entity-data-in-excel-when-you-start-from-a-finance-and-operations-app"></a>Abrir dados da entidade no Excel ao iniciar um aplicativo de finanças e operações
1. Em uma página de um aplicativo de finanças e operações, selecione **Abrir no Microsoft Office**.

    Se a fonte de dados raiz (tabela) da página for a mesma que a fonte de dados raiz de qualquer entidade, opções **Abrir no Excel** padrões são geradas para a página. Opções **Abrir no Excel** podem ser encontradas em páginas frequentemente usadas, como **Todos os fornecedores** e **Todos os clientes**.
 
2. Selecione uma opção **Abrir no Excel**, e abra a pasta de trabalho gerada. Essa pasta de trabalho possui informações obrigatórias da entidade, um indicador para seu ambiente e um indicador para o suplemento do Excel.
3. No Excel, selecione **Habilitar edição** para permitir que o suplemento do Excel seja executado. O suplemento do Excel funciona em um painel do lado direito da janela do Excel.
4. Caso esteja executando o suplemento do Excel pela primeira vez, selecione **Confiar nesse Suplemento**.
5. Se for solicitado que você entre no sistema, selecione **Entrar** e use as mesmas credenciais do aplicativo de finanças e operações. O suplemento do Excel usará um contexto de entrada anterior do navegador e conectará você automaticamente, se possível. (Para obter informações sobre o navegador usado com base no sistema operacional, consulte [Navegadores usados por suplementos do Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)). Para garantir que a conexão foi bem-sucedida, verifique o nome de usuário no canto superior direito do suplemento do Excel. 

O suplemento do Excel lê automaticamente os dados da entidade selecionada. Observe que não haverá dados na pasta de trabalho até que o suplemento do Excel realize a leitura.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Abrir dados da entidade no Excel ao iniciar pelo Excel
1. No Excel, na guia **Inserir**, no grupo **Suplementos**, selecione **Loja** para abrir a Loja do Office.
2. Na Loja do Office, procure a palavra **Dynamics** e selecione **Adicionar** do lado de Suplemento do **Microsoft Dynamics Office** (o suplemento do Excel).
3. Caso esteja executando o suplemento do Excel pela primeira vez, selecione **Confiar nesse suplemento** para permitir que o suplemento funcione. O suplemento do Excel funciona em um painel do lado direito da janela do Excel.
4. Selecione **Adicionar informações do servidor** para abrir o painel **Opções**.
5. No seu navegador, copie a URL da instância desejada do aplicativo de finanças e operações, cole-a no campo **URL do Servidor** e, em seguida, exclua tudo que vem depois do nome do host. A URL resultante deve ter apenas o nome do host.

    Por exemplo, se a URL for `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`, exclua tudo, exceto `https://xxx.dynamics.com`.

6. Selecione **OK** e, depois, **Sim** para confirmar a alteração. O suplemento do Excel é reiniciado e carrega os metadados.

    O botão **Design** agora está disponível. Se o suplemento do Excel tiver um link **Carregar applets**, você provavelmente não será conectado como o usuário correto. Para obter mais informações sobre como resolver esse problema, consulte a entrada de solução de problemas [Carregar applets](../office-integration/office-integration-troubleshooting.md#issue-the-excel-add-in-loads-but-instead-of-showing-data-it-displays-load-applets-in-the-task-pane).

7. Selecione **Design**. O suplemento do Excel recupera metadados da entidade.
8. Selecionar **Adicionar tabela**. Uma lista de entidades aparece. As entidades são listadas no formato "Nome - Rótulo".
9. Selecionar uma entidade da lista, como **Cliente - Clientes** e selecionar **Próximo**.
10. Para adicionar um campo da lista **Campos disponíveis** à lista **Campos selecionados**, selecione o campo e **Adicionar**. Outra opção é clicar duas vezes no campo na lista **Campos disponíveis**.
11. Após adicionar os campos desejados à lista **Campos selecionados**, verifique se o cursor está no lugar correto na planilha (por exemplo, célula A1), e selecione **Concluído**. Selecione **Concluído** para sair do designer.
12. Selecione **Atualizar** para obter um conjunto de dados.

## <a name="view-and-update-entity-data-in-excel"></a>Visualizar e atualizar dados da entidade no Excel
Depois que o suplemento do Excel ler os dados da entidade na planilha, você poderá atualizar os dados a qualquer momento, selecionando **Atualizar** no suplemento do Excel.

## <a name="edit-entity-data-in-excel"></a>Editar dados da entidade no Excel
É possível alterar os dados da entidade conforme necessário e publicá-los novamente nos aplicativos de finanças e operações selecionando **Publicar** no suplemento do Excel. Para editar um registro, selecione uma célula na planilha e então altere o valor da célula. Para adicionar um novo registro, siga uma dessas etapas:

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

## <a name="change-the-publish-batch-size"></a>Alterar o tamanho do lote de publicação
Quando os usuários publicam alterações em registros de dados usando o suplemento do Excel, as atualizações são enviadas em lotes. O tamanho do lote de publicação padrão (e máximo) é de 100 linhas; porém, o recurso **Permitir configuração do tamanho do lote de publicação no suplemento do Excel** oferece flexibilidade para reduzir o tamanho do lote de publicação, especialmente se você estiver vendo tempos limite ao tentar publicar atualizações do Excel.

Os administradores do sistema podem especificar um limite de tamanho do lote de publicação em todo o sistema para pastas de trabalho "Abrir no Excel" configurando o campo **Limite do lote de publicação** na seção **Parâmetros do aplicativo** da página **Parâmetros do aplicativo Office**.

O tamanho do lote de publicação também pode ser alterado para uma pasta de trabalho individual usando o suplemento do Excel.

1. Abra a pasta de trabalho no Excel.
2. Selecione o botão **Opção** (engrenagem) na parte superior direita do suplemento do Excel.
3. Defina o campo **Tamanho do lote de publicação** conforme desejado. O valor definido deve ser menor do que o limite do lote de publicação em todo o sistema.
4. Selecione **OK**.
5. Salve a pasta de trabalho. Se você não salvar a pasta de trabalho depois de fazer alterações nas configurações do suplemento, essas alterações não serão mantidas quando a pasta de trabalho for reaberta.

Os autores de modelos de pastas de trabalho do Excel podem usar o mesmo procedimento para definir o tamanho do lote de publicação para modelos antes de carregá-los no sistema.

## <a name="copy-environment-data"></a>Copiar dados do ambiente

Os dados lidos na pasta de trabalho de um ambiente podem ser copiados para outro ambiente. Entretanto, você não pode apenas alterar a URL de conexão, pois o cache de dados na pasta de trabalho continuará a tratar os dados como dados existentes. Você deve usar a funcionalidade Copiar Dados do Ambiente para publicar os dados em um novo ambiente como novos dados.

1. Selecione o botão **Opções** (o símbolo de engrenagem) e, na Guia Rápida **Conector de Dados**, selecione **Copiar Dados do Ambiente**. 
2. Inserir a URL do servidor para o novo ambiente. 
3. Selecionar **OK** e, depois, **Sim** para confirmar a ação. O suplemento do Excel é reiniciado e conectado ao novo ambiente. Todos os dados existentes na pasta de trabalho são tratados como dados novos.

    Após o suplemento do Excel ser reiniciado, uma caixa de mensagem indica que a pasta de trabalho está no modo Cópia de ambiente.

4. Para copiar os dados no novo ambiente como novos dados, selecione **Publicar**. Para cancelar a operação de cópia do ambiente e rever os dados existentes no novo ambiente, selecione **Atualizar**.

## <a name="troubleshooting"></a>Solução de problemas
Existem alguns problemas que podem ser resolvidos através de algumas etapas simples.

- **O link "Carregar applets" é mostrado** – Para obter mais informações sobre como resolver esse problema, consulte a entrada de solução de problemas [Carregar applets](../office-integration/office-integration-troubleshooting.md#issue-the-excel-add-in-loads-but-instead-of-showing-data-it-displays-load-applets-in-the-task-pane). 
- **Você recebe uma mensagem "Proibido"** – Se receber uma mensagem "Proibido" enquanto o suplemento do Excel estiver carregando metadados, a conta conectada no suplemento não terá permissão para usar o serviço, a instância ou o banco de dados escolhido. Para resolver esse problema, verifique se o nome de usuário correto aparece no canto superior direito do suplemento do Excel. Caso um nome de usuário incorreto apareça, selecione-o, saia da sessão e entre novamente.
- **Uma página da Web em branco aparece no Excel** – se uma página da Web em branco for aberta durante o processo de logon, a conta exigirá AD FS, mas a versão do Excel que estiver executando o suplemento do Excel não será recente o suficiente para carregar a caixa de diálogo do logon. Para resolver esse problema, atualize a versão do Excel utilizada. Para atualizar a versão do Excel em uma empresa que está no canal diferido, utilize a [ferramenta de implantação do Office](/deployoffice/overview-office-deployment-tool) para [mover do canal diferido para o canal atual](/deployoffice/overview-update-channels).
- **Você recebe um tempo limite ao publicar alterações de dados** – Se você receber mensagens de tempo limite ao tentar publicar alterações de dados em uma entidade, considere a redução do tamanho do lote de publicação da pasta de trabalho afetada. As entidades que acionam quantidades maiores de lógica em alterações de registro podem exigir que atualizações sejam enviadas em lotes menores para ajudar a evitar tempos limites.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

