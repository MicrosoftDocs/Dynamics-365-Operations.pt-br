---
title: "Exibir relatórios financeiros"
description: "Este artigo descreve como exibir e explorar relatórios financeiros no Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. Ele inclui informações sobre as várias opções que você pode aplicar a relatórios financeiros para alterar sua aparência e os dados que eles incluem."
author: kweekley
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 61763e57a54a24665d7ca899d8a26cf9e4d3984b
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="view-financial-reports"></a>Exibir relatórios financeiros

[!include[banner](../includes/banner.md)]


Este artigo descreve como exibir e explorar relatórios financeiros no Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. Ele inclui informações sobre as várias opções que você pode aplicar a relatórios financeiros para alterar sua aparência e os dados que eles incluem.

<a name="financial-reporting-overview"></a>Visão geral de relatórios financeiros
----------------------------

## <a name="open-a-financial-report"></a>Abrir um relatório financeiro
Para abrir um relatório, selecione o nome do relatório. Na primeira vez que um relatório for aberto, será gerado automaticamente para o mês anterior. Por exemplo, se você abrir um relatório pela primeira vez em agosto de 2015, o relatório é gerado para 31 de julho de 2015. Depois que um relatório for aberto, você pode começar a explorá-la ao aprofundamento de partes específicas de dados e alterar opções de relatório.

## <a name="drill-down-on-a-financial-report"></a>Busca detalhada em um relatório financeiro
Os relatórios financeiros podem incluir vários níveis de detalhe. O nível financeiro é o primeiro nível exibido quando você abre um relatório financeiro. Para ir até o nível de conta, selecione os dados sobre os quais realizar a busca detalhada. Por exemplo, para visualizar os detalhes da conta para vendas, selecione os dados de vendas que você deseja explorar. No nível de conta, você pode fazer a busca detalhada para visualizar as transações que compõem o saldo da conta. Existem duas maneiras de visualizar as transações: transações de relatório e transações de comprovante.

-   **Transações de relatório** – As transações aparecem em uma exibição formatada que está inclusa no relatório financeiro. Para visualizar transações na exibição formatada, selecione os dados sobre os quais fazer a busca detalhada, e então clique em **Buscar no nível de transação de relatório**.
-   **Transações de comprovante** – Uma consulta de transação de comprovante é aberta, onde é possível visualizar transações. Para visualizar transações na consulta de transação de comprovante, selecione os dados sobre os quais fazer a busca detalhada, e então clique em **Abrir transações de conta**.

Se os dados são dados do orçamento, você pode escolher abrir entradas da conta de orçamento. Para fechar qualquer nível do relatório e retornar ao início, você pode pressionar a tecla Esc ou clicar no botão **Fechar** (**X**) no canto superior direito.

## <a name="change-report-options"></a>Alterar opções de relatório
Você pode alterar a data do relatório, aplicar filtros de atributo e dimensão, ou alterar o cenário de orçamento em um relatório **Real versus orçamento**. No Painel de Ação, clique em **Opções de relatório**, e então siga uma ou mais das etapas abaixo:

-   Para alterar o período base e o ano base de um relatório, selecione um período base e um ano base, e clique em **OK**.
-   Para aplicar filtros de atributo em um relatório, selecione **Adicionar um filtro de atributo**. Selecione o atributo, digite o valor do atributo, e clique em **OK**. Por exemplo, se você selecionar o atributo **Categoria da Conta**, insira **VENDAS** como valor de atributo. Para remover um filtro de atributo, clique em **Limpar**.
-   Para aplicar filtros de dimensão em um relatório, selecione **Adicionar um filtro de dimensão**. Selecione a dimensão e, em seguida, digite o ID de dimensão ou selecione a dimensão na lista. Para remover um filtro de dimensão, clique em **Limpar**.
-   Para alterar o cenário em um relatório **Real versus orçamento**, selecione um novo cenário, e clique em **OK**. Se o cenário selecionado for para um ano diferente, lembre de atualizar o ano base. Por exemplo, se o cenário atual é para FY2015, e você selecionou um novo cenário que é para FY2016, você deve alterar o ano base para **2016**.

Quando você clica em **OK**, todas as opções selecionadas serão aplicadas ao relatório. Se você decidir que não deseja aplicar as opções selecionadas, clique em **Cancelar**.

## <a name="update-a-financial-report"></a>Atualizar um relatório financeiro
Você pode atualizar um relatório financeiro para que ele mostre os dados mais recentes do período e ano para o qual foi gerado. Por exemplo, se você atualizar um relatório financeiro que foi gerado para outubro de 2015, o relatório irá refletir todas as novas transações que foram lançadas para outubro de 2015. Para atualizar um relatório financeiro, no Painel de Ação, clique em **Atualizar**. Um relatório atualizado está disponível apenas para a pessoa que o atualizou. Para que outras pessoas possam visualizar os mesmos dados, o relatório deve ser publicado.

## <a name="publish-a-financial-report"></a>Publicar um relatório financeiro
Após atualizar um relatório financeiro, é possível publicá-lo. Outras pessoas na organização poderão então visualizá-lo. Para publicar um relatório, no Painel de Ação, clique em **Publicar**.

## <a name="display-a-financial-report-in-a-different-currency"></a>Exibir um relatório financeiro em uma moeda diferente
Um relatório financeiro pode ser exibido em qualquer moeda a qualquer momento. Para exibir um relatório em uma moeda diferente, no Painel de Ação, clique em **Moeda**, e então selecione uma moeda. O relatório é convertido naquela moeda, e os resultados são exibidos. Todos os códigos ou símbolos de moeda que estão inclusos no relatório como parte de seu design são atualizados para refletir a nova moeda. As moedas que aparecem na lista são as moedas de relatório que estão configuradas no Finance and Operations.

## <a name="display-a-summarized-view-of-the-financial-report"></a>Exibir uma visualização resumida do relatório financeiro
Um relatório financeiro pode conter linhas de detalhe e de resumo. Linhas de detalhe são linhas que contêm contas principais ou dimensões. Linhas de resumo são linhas de descrição, de total e de cálculo. Para exibir apenas as linhas de resumo de um relatório, clique em **Mostrar**, e então clique em **Apenas linhas de resumo**. O relatório é recolhido e passa a exibir somente as linhas de resumo. Para exibir as linhas de detalhe juntamente com as linhas de resumo, clique em **Mostrar**, e então clique novamente em **Apenas linhas de resumo**.

## <a name="open-a-financial-report-from-a-previous-month"></a>Abrir um relatório financeiro de um mês anterior
Você pode visualizar relatórios do mês atual ou de meses anteriores sem gerar novamente o relatório. Para abrir o relatório para um mês anterior, clique em **Mostrar** e, em seguida, clique em **Relatórios anteriores**. Aparece uma lista dos meses anteriores em que o relatório foi gerado. Expanda o mês para o qual visualizar o relatório, selecione a data, e então clique em **OK**. A relatório do mês anterior é exibido. Para retornar ao relatório do mês atual, clique em **Cancelar**.

## <a name="print-a-financial-report"></a>Imprimir um relatório financeiro
Para imprimir um relatório financeiro, no Painel de Ação, clique em **Imprimir**, e então siga uma ou mais dessas etapas para definir as opções de impressão:

-   Para incluir os diversos níveis de detalhe no relatório impresso, defina o controle deslizante como **Sim** ou **Não**. Se um relatório utiliza uma árvore de relatório, você pode optar por incluir todas as unidades de relatório ou apenas a unidade de relatório atual.
-   Para definir o tamanho da página, selecione um tamanho de página na lista.
-   Para definir o layout da página, selecione um layout na lista. Se desejar que o conteúdo do relatório se ajuste à largura que você selecionou, defina o controle deslizante como **Sim**.
-   Para definir as margens da página, digite o tamanho das margens superior, inferior, esquerda e direita em polegadas.

Após concluir a definição das opções de impressão, clique em **Imprimir** para imprimir o relatório. Se decidir que não deseja imprimir o relatório, clique em **Cancelar**. Uma pré-visualização do relatório impresso é exibida. Você pode selecionar a impressora para a qual enviar o relatório, e também pode ajustar as opções de impressão.

## <a name="export-a-financial-report"></a>Exportar um relatório financeiro
Para exportar um relatório financeiro, no Painel de Ação, clique em **Exportar**. O relatório é exportado para o Microsoft Excel, e o navegador solicitará que abra ou salve o arquivo exportado. As configurações de exportação que estão definidas no design do relatório são aplicadas ao relatório exportado.    

<a name="see-also"></a>Consulte também
--------

[Relatório financeiro do Microsoft Dynamics AX](../../dev-itpro/analytics/financial-reporting-intro.md)





