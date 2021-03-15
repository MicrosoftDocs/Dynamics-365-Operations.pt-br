---
title: Organizar componentes de relatório no designer de relatórios
description: Este tópico explica como organizar objetos no designer de relatórios, blocos de construção e relatórios existentes.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0b55dcee00f571228ec1e933306d77d9edc12866
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092414"
---
# <a name="organize-report-components-in-report-designer"></a>Organizar componentes do relatório no designer de relatórios

[!include [banner](../includes/banner.md)]

Depois que você tiver desenvolvido blocos de construção e relatórios gerados, é útil organizar esses objetos para que fiquem mais fácil para os usuários a localizar. Este artigo explica como organizar objetos no report designer, blocos de construção e relatórios existentes.

Você pode renomear pastas, relatórios, blocos de construção e outros objetos no designer de relatórios para ajudar a organizar seus arquivos. Dependendo do tipo de objeto que você renomear, talvez seja necessário atualizar associações a esse objeto.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Renomear uma pasta ou um bloco de construção no Designer de Relatórios
No Report Designer, você pode renomear pastas, definições de relatórios, de linhas, de colunas e de hierarquia organizacional.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Renomear uma pasta ou bloco de construção no Report Designer

1. No Report Designer, use o painel de navegação para localizar a pasta ou o objeto a ser renomeado.
2. Clique com o botão direito do mouse na pasta ou objeto, e clique em **Renomear**. O campo **Nome** no painel de navegação torna-se disponível.
3. Digite um novo nome e pressione Inserir.
4. Se o bloco de construção for uma definição de linha, uma definição de coluna ou uma definição de árvore de relatórios, atualize outros blocos de construção associados a ele. Clique com o botão direito do mouse no bloco de construção que você renomeou na etapa 3, selecione **Associações** e selecione um item na lista para a atualizá-lo.
5. Repita a etapa 4 até que todos os itens associados sejam atualizados.

## <a name="create-and-manage-report-groups"></a>Criar e gerenciar grupos de relatórios
você pode agrupar definições de relatório para gerar vários relatórios ao mesmo tempo. Para criar, modificar, excluir e gerar grupos de relatório, você deve ter a função de designer ou administrador. Os usuários com a função de gerador podem gerar grupos de relatórios, e também podem modificar as definições de relatório do usuário para grupos de relatórios.

### <a name="create-a-report-group"></a>Criar um grupo de relatórios

1. No Designer de Relatórios, clique em **Grupos de Relatórios** no painel de navegação.
2. No menu **Arquivo**, clique em **Novo** &gt; **Definição de grupo de relatório** para abrir um novo grupo de relatório na janela de visualização. Como alternativa, clique no botão **Grupo de Relatórios** ![Grupo de Relatórios](media/report-group.gif "Grupo de Relatórios") na barra de ferramentas.
3. Clique na guia **Grupo de relatório**. Para substituir as informações nas definições de relatório individuais para a geração deste relatório, marque a caixa de seleção **Substituir a empresa, os detalhes e as configurações de data das definições de relatório individuais**. As informações de nome da empresa, nível de detalhe, configurações provisórias e data são preenchidas automaticamente, mas você ainda pode fazer atualizações.
4. Marque a caixa de seleção **Incluir todas as moedas de relatório** se desejar que os vários relatórios gerados exibam essas moedas. Você pode acessar diversas exibições clicando no botão **Moeda** no Visualizador Web quando você exibir o relatório.
5. No campo **Relatórios no grupo**, clique em **Adicionar** para selecionar os relatórios a serem incluídos no grupo Relatório. Para selecionar vários relatórios na caixa de diálogo **Adicionar**, mantenha pressionada a tecla CTRL enquanto seleciona relatórios. Quando terminar de selecionar os relatórios, clique em **OK**.
6. Clique em **Arquivo** &gt; **Salvar** para salvar o novo grupo de relatório.

### <a name="modify-a-report-group"></a>Modificar um grupo de relatório

1. No Designer de Relatórios, clique em **Grupos de Relatórios** no painel de navegação.
2. Clique duas vezes no grupo de relatórios a ser modificado.
3. Clique na guia **Grupo de Relatório** e faça as alterações desejadas.
4. No menu **Arquivo**, clique em **Salvar** para salvar o grupo de relatórios modificado. Como alternativa, clique no botão **Salvar** ![Salvar](media/save.gif "Salvar") na barra de ferramentas.

> [NOTA] Se você agendou relatórios para que sejam gerados em intervalos definidos, pode substituir essas configurações e gerar um relatório imediatamente.

### <a name="generate-a-report-group-report"></a>Gerar um relatório do grupo de relatório

1. No Designer de Relatórios, clique em **Grupos de Relatórios** no painel de navegação.
2. Abra o grupo de relatórios a ser gerado.
3. Clique no botão **Gerar Relatório** ![Gerar Relatório](media/generate-report.gif "Gerar Relatório") para gerar relatórios.

### <a name="delete-a-report-group"></a>Excluir um grupo de relatório

1. No Designer de Relatórios, clique em **Grupos de Relatórios** no painel de navegação.
2. Clique com o botão direito do mouse no grupo de relatórios e selecione **Excluir** para excluir.
3. Quando uma mensagem de confirmação aparecer, clique em **Sim**.

## <a name="report-group-tab-controls"></a>Controles de guia do grupo de relatórios
A tabela a seguir descreve os controles na guia **Grupo de relatórios**.

<table>
<thead>
<tr>
<th>Controle</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr>
<td>Substituir a empresa, os detalhes e as configurações de data das definições de relatório individuais</td>
<td>Marque esta caixa de seleção para substituir definições de relatório individuais dos relatórios nesse grupo de relatórios para a geração apenas desses relatórios.</td>
</tr>
<tr>
<td>Nome da empresa</td>
<td>Selecione a empresa a ser usada para os relatórios.</td>
</tr>
<tr>
<td>Nível de detalhe</td>
<td>Especifique o nível de detalhamento que os relatórios incluem.
<ul>
<li><strong>Financeiro</strong> - um relatório de resumo de alto nível. Você não pode fazer uma busca detalhada em contas e dimensões, exceto naquelas contas e dimensões que foram adicionadas pela árvore do relatório.</li>
<li><strong>Financeiro &amp; Conta</strong> − Um relatório que contém detalhes de resumo e conta de alto nível.</li>
<li><strong>Financeiro, Conta &amp; Transação</strong> − Um relatório que contém detalhes de resumo e transação de alto nível.</li>
</ul></td>
</tr>
<tr>
<td>Provisional</td>
<td>Especifique os tipos de atividade que os relatórios incluem.
<ul>
<li><strong>Somente atividades lançadas</strong> - inclui somente as transações e os saldos lançados em seus dados financeiros.</li>
<li><strong>Atividades lançadas e não lançadas</strong> - inclui todas as transações e os saldos inseridos e lançados em seus dados financeiros.</li>
<li><strong>Somente atividades não lançadas</strong> - inclui somente as transações inseridas, mas ainda não lançadas, em seus dados financeiros.</li>
</ul></td>
</tr>
<tr>
<td>Incluir todas as moedas de relatório</td>
<td>Todas as moedas de relatório adicionais estiverem configuradas no sistema ERP do Microsoft Dynamics serão listadas aqui. Selecione esta caixa de seleção para que os relatórios adicionais sejam gerados nas moedas indicadas. Para exibir esses relatórios no Visualizador da Web, clique no botão <strong>Moeda</strong> e selecione uma moeda.</td>
</tr>
<tr>
<td>Informações de data não salvas com a definição de relatório</td>
<td><ul>
<li>Período base</li>
<li>Ano base</li>
<li>Período coberto</li>
</ul>
Somente as configurações do Período Base Padrão são salvas com a definição de relatório.</td>
</tr>
<tr>
<td>Informações de data salvas com a definição de relatório</td>
<td><ul>
<li>Data do relatório</li>
<li>Período base padrão</li>
</ul></td>
</tr>
<tr>
<td>Relatórios em grupo</td>
<td>Adicionar, remover e reordenar relatórios no grupo de relatório.
<ul>
<li>Para adicionar definições ao grupo de relatórios, clique duas vezes no grupo de relatórios para abri-lo e clique em <strong>Adicionar</strong>. Selecione os relatórios que serão incluídos no grupo de relatórios e clique em <strong>OK</strong>.</li>
<li>Para remover um relatório do grupo de relatórios, selecione-o e então clique em <strong>Remover</strong>.</li>
<li>Para mudar a ordem em que os relatórios são gerados, selecione um relatório na lista e clique em <strong>Mover para cima</strong> ou <strong>Mover para baixo</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Recursos adicionais

[Relatórios financeiros](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]