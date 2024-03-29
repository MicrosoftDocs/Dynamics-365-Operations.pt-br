---
title: Componentes de relatórios financeiros
description: Este artigo descreve como os componentes ou blocos de construção de definições de relatório são usados em relatórios financeiros.
author: aprilolson
ms.date: 10/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.form: FinancialReports
ms.openlocfilehash: 180b3c64b9eb506f162071a67b1fa9b728a569ce
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831601"
---
# <a name="financial-report-components"></a>Componentes de relatórios financeiros

[!include [banner](../includes/banner.md)]

Este artigo descreve como os componentes ou blocos de construção de definições de relatório são usados em relatórios financeiros. Esses blocos de construção incluem definições de linha, coluna e definições de árvore de relatórios. O artigo explica como organizar e bloquear blocos de construção.

A filosofia de design por trás do designer de relatórios financeiros é dividir informações no componente ou o bloco de construção, menor e, em seguida, mesclar e combinar os componentes conforme necessário. Portanto, a formatação do relatório é separada de dados financeiros, e você pode alterar o design de um relatório sem modificar os dados financeiros no Microsoft Dynamics 365 Finance. Usando esta abordagem de bloco de construção, você pode combinar texto, valores e cálculos, para gerar os relatórios necessários. Além disso, esta flexibilidade incentiva a criatividade, facilitando a exibição de suas operações de diferentes formas. Os blocos de construção individuais de uma definição de relatório são semelhantes a uma planilha tridimensional, mas com mais potência. Uma definição de relatório especifica a definição de linha, a definição de coluna e a definição de árvore do relatório opcional a serem usadas para o relatório. Ela também inclui informações sobre onde armazenar o relatório gerado e como formatá-lo.

## <a name="building-blocks-of-a-report"></a>Blocos de construção de um relatório

| Bloquear de construção            | descrição | Para obter mais informações |
|---------------------------|-------------|----------------------|
| Definição de linha            | Uma definição de linha define as linhas descritivas em um relatório (por exemplo, salários ou vendas). Ela também lista os valores ou as dimensões de segmentos que contêm valores para cada item de linha, e inclui a formatação e os cálculos da linha. | [Definições de linha](row-definitions-financial-reporting.md) |
| Definição de coluna         | Uma definição de coluna define o período a ser usado ao extrair dados das dimensões financeiras. Ela também inclui a formatação e os cálculos da coluna. | [Definições de coluna](column-definitions-financial-reports.md) |
| Definição de hierarquia organizacional | Uma definição de hierarquia organizacional lembra um gráfico organizacional. Ela contém unidades de relatório individuais que representam cada caixa no gráfico. As unidades podem ser departamentos específicos dos dados financeiros ou unidades de nível superior que resumem dados de outras unidades organizacionais. | [Definições de árvore de relatórios](financial-reporting-tree-definitions.md) |
| Definição de relatório         | Uma definição de relatórios usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório. Ela também fornece opções e configurações adicionais para personalizar um relatório. | [Definição de relatório](design-financial-report-definitions.md) |

Se você está começando a criar relatórios, convém usar o assistente de relatórios para criar rapidamente uma definição de relatório que possa ser personalizada depois. Se você tem experiência na criação de relatórios e deseja maior flexibilidade no projeto de relatório, pode combinar os blocos de construção novos ou existentes para criar uma nova definição de relatório. Você não precisa compreender totalmente todas as opções de definição de relatório disponíveis para gerar relatórios de qualidade. Ao familiarizar-se com a criação de relatórios, você pode expandir as definições de relatório para aproveitar mais recursos avançados. Depois de criar um relatório básico, você pode personalizar a definição de relatório e qualquer bloco de construção na definição de relatório.

## <a name="organize-the-building-blocks"></a>Organizar os blocos de construção
Use pastas para organizar seus blocos de construção no Designer de Relatórios. Todas as pastas são específicas do tipo de bloco de construção que elas contêm. Por exemplo, todas as pastas contendo definições de linha estão localizadas no painel **Definições de Linha** do Report Designer.

### <a name="create-a-folder"></a>Criar uma pasta

1. No Report Designer, selecione o tipo de bloco de construção para organizar no painel de navegação. Por exemplo, para classificar uma definição de linha, clique em **Definições de Linha**.
2. No painel de navegação, selecione a pasta existente para criar a nova pasta em, depois siga uma destas etapas:

    - Clique com o botão direito do mouse na pasta pai e, depois, clique em **Nova pasta**.
    - Selecione a pasta pai e clique em **Arquivo**. Depois, clique em **Nova pasta**.

3. Quando a nova pasta aparecer, insira o nome dela e pressione **Enter**.

## <a name="lock-a-building-block"></a>Bloquear um bloco de construção
Você pode criar uma senha para proteger e bloquear um bloco de construção. Desta forma você pode adicionar um nível de segurança a um componente de relatório sem proteger o sistema inteiro. Uma senha pode ajudar a proteger as informações do bloco de construção que são importantes para o processo de criação de relatório de fim de mês. Um usuário em qualquer função pode bloquear um bloco de construção. No entanto, outros usuários sempre têm acesso somente leitura a um componente bloqueado. Os usuários podem abrir, alterar e salvar o componente bloqueado com um novo nome. Um usuário com a função de administrador sempre pode acessar e alterar um bloco de construção bloqueado.

1. No Report Designer, abra o componente do relatório a ser bloqueado, como uma definição de linha, uma definição de coluna, uma definição de relatório ou uma definição de árvore de relatórios.
2. No menu **Ferramentas**, clique em **Proteger/Desproteger**. Você também pode clicar no ícone **Proteger/Desproteger** (um bloqueio) na barra de ferramentas.
3. Na caixa de diálogo **Proteger**, insira e confirme uma senha, e clique em **OK**. O ícone de bloqueio na barra de ferramentas é realçado quando um bloco de construção aberto é bloqueado.

Para desbloquear um bloco de construção bloqueado, abra-o e clique no ícone **Proteger/Desproteger** na barra de ferramentas. De forma alternativa, no menu **Ferramentas**, clique em **Desproteger**.

## <a name="building-block-groups"></a>Grupos do Bloco de Construção

Os blocos de construção são as definições linha, definições de coluna, definições de árvore de relatórios e definições de relatório que você pode criar para um relatório. Os grupos de blocos de construção são coleções dos conjuntos de valores de dimensão e definições.

### <a name="view-a-building-block-group"></a>Exibir um grupo de bloco de construção

Você pode exibir todos os blocos de construção atribuídos a um grupo de blocos de construção. Você também pode exportar ou importar um grupo de blocos de construção.

1. No Report Designer, no menu **Empresa**, clique em **Grupos de blocos de construção**.
2. Na caixa de diálogo **Grupos do bloco de construção**, selecione o bloco de construção a ser exibido.
3. Clique em **Exibir** para abrir a caixa de diálogo **Exibir grupo do bloco de construção** e para exibir o conteúdo do grupo do bloco de construção.
4. Clique em **Fechar** para fechar as caixas de diálogo.

### <a name="export-a-building-block-group"></a>Exportar um grupo de bloco de construção

É possível exportar um grupo de blocos de construção ou bloco de construção do relatório específico em um grupo de blocos de construção. Você pode usar o grupo de blocos de criação exportado como backup. Você também pode copiar os dados exportados entre as instalações. O Report Designer tem os estilos de fonte referenciados e os conjuntos de valores de dimensão junto com o grupo de blocos de construção.

1. No Report Designer, no menu **Empresa**, clique em **Grupos de blocos de construção**.
2. Na caixa de diálogo **Grupos de blocos de construção**, selecione o grupo de bloco de construção a ser exportado e clique em **Exportar**.
3. Na caixa de diálogo **Exportar**, selecione as definições de relatório para exportação:

    - Para exportar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar tudo**.
    - Para exportar relatórios, linhas, colunas, árvores ou conjuntos de valores de dimensão específicos, clique na guia apropriada e selecione os itens a serem exportados. Pressione e mantenha pressionada a tecla Ctrl para selecionar vários itens em uma guia.

    > [!NOTE]
    > Quando você seleciona relatórios para exportar, as linhas, as colunas, as hierarquias e os conjuntos de valores de dimensão associados são selecionados.

4. Quando você acabar de selecionar itens para exportação, clique em **Exportar**.
5. Na caixa de diálogo **Salvar Como**, selecione um local para exportar o grupo do bloco de construção.
6. No campo **Nome do arquivo**, insira um nome para o arquivo. O designer de relatórios adiciona automaticamente um nome de arquivo com a extensão .tdbx.
7. Clique em **Salvar**. O grupo do bloco de construção é salvo no local que você especificou.

### <a name="import-a-building-block-group"></a>Importar um grupo do bloco de construção

Você pode importar um grupo de blocos de construção para um grupo existente de blocos de construção. Todos os grupos de bloco de construção importados mantêm seus estilos de fonte original e referências de empresa e incluem os conjuntos de valores de dimensão relevante.

1. No Report Designer, no menu **Empresa**, clique em **Grupos de blocos de construção**.
2. Na caixa de diálogo **Grupos de blocos de construção**, selecione o bloco de construção para o qual importar um grupo de blocos de construção e clique em **Importar**.
3. Na caixa de diálogo **Abrir**, selecione o grupo de blocos de construção a ser importado e clique em **Abrir**.
4. Na caixa de diálogo **Importar**, selecione as definições de relatório para importação:

    - Para importar todas as definições de relatório e os blocos de construção de suporte, clique em **Selecionar tudo**.
    - Para importar relatórios, linhas, colunas, árvores ou conjuntos de valores de dimensão específicos, selecione os relatórios, as linhas, as colunas, as árvores ou os conjuntos de valores de dimensão a serem importados.

5. Quando você acabar de selecionar itens para importação, clique em **Importar**.

### <a name="undo-a-checkout-of-a-building-block"></a>Desfazer o check-out de um bloco de construção

Quando você abre um bloco de construção, outros usuários só podem acessar o bloco de construção no modo somente leitura. Às vezes, um usuário se esquece de fechar um bloco de construção ou desliga o sistema sem fechar o bloco de construção. Como resultado, é feito o check-out do bloco de construção e outros usuários não podem abri-lo. Nessas situações, um administrador do relatório financeiro pode usar a caixa de diálogo **Itens com Check-out** para efetuar check-in em blocos de construção que um usuário tenha deixado com status check-out.

> [!NOTE]
> Você deve ter a função de administrador para fazer check-in dos blocos de construção usando a caixa de diálogo **Itens de Check-out**.

1. No Report Designer, no menu **Ferramentas**, clique em **Itens com check-out**.
2. Na caixa de diálogo **Itens com check-out**, selecione **Mostrar itens de todos os usuários**. A lista é atualizada para exibir todos os blocos de construção com check-out e os usuários que fizeram o check-out.
3. Selecione um bloco de construção e clique em **Desfazer check-out**.
4. Clique em **Sim** para fazer check-in do bloco de construção.

## <a name="additional-resources"></a>Recursos adicionais

[Relatórios financeiros](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
