---
title: Exibir relatórios financeiros
description: Este tópico descreve como visualizar e explorar relatórios financeiros no Microsoft Dynamics 365 Finance. Ele inclui informações sobre as várias opções que você pode aplicar a relatórios financeiros para alterar sua aparência e os dados que eles incluem.
author: kweekley
ms.date: 03/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f729b1703a7703a8a604b007bd1c8d9e1f604a6
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897275"
---
# <a name="view-financial-reports"></a>Exibir relatórios financeiros

[!include [banner](../includes/banner.md)]

Este tópico descreve como visualizar e explorar relatórios financeiros. Ele inclui informações sobre as várias opções que você pode aplicar a relatórios financeiros para alterar sua aparência e os dados que eles incluem.

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
Você pode aplicar filtros de atributo e dimensão ou alterar o cenário de orçamento em um relatório **Real versus orçamento**. No Painel de Ação, clique em **Opções de relatório**, e então siga uma ou mais das etapas abaixo:

-   Para aplicar filtros de atributo em um relatório, selecione **Adicionar um filtro de atributo**. Selecione o atributo, digite o valor do atributo, e clique em **OK**. Por exemplo, se você selecionar o atributo **Categoria da Conta**, insira **VENDAS** como valor de atributo. Para remover um filtro de atributo, clique em **Limpar**.
-   Para aplicar filtros de dimensão em um relatório, selecione **Adicionar um filtro de dimensão**. Selecione a dimensão e, em seguida, digite o ID de dimensão ou selecione a dimensão na lista. Para remover um filtro de dimensão, clique em **Limpar**.
-   Para alterar o cenário em um relatório **Real versus orçamento**, selecione um novo cenário, e clique em **OK**. Se o cenário selecionado for de um ano fiscal diferente, nenhum resultado será retornado. Por exemplo, se for gerado um relatório para FY2015, o cenário atual for de FY2015 e o novo cenário selecionado for relativo a FY2016, nenhum resultado será retornado. Se for necessário um novo cenário para outro ano fiscal, gere uma nova versão do relatório para o ano fiscal relacionado ao cenário.

Quando você clica em **OK**, todas as opções selecionadas serão aplicadas ao relatório. Se você decidir que não deseja aplicar as opções selecionadas, clique em **Cancelar**.

## <a name="update-a-financial-report"></a>Atualizar um relatório financeiro
Você pode atualizar um relatório financeiro para que ele mostre os dados mais recentes do período e ano para o qual foi gerado. Por exemplo, se você atualizar um relatório financeiro que foi gerado para outubro de 2015, o relatório irá refletir todas as novas transações que foram lançadas para outubro de 2015. Para atualizar um relatório financeiro, no Painel de Ação, clique em **Atualizar**. Um relatório atualizado está disponível apenas para a pessoa que o atualizou. Para que outras pessoas possam visualizar os mesmos dados, o relatório deve ser publicado.

## <a name="publish-a-financial-report"></a>Publicar um relatório financeiro
Após atualizar um relatório financeiro, é possível publicá-lo. Outras pessoas na organização poderão então visualizá-lo. Para publicar um relatório, no Painel de Ação, clique em **Publicar**.

## <a name="display-a-financial-report-in-a-different-currency"></a>Exibir um relatório financeiro em uma moeda diferente
Um relatório financeiro pode ser exibido em qualquer moeda a qualquer momento. Para exibir um relatório em uma moeda diferente, no Painel de Ação, clique em **Moeda**, e então selecione uma moeda. O relatório é convertido naquela moeda, e os resultados são exibidos. Todos os códigos ou símbolos de moeda que estão inclusos no relatório como parte de seu design são atualizados para refletir a nova moeda. As moedas que aparecem na lista são as moedas de relatório que estão configuradas no Finance.

## <a name="display-a-summarized-view-of-the-financial-report"></a>Exibir uma visualização resumida do relatório financeiro
Um relatório financeiro pode conter linhas de detalhe e de resumo. Linhas de detalhe são linhas que contêm contas principais ou dimensões. Linhas de resumo são linhas de descrição, de total e de cálculo. Para exibir apenas as linhas de resumo de um relatório, clique em **Mostrar**, e então clique em **Apenas linhas de resumo**. O relatório é recolhido e passa a exibir somente as linhas de resumo. Para exibir as linhas de detalhe juntamente com as linhas de resumo, clique em **Mostrar**, e então clique novamente em **Apenas linhas de resumo**.

## <a name="print-a-financial-report"></a>Imprimir um relatório financeiro
Imprimir um relatório financeiro criará um arquivo PDF que pode ser impresso manualmente. Para criar um relatório financeiro imprimível, no Painel de Ação, clique em **Imprimir**, e então siga uma ou mais dessas etapas para definir as opções de impressão:

-   Para incluir os diversos níveis de detalhe no relatório impresso, defina o controle deslizante como **Sim** ou **Não**. Se um relatório utiliza uma árvore de relatório, você pode optar por incluir todas as unidades de relatório ou apenas a unidade de relatório atual.
-   Para definir o tamanho da página, selecione um tamanho de página na lista.
-   Para definir o layout da página, selecione um layout na lista. Se desejar que o conteúdo do relatório se ajuste à largura que você selecionou, defina o controle deslizante como **Sim**.
-   Para definir as margens da página, digite o tamanho das margens superior, inferior, esquerda e direita em polegadas.

Depois de concluir as configurações das opções de impressão, clique em **Imprimir** para continuar e ser avisado se deseja baixar o arquivo ou salvá-lo no OneDrive ou SharePoint. Se decidir que não deseja continuar, clique em **Cancelar**. Depois de continuar, o relatório começará a ser renderizado no servidor e você será avisado para baixar o relatório no formato de PDF. Agora você pode exibir o relatório na exibição de PDF e, a partir daí, você pode selecionar a impressora para onde enviar o relatório, e realizar quaisquer ajustes adicionais para as opções de impressão.

## <a name="export-a-financial-report"></a>Exportar um relatório financeiro
Para exportar um relatório financeiro, no Painel de Ação, clique em **Exportar**. O relatório é exportado para o Microsoft Excel, e o navegador solicitará que você abra ou salve o arquivo exportado. As configurações de exportação que estão definidas no design do relatório são aplicadas ao relatório exportado.    

<a name="additional-resources"></a>Recursos adicionais
--------

[Relatórios financeiros](../../fin-ops-core/dev-itpro/analytics/financial-reporting-intro.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]