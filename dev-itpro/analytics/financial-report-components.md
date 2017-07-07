---
title: "Componentes de relatórios financeiros"
description: "Este artigo descreve como os componentes ou blocos de construção de definições de relatório são usados em relatórios financeiros. Esses blocos de construção incluem definições de linha, coluna e definições de árvore de relatórios. Este artigo explica como organizar blocos de construção de bloqueio e como trabalhar com grupos de bloco de construção."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5c09b1fc061f95cd78e9f18c2bdf846fdbfc7cf1
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017


---

# <a name="financial-report-components"></a>Componentes de relatórios financeiros

[!include[banner](../includes/banner.md)]


Este artigo descreve como os componentes ou blocos de construção de definições de relatório são usados em relatórios financeiros. Esses blocos de construção incluem definições de linha, coluna e definições de árvore de relatórios. Este artigo explica como organizar blocos de construção de bloqueio e como trabalhar com grupos de bloco de construção. 

A filosofia de design por trás do designer de relatórios financeiros é dividir informações no componente ou o bloco de construção, menor e, em seguida, mesclar e combinar os componentes conforme necessário. Portanto, a formatação do relatório é separada do seus dados financeiros e você pode alterar o design de um relatório sem modificar os dados financeiros no sistema Microsoft Dynamics ERP. Usando esta abordagem de bloco de construção, você pode combinar texto, valores e cálculos, para gerar os relatórios necessários. Além disso, esta flexibilidade incentiva a criatividade, facilitando a exibição de suas operações de diferentes formas. Os blocos de construção individuais de uma definição de relatório são semelhantes a uma planilha tridimensional, mas com mais potência. Uma definição de relatório especifica a definição de linha, a definição de coluna e a definição de árvore do relatório opcional a serem usadas para o relatório. Ela também inclui informações sobre onde armazenar o relatório gerado e como formatá-lo. Para melhorar a capacidade de reutilização e o compartilhamento, você pode criar um grupo do bloco de construção, que é um conjunto de definições de relatório existentes, definições de linha, definições de coluna, definições de árvore de relatórios e conjuntos de dimensões associados a uma empresa no.

## <a name="building-blocks-of-a-report"></a>Blocos de construção de um relatório
| Bloquear de construção            | Descrição                                                                                                                                                                                                                                                                              | Para obter mais informações                                                                                                 |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Definição de linha            | Uma definição de linha define as linhas descritivas em um relatório (por exemplo, salários ou vendas). Ela também lista os valores ou as dimensões de segmentos que contêm valores para cada item de linha, e inclui a formatação e os cálculos da linha.                                                    | [Definições de linha](row-definitions-financial-reporting.md)                       |
| Definição de coluna         | Uma definição de coluna define o período a ser usado ao extrair dados das dimensões financeiras. Ela também inclui a formatação e os cálculos da coluna.                                                                                                                                 | [Definições de coluna](column-definitions-financial-reports.md)         |
| Definição de árvore de relatórios | Uma definição de árvore de relatórios se parece com a um organograma. Ela contém unidades de relatório individuais que representam cada caixa no gráfico. As unidades podem ser departamentos individuais de dados financeiros ou unidades de nível superior que resumem dados de outras unidades de relatório. | [Definições de árvore de relatórios](financial-reporting-tree-definitions.md) |
| Definição de relatórios         | Uma definição de relatórios usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório. Ela também fornece opções e configurações adicionais para personalizar um relatório.                                                                    | [Definição de relatório](design-financial-report-definitions.md)                  |

Se você está começando a criar relatórios, convém usar o assistente de relatórios para criar rapidamente uma definição de relatório que possa ser personalizada depois. Se você tem experiência na criação de relatórios e deseja maior flexibilidade no projeto de relatório, pode combinar os blocos de construção novos ou existentes para criar uma nova definição de relatório. Você não precisa compreender totalmente todas as opções de definição de relatório disponíveis para gerar relatórios de qualidade. Ao familiarizar-se com a criação de relatórios, você pode expandir as definições de relatório para aproveitar mais recursos avançados. Depois de criar um relatório básico, você pode personalizar a definição de relatório e qualquer bloco de construção na definição de relatório.

## <a name="organize-the-building-blocks"></a>Organizar os blocos de construção
Use pastas para organizar seus blocos de construção no Designer de Relatórios. Todas as pastas são específicas do tipo de bloco de construção que elas contêm. Por exemplo, todas as pastas contendo definições de linha estão localizadas no painel **Definições de Linha** do Designer de Relatórios.

### <a name="create-a-folder"></a>Criar uma pasta

1.  No Designer de Relatórios, selecione o tipo de bloco de construção para organizar no painel de navegação. Por exemplo, para classificar uma definição de linha, clique em **Definições de Linha**.
2.  No painel de navegação, selecione a pasta existente para criar a nova pasta em, depois siga uma destas etapas:
    -   Clique com o botão direito do mouse na pasta pai e clique em **Nova Pasta**.
    -   Selecione a pasta pai e clique em **Arquivo**. Depois, clique em **Nova Pasta**.

3.  Quando a nova pasta aparecer, digite o nome dela e pressione Inserir.

## <a name="lock-a-building-block"></a>Bloquear um bloco de construção
Você pode criar uma senha para proteger e bloquear um bloco de construção. Desta forma você pode adicionar um nível de segurança a um componente de relatório sem proteger o sistema inteiro. Uma senha pode ajudar a proteger as informações do bloco de construção que são importantes para o processo de criação de relatório de fim de mês. Um usuário em qualquer função pode bloquear um bloco de construção. No entanto, outros usuários sempre têm acesso somente leitura a um componente bloqueado. Os usuários podem abrir, alterar e salvar o componente bloqueado com um novo nome. Um usuário com a função de administrador sempre pode acessar e alterar um bloco de construção bloqueado.
1.  No Designer de Relatórios, abra o componente do relatório a ser bloqueado, como uma definição de linha, uma definição de coluna, uma definição de relatório ou uma definição de árvore de relatórios.
2.  No menu **Ferramentas**, clique em **Proteger/Desproteger**. Você também pode clicar no ícone **Proteger/Desproteger** (um bloqueio) na barra de ferramentas.
3.  Na caixa de diálogo **Proteger**, insira e confirme uma senha, e clique em **OK**. O ícone de bloqueio na barra de ferramentas é realçado quando um bloco de construção aberto é bloqueado.

Para desbloquear um bloco de construção bloqueado, abra-o e clique no ícone **Proteger/Desproteger** na barra de ferramentas. De forma alternativa, no menu **Ferramentas**, clique em **Desproteger**.

## <a name="building-block-groups"></a>Grupos do Bloco de Construção

Os blocos de construção são as definições linha, definições de coluna, definições de árvore de relatórios e definições de relatório que você pode criar para um relatório. Os grupos do bloco de construção são coleções dos conjuntos de definições e dimensões que estão associados a uma empresa. Os grupos do bloco de construção podem ser específicos da empresa, ou várias empresas podem compartilhar o mesmo conjunto de blocos de construção. Se você tiver as empresas com um plano de contas diferente, poderá usar um grupo diferente de bloco de construção para cada empresa. Como alternativa, você pode nomear todos os blocos de construção individuais para refletir a empresa com que eles são compatíveis.
### <a name="create-a-building-block-group"></a>Criar um grupo do bloco de construção

1.  No Designer de Relatórios, no menu **Empresa**, clique em **Grupos do Bloco de Construção**.
2.  Na caixa de diálogo **Grupos do bloco de construção**, clique em **Novo**.
3.  Insira um nome exclusivo e uma descrição para o grupo do bloco de construção. Cada campo pode conter, no máximo, 256 caracteres. (Esse número inclui espaços.)
4.  Clique em **OK** para criar um novo grupo do bloco de construção.

### <a name="assign-a-building-block-group"></a>Atribuir um grupo do bloco de construção

Depois de criar um grupo de blocos, você deve atribuí-lo a pelo menos uma empresa. É possível criar definições de relatório, de linha, de coluna e de árvore de relatórios, e salvá-las no grupo do bloco de construção. Você deve fechar todos os blocos de construção antes de começar o procedimento a seguir.
1.  No Designer de Relatórios, no menu **Empresa**, clique em **Empresas**.
2.  Na caixa de diálogo **Empresas**, selecione a empresa à qual você está atribuindo um grupo de bloco de construção.
3.  Clique em **Modificar**.
4.  Na caixa de diálogo **Modificar Empresa**, no campo **Grupo do bloco de construção**, selecione o grupo do bloco de construção para atribuir a empresa, ou clique em **Novo** para criar um novo grupo do bloco de construção.
5.  Clique em **OK** para atribuir o grupo do bloco de construção.
6.  Clique em **Fechar** para fechar a caixa de diálogo **Empresas**. Agora, o grupo do bloco de construção selecionado é atribuído à empresa. Todas as definições de linha, definições de coluna e outras recém-geradas farão parte do grupo do bloco de construção atribuído a essa empresa. Também é possível importar um arquivo .tdbx ou relatório de outro sistema.

### <a name="view-a-building-block-group"></a>Exibir um grupo do bloco de construção

Depois que um grupo de bloco de construção foi criado e está sendo usado, você pode exibir todos os blocos de construção são atribuídos a ele. Você também pode exportar ou importar um grupo de blocos de construção e manutenção adicionais no bloco de construção de grupos.
1.  No Designer de Relatórios, no menu **Empresa**, clique em **Grupos do Bloco de Construção**.
2.  Na caixa de diálogo **Grupos do Bloco de Construção**, selecione o bloco de construção para exibir.
3.  Clique em **Exibir** para abrir a caixa de diálogo **Exibir Grupo do Bloco de Construção** e para exibir o conteúdo do grupo do bloco de construção.
4.  Clique em **Fechar** para fechar as caixas de diálogo.

### <a name="save-a-building-block-group-under-a-new-name"></a>Salvar um grupo do bloco de construção usando um novo nome

Você pode salvar um grupo do bloco de construção existente usando um novo nome. Depois, pode modificar o novo grupo do bloco de construção sem alterar o grupo original do bloco de construção.
1.  No Designer de Relatórios, no menu **Empresa**, clique em **Grupos do Bloco de Construção**.
2.  Na caixa de diálogo **Grupos do Bloco de Construção**, selecione o grupo do bloco de construção a ser salvo usando um novo nome.
3.  Clique em **Salvar Como**.
4.  Insira um novo nome e uma descrição para o grupo do bloco de construção.
5.  Clique em **OK**. O novo grupo do bloco de construção aparece na caixa de diálogo **Grupos do Bloco de Construção**.

### <a name="export-a-building-block-group"></a>Exportar um grupo do bloco de construção

Você pode exportar um grupo de bloco de construção ou blocos de construção específicos de relatório em um grupo de bloco de construção. Você pode usar o grupo exportado de blocos de construção como um backup. Você também poderá copiar os dados exportados entre grupos de blocos de construção ou instalações do Finance and Operations. O designer de relatórios tem os estilos de fontes referenciados e os conjuntos de dimensões junto com o grupo do bloco de construção.
1.  No Designer de Relatórios, no menu **Empresa**, clique em **Grupos do Bloco de Construção**.
2.  Na caixa de diálogo **Grupos do Bloco de Construção**, selecione o grupo do bloco de construção para exportação. Depois, clique em **Exportar**.
3.  Na caixa de diálogo **Exportar**, selecione as definições de relatório para exportação:
    -   Para exportar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar Tudo**.
    -   Para exportar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, clique na guia apropriada e selecione os itens a serem exportados. Pressione e mantenha pressionada a tecla Ctrl para selecionar vários itens em uma guia. **Observação:** Quando você seleciona relatórios para exportação, as linhas, colunas, árvores e conjuntos de dimensões associados são selecionados.

4.  Quando você acabar de selecionar itens para exportação, clique em **Exportar**.
5.  Na caixa de diálogo **Salvar Como**, selecione um local para exportar o grupo do bloco de construção.
6.  No campo **Nome do Arquivo**, digite um nome para o arquivo. O designer de relatórios adiciona automaticamente um nome de arquivo com a extensão .tdbx.
7.  Clique em **Salvar**. O grupo do bloco de construção é salvo no local que você especificou.

### <a name="import-a-building-block-group"></a>Importar um grupo do bloco de construção

Você pode importar um grupo de blocos de construção para um grupo de blocos de construção existente, ou você pode criar um novo grupo de bloco de construção para os dados. Todos os grupos de bloco de construção importados mantêm seus estilos de fonte original e referências de empresa e incluem os conjuntos de dimensão relevante.
1.  No Designer de Relatórios, no menu **Empresa**, clique em **Grupos do Bloco de Construção**.
2.  Na caixa de diálogo **Grupos do Bloco de Construção**, selecione o grupo do bloco de construção para importar um grupo de bloco de construção. Depois, clique em **Importar**.
3.  Na caixa de diálogo **Abrir**, selecione o grupo do bloco de construção para importação. Depois, clique em **Abrir**.
4.  Na caixa de diálogo **Importar**, selecione as definições de relatório para importação:
    -   Para importar todas as definições de relatório e os blocos de construção de suporte, clique em **Selecionar Tudo**.
    -   Para importar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, selecione os relatórios, as linhas, as colunas, as árvores ou os conjuntos de dimensões a serem importados.

5.  Quando você acabar de selecionar itens para importação, clique em **Importar**.

### <a name="undo-a-checkout-of-a-building-block"></a>Desfazer o check-out de um bloco de construção

Quando você abre um bloco de construção, outros usuários só podem acessar o bloco de construção no modo somente leitura. Às vezes, um usuário se esquece de fechar um bloco de construção ou desliga o sistema sem fechar o bloco de construção. Como resultado, é feito o check-out do bloco de construção e outros usuários não podem abri-lo. Nessas situações, um administrador do relatório financeiro pode usar a caixa de diálogo **Itens com Check-out** para efetuar check-in em blocos de construção que um usuário tenha deixado com status check-out. **Observação:** Você deve usar a função administrador para efetuar check-in em blocos de construção da caixa de diálogo **Itens com Check-out**.
1.  No Designer de Relatórios, no menu **Ferramentas**, clique em **Itens com Check-out**.
2.  Na caixa de diálogo **Itens com Check-out**, selecione **Mostrar itens de todos os usuários**. A lista é atualizada para exibir todos os blocos de construção com check-out e os usuários que efetuaram o check-out.
3.  Selecione um bloco de construção e clique em **Desfazer Check-out**.
4.  Clique em **Sim** para efetuar check-in no bloco de construção.

# <a name="see-also"></a>Consulte também

[Relatórios financeiros](financial-reporting-intro.md)




