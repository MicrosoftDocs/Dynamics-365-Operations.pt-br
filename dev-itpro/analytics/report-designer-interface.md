---
title: "Interface do Designer de Relatórios"
description: "Este artigo explica como navegar através do Designer de relatórios e como usar as diversas opções para atender a necessidades específicas."
author: RobinARH
manager: AnnBe
ms.date: 2016-03-07 18 - 50 - 10
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59041
ms.assetid: 054de5b0-8618-4195-be12-f031b4bb4d74
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 58c56aca6f339a5ec13703605334dd45b208ab2c
ms.lasthandoff: 03/29/2017


---

# <a name="report-designer-interface"></a>Interface do Designer de Relatórios

Este artigo explica como navegar através do Designer de relatórios e como usar as diversas opções para atender a necessidades específicas. 

<a name="report-designer-menu-commands"></a>Comandos de menu do Designer de Relatórios
-----------------------------

As tabelas a seguir descrevem os comandos de menu e as opções que podem ser usadas quando você cria relatórios financeiros. Alguns comandos de menu e opções estão disponíveis apenas em condições específicas. Por exemplo, os comandos para promover e rebaixar unidades de relatório estão disponíveis somente quando você está modificando uma definição de árvore do relatório.

### <a name="file-menu"></a>Menu Arquivo

O menu **Arquivo** está disponível a todos os usuários e inclui os comandos a seguir.

| Comando                           | Descrição                                                                                                                                                                                      |
|-----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Novo                               | Criar uma nova definição de relatório, definição de linha, definição de coluna, definição de árvore de relatório, definição de grupo de relatórios ou pasta. Opções adicionais estão disponíveis, dependendo da sua função de usuário. |
| Abertas                              | Abrir uma definição de linha existente, definição de coluna, definição de árvore de relatórios ou definição de relatório.                                                                                             |
| Fechar                             | Fechar o bloco de construção atual.                                                                                                                                                                |
| Fechar Tudo                         | Fechar todos os blocos de construção.                                                                                                                                                                       |
| Salvar                              | Salvar a definição de linha atual, definição de coluna, definição de árvore de relatórios ou definição de relatório.                                                                                             |
| Salvar como                           | Salvar a definição de linha atual, definição de coluna, definição de árvore de relatórios ou definição de relatório com um novo nome.                                                                            |
| Propriedades                        | Abrir a caixa de diálogo **Propriedades**, na qual você pode alterar o nome e a descrição de um relatório.                                                                                                   |
| Gerar                          | Gerar o relatório atual. Este comando está disponível em uma definição de relatório.                                                                                                                 |
| Exibir Relatório                       | Abre a versão mais recente do relatório gerado em dynamics 365 para as operações. Este comando está disponível em uma definição de relatório se você gerou pelo menos um relatório.                                 |
| Definições de Relatório Recentes         | Mostrar uma lista de relatórios que foram criados ou alterados recentemente. Você pode selecionar um relatório na lista.                                                                                    |
| Definições de Linha Recentes            | Mostrar uma lista de definições de linha que foram criadas ou alteradas recentemente. Você pode selecionar uma definição de linha na lista.                                                                    |
| Definições de Coluna Recentes         | Mostrar uma lista de definições de coluna que foram criadas ou alteradas recentemente. Você pode selecionar uma definição de coluna na lista.                                                              |
| Definições de Árvore de Relatórios Recentes | Mostrar uma lista de definições de árvore de relatório que foram criadas ou alteradas recentemente. Você pode selecionar uma definição de árvore de relatório na lista.                                              |
| Sair                              | Sair do Designer de Relatórios.                                                                                                                                                                            |

### <a name="edit-menu"></a>Menu Editar

O menu **Editar** está disponível para usuários com a função **Designer** ou **Administrador**. Este menu inclui os comandos a seguir.

| Comando                                | Descrição                                                                                                                                                                                                        |
|----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Desfazer                                   | Desfazer a última ação.                                                                                                                                                                                              |
| Refazer                                   | Reverter a última ação desfeita.                                                                                                                                                                                      |
| Recortar                                    | Excluir o texto selecionado e copiá-lo na área de transferência.                                                                                                                                                            |
| Copiar                                   | Copiar o texto selecionado na área de transferência.                                                                                                                                                                           |
| Colar                                  | Inserir o texto cortado ou copiado recentemente da área de transferência.                                                                                                                                                    |
| Limpar                                  | Excluir o conteúdo da célula selecionada do bloco de construção.                                                                                                                                                           |
| Localizar                                   | Abra a caixa de diálogo **Localizar e Substituir**, na qual você pode pesquisar o texto no painel de exibição.                                                                                                                              |
| Substituir                                | Abra a caixa de diálogo **Localizar e Substituir**, na qual você pode pesquisar e substituir o texto no painel de exibição.                                                                                                                  |
| Inserir Linhas de Dimensões            | Abra a caixa de diálogo **Inserir Linhas de Dimensões**, na qual você pode selecionar os valores de dimensão a serem incluídos na definição de linha. Este comando está disponível em uma definição de linha.                                  |
| Renumerar Linhas                          | Renumerar todos os códigos numéricos de linha. Este comando está disponível em uma definição de linha.                                                                                                                                   |
| Links de Linhas                              | Abra a caixa de diálogo **Links de Linhas**, na qual você pode especificar as origens de definições de links de dados e as definições de árvores de relatórios. Este comando está disponível em uma definição de linha.                            |
| Ajuste de Arredondamento                    | Abra a caixa de diálogo **Ajustes de Arredondamento**, na qual você pode especificar os parâmetros para arredondamento. Este comando está disponível em uma definição de linha.                                                                  |
| Gerenciar Conjuntos de Dimensões                  | Abra a caixa de diálogo **Conjuntos de Dimensões**, na qual você pode criar e modificar conjuntos de dimensões. Este comando está disponível em uma definição de linha ou definição de árvore de relatórios.                                              |
| Inserir Linha                             | Inserir uma linha em branco na definição de linha ou uma linha de cabeçalho em branco na definição de coluna. Este comando está disponível em uma definição de linha ou definição de coluna.                                               |
| Excluir Linha                             | Excluir a linha selecionada da definição de linha ou a linha de cabeçalho selecionada da definição de coluna. Este comando está disponível em uma definição de linha ou definição de coluna.                                       |
| Inserir Coluna                          | Inserir uma coluna vazia na definição de coluna. Este comando está disponível em uma definição de coluna.                                                                                                             |
| Excluir Coluna                          | Excluir a coluna selecionada da definição de coluna. Este comando está disponível em uma definição de coluna.                                                                                                         |
| Inserir Unidades de Relatório de Dimensões | Abra a caixa de diálogo **Inserir Unidades de Relatório de Dimensões**, na qual você pode selecionar os valores de dimensão a serem incluídos na definição de árvore de relatórios. Este comando está disponível em uma definição de árvore de relatórios. |
| Importar Hierarquia de Conjunto de Dimensões         | Abra a caixa de diálogo **Hierarquia de Conjunto de Dimensões**, na qual você pode importar uma hierarquia de conjunto de dimensões dos dados financeiros. Esse comando está disponível em uma definição de hierarquia organizacional a A. \ \ com dimensões financeiras com o sistema.  |
| Inserir Unidade de Relatórios                  | Inserir uma linha em branco na definição de árvore de relatórios. Este comando está disponível em uma definição de árvore de relatórios.                                                                                                |
| Excluir Unidade de Relatórios                  | Excluir a linha da unidade de relatórios selecionada da definição de árvore de relatórios. Este comando está disponível em uma definição de árvore de relatórios.                                                                             |

### <a name="view-menu"></a>Menu exibir

O menu **Exibir** está disponível para todos os usuários e inclui os comandos a seguir.

| Comando         | Descrição                                                            |
|-----------------|------------------------------------------------------------------------|
| Painel de Navegação | Exibir ou ocultar o painel de navegação.                                      |
| Barras de ferramentas        | Selecionar as barras de ferramentas que são visíveis.                                  |
| Barra de Status      | Mostrar ou ocultar as informações de status na janela **Designer de Relatórios**. |
| Página Inicial    | Abrir a página **Bem-vindo**.                                             |

### <a name="format-menu"></a>Menu Formatar

O menu **Formatar** está disponível para usuários com a função **Designer** ou **Administrador**. Este menu inclui os comandos a seguir.

| Comando               | Descrição                                                                                                                                                                                                          |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Estilos e Formatação | Abra a caixa de diálogo **Estilos e Formatação**, na qual você pode criar e modificar o estilo do texto em definições de linha e definições da coluna. Este comando está disponível em uma definição de linha ou definição de coluna. |
| Largura da Coluna          | Abra a caixa de diálogo **Largura da Coluna**, na qual você pode definir a largura da coluna selecionada. Este comando está disponível em uma definição de linha, definição de coluna ou definição de árvore de relatórios.                      |
| Ocultar                  | Ocultar a coluna selecionada. Este comando está disponível em uma definição de linha, definição de coluna ou definição de árvore de relatórios.                                                                                        |
| Reexibir                | Torne as colunas ocultas entre as colunas selecionadas visíveis. Este comando está disponível em uma definição de linha, definição de coluna ou definição de árvore de relatórios.                                                      |

### <a name="company-menu"></a>Menu Empresa

O menu **Empresa** está disponível para usuários com a função **Designer** ou **Administrador**. Este menu inclui os comandos a seguir.

| Comando               | Descrição                                                                                                            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------|
| Empresas             | Abra a caixa de diálogo **Empresas**, na qual você pode criar e modificar empresas.                                          |
| Grupos do Bloco de Construção | Abra a caixa de diálogo **Grupos do Bloco de Construção**, na qual é possível criar, modificar, importar exportar grupos do bloco de construção. |

### <a name="go-menu"></a>Menu Ir

O menu **Ir** está disponível para todos os usuários e inclui os comandos a seguir. **Observação:** Estes comandos não têm efeito visível, a menos que o painel de navegação esteja visível.

| Comandos                   | Descrição                                                                        |
|----------------------------|------------------------------------------------------------------------------------|
| Definições de Relatório         | Mostrar definições de relatório no painel de navegação.                                    |
| Definições de Linha            | Mostrar definições de linha no painel de navegação.                                       |
| Definições de Coluna         | Mostrar definições de coluna no painel de navegação.                                    |
| Definições de Árvore de Relatórios | Mostrar definições de árvore de relatórios no painel de navegação.                            |
| Segurança                   | Mostrar informações de segurança para usuários, grupos e empresas no painel de navegação. |

### <a name="tools-menu"></a>Menu Ferramentas

O menu **Ferramentas** está disponível para todos os usuários, mas alguns comandos têm disponibilidade limitada. Este menu inclui os comandos a seguir.

| Comando                       | Descrição                                                                                                                                                                                                       |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Proteger                       | Aplicar uma senha ao bloco de construção atual. Este comando está disponível para usuários com a função **Designer** ou **Administrador**.                                                                           |
| Status da Fila de Relatórios           | Abra a caixa de diálogo **Status da Fila de Relatórios**, na qual você pode ver todos os relatórios gerados recentemente e os detalhes de cada relatório.                                                                                    |
| Informações do Sistema de Origem     | Mostrar as configurações do sistema ERP do Microsoft Dynamics. Este comando está disponível para usuários com a função **Designer** ou **Administrador**.                                                                 |
| Itens Verificados             | Mostrar as definições de linha, definições de coluna, definições de árvore de relatórios e definições de relatório que estão abertas no momento. Este comando está disponível para usuários com a função **Designer** ou **Administrador**. |
| Atualizar Dados Financeiros em Cache | Atualizar os dados na coluna de dimensões financeiras.                                                                                                                                                               |
| Opções                       | Abra a caixa de diálogo **Opções**, na qual você pode mudar as preferências de usuário para o Designer de Relatórios.                                                                                                                       |

### <a name="window-menu"></a>Menu Janela

O menu **Janela** está disponível para todos os usuários e inclui os comandos a seguir.

| Comando              | Descrição                                                                                                                                                                                   |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Lado a lado horizontalmente    | Mostrar todas as janelas abertas, uma ao lado da outra.                                                                                                                                                     |
| Lado a lado verticalmente      | Mostrar todas as janelas abertas, uma sobre a outra.                                                                                                                                               |
| Cascata              | Dispor em camadas todas as janelas abertas, de forma que a barra de título de cada janela fique visível.                                                                                                                      |
| Congelar Horizontal    | Congelar a linha selecionada de forma que, ao rolar a tela, essa linha continue visível na janela. Este comando está disponível para usuários com a função **Designer** ou **Administrador**.       |
| Congelar Vertical      | Congelar a coluna selecionada de forma que, ao rolar a tela, essa coluna continue visível na janela. Este comando está disponível para usuários com a função **Designer** ou **Administrador**. |
| Lista de Janelas Abertas | Mostrar uma lista de janelas que estão abertas. Selecione uma janela para colocá-la na frente.                                                                                                               |

### <a name="help-menu"></a>Menu de Ajuda

O menu **Ajuda** está disponível para todos os usuários e inclui os comandos a seguir.

| Comando | descrição                                                  |
|---------|--------------------------------------------------------------|
| Ajuda    | Abra o dynamics 365 para a página de wiki de ajuda de operações para relatórios financeiros. |
|         |                                                              |

## <a name="report-designer-toolbar-buttons"></a>Botões da barra de ferramentas do Designer de Relatórios
As tabelas a seguir descrevem os botões da barra de ferramentas que você pode usar quando cria relatórios. Alguns botões da barra de ferramentas estão disponíveis apenas em condições específicas. Por exemplo, os botões para promover e rebaixar unidades de relatório estão disponíveis somente quando você está modificando uma definição de árvore de relatório.

### <a name="standard-toolbar"></a>Barra de ferramentas padrão

A barra de ferramentas padrão fornece acesso rápido aos comandos Arquivo e Editar. Esta barra de ferramentas inclui os botões a seguir.

| Botão                                                                                                                                                                                   | Descrição                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [![New button](./media/rowc130389.png)](./media/rowc130389.png)                              | Criar uma definição de relatório nova (vazia), definição de linha, definição de coluna ou definição de árvore de relatórios.                                                                               |
| [botão abertos![(]. /media/openfolderc130389.png)](. /media/openfolderc130389.png)               | Abrir uma definição de linha existente, definição de coluna, definição de árvore de relatórios ou definição de relatório.                                                                                   |
| [botão de salvar![(]. /media/savec130389.png)](. /media/savec130389.png)                           | Salvar a definição de linha atual, definição de coluna, definição de árvore de relatórios ou definição de relatório.                                                                                   |
| [botão copiar![(]. /media/copyc130389.png)](. /media/copyc130389.png)                           | Copiar o texto selecionado na área de transferência.                                                                                                                                               |
| [botão de corte![(]. /media/cutc130389.png)](. /media/cutc130389.png)                              | Excluir o texto selecionado e copiá-lo na área de transferência.                                                                                                                                |
| [botão![pasta (![]. /media/pastec130389.png)](. /media/pastec130389.png)                        | Inserir o texto da área de transferência.                                                                                                                                                    |
| ![desfaz [] (o botão. /media/undoc130389.png)](. /media/undoc130389.png)                           | Desfazer a última ação.                                                                                                                                                                  |
| ![refaz [] (o botão. /media/redoc130389.png)](. /media/redoc130389.png)                           | Reverter a última ação desfeita.                                                                                                                                                          |
| [botão localizar![(]. /media/findc130389.png)](. /media/findc130389.png)                           | Abra a caixa de diálogo **Localizar e Substituir**, na qual você pode pesquisar e substituir o texto na janela ativa.                                                                                  |
| [botão de inserção de linha] (![. /media/insertrowc130389.png)](. /media/insertrowc130389.png)           | Inserir uma linha em branco na definição de linha ou uma linha de cabeçalho em branco na definição de coluna. Este botão está disponível em uma definição de linha ou definição de coluna.                    |
| [coluna de botões de inserção![(]. /media/insertcolumnc130389.png)](. /media/insertcolumnc130389.png)  | Inserir uma coluna vazia na definição de coluna. Este botão está disponível em uma definição de coluna.                                                                                  |
| [botão de bloqueio do![(]. /media/lockc130389.png)](. /media/lockc130389.png)                           | Aplicar uma senha ao bloco de construção atual. Este botão está disponível para usuários com a função **Designer** ou **Administrador**.                                                 |
| [botão o link de linha do![(]. /media/rowlinkc130389.png)](. /media/rowlinkc130389.png)                 | Abra a caixa de diálogo **Links de Linhas**, na qual você pode especificar as origens de definições de links de dados e as definições de árvores de relatórios. Este botão está disponível em uma definição de linha. |
| [de botão promover![(]. /media/promotec130389.png)](. /media/promotec130389.png)                  | Promover uma unidade da definição de árvore de relatório. Quando você seleciona uma unidade filho e clica em **Promover**, a unidade filho é movida para o mesmo nível da unidade pai.                |
| [degrada o![(botão]. /media/demotec130389.png)](. /media/demotec130389.png)                     | Rebaixar uma unidade da definição de árvore de relatórios. Quando você seleciona uma unidade e clica em **Rebaixar**, a unidade se torna um filho da unidade que a precede.                               |
| expande![[] (o botão. /media/expandtreebuttonc130389.png)](. /media/expandtreebuttonc130389.png) | Expandir todas as unidades da definição de árvore de relatórios no nível da unidade selecionada.                                                                                                   |
| [botão de recolher![(]. /media/collapsec130389.png)](. /media/collapsec130389.png)               | Recolher a árvore de relatórios.                                                                                                                                                           |
| [botão ajuda do![(]. /media/helpc130389.png)](. /media/helpc130389.png)                           | Abrir Ajuda.                                                                                                                                                                             |

### <a name="formatting-toolbar"></a>Barra de ferramentas de formatação

A barra de ferramentas de formatação fornece acesso fácil a comandos de estilo. Esta barra de ferramentas inclui os botões a seguir.

| Botão                                                                                                                                                                                                   | Descrição                                             |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| [botão estilo de fonte do![(]. /media/formattingc130389.png)](. /media/formattingc130389.png)                         | Aplicar o estilo de fonte selecionado ao texto atual.      |
| [botão de origem] (![. /media/fonttype.png)](. /media/fonttype.png)                                                 | Definir o texto atual para a fonte selecionada.              |
| [botão do tamanho de fonte do![(]. /media/fontsize.png)](. /media/fontsize.png)                                            | Definir o texto atual para o tamanho da fonte selecionada (em pontos). |
| [botão negrito![(]. /media/boldc130389.png)](. /media/boldc130389.png)                                           | Colocar o texto atual em negrito.                             |
| [botão em itálico![(]. /media/italicsc130389.png)](. /media/italicsc130389.png)                                   | Colocar o texto atual em itálico.                           |
| [botão de sublinhado![(]. /media/underlinec130389.png)](. /media/underlinec130389.png)                            | Sublinhar o texto atual.                             |
| [botão o recuo de![do![(]. /media/outdentlsc130389.png)](. /media/outdentlsc130389.png)                      | Diminuir o recuo do texto atual.                |
| [botão o recuo de aumento do![(]. /media/indentlsc130389.png)](. /media/indentlsc130389.png)                        | Aumentar o recuo do texto atual.                |
| [botão de cor de plano de fundo![(]. /media/fillbackgroundcolorc130389.png)](. /media/fillbackgroundcolorc130389.png) | Alterar a cor de plano de fundo da célula atual.        |
| [botão de cor de fonte do![(]. /media/fontcolorc130389.png)](. /media/fontcolorc130389.png)                           | Alterar a cor do texto atual.                   |

### <a name="report-designer-toolbar"></a>Barra de ferramentas do designer de relatórios

A barra de ferramentas do designer de relatórios fornece acesso rápido aos comandos para navegar no designer de relatórios. Esta barra de ferramentas inclui os botões a seguir.

| Botão                                                                                                                                                                                          | Descrição                                                                                                                                                                  |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [botão da definição do![(]. /media/reportc130389.png)](. /media/reportc130389.png)                 | Mostrar a definição de relatório que está listada no menu **Janela**.                                                                                                            |
| [botão de definição de linha do![(]. /media/rowc130389.png)](. /media/rowc130389.png)                          | Mostrar a definição de linha que é atribuída à definição de relatório ativo.                                                                                                    |
| [botão de coluna do![(]. /media/columnc130389.png)](. /media/columnc130389.png)                 | Mostrar a definição de coluna que é atribuída à definição de relatório ativo.                                                                                                 |
| [botão de hierarquia organizacional do![(]. /media/treec130389.png)](. /media/treec130389.png)             | Mostrar a definição de árvore de relatórios que é atribuída à definição de relatório ativo.                                                                                         |
| [botão visualizador![relatório do![(]. /media/reportviewerc130389.png)](. /media/reportviewerc130389.png)         | Iniciar o Visualizador de Relatórios e mostrar a versão mais recente do relatório gerado. Este botão está disponível em uma definição de relatório se você gerou pelo menos um relatório. |
| [![gera o botão de relatórios (]. /media/generate-to-ddvc130389.png)](. /media/generate-to-ddvc130389.png) | Gerar um relatório a partir da definição de relatório ativo. Este botão está disponível em uma definição de relatório.                                                                      |



<a name="see-also"></a>Consulte também
--------

[Relatório financeiro do Microsoft Dynamics ERP](financial-reporting-intro.md)

[Generate a financial report](\financials\general-ledger\generate-financial-report.md)


