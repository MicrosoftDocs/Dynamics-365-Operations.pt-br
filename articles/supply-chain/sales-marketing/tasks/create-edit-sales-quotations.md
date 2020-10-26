---
title: Criar e editar cotações de venda
description: Este procedimento demonstrativos como criar e atualizar uma cotação de venda.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable, CustQuotationConfirmationJournal, CustQuotationJournal, CustSalesLines, SalesQuotationCopying, SalesQuotationDeleteQuotations, SalesQuotationListPagePreviewPane, SalesQuotationTypeGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 73c15b41a4b0979ec79c8dbd8d88627bffcf6ed3
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981223"
---
# <a name="create-and-edit-sales-quotations"></a>Criar e editar cotações de venda

[!include [banner](../../includes/banner.md)]

Este procedimento demonstrativos como criar e atualizar uma cotação de venda. Você pode realizar esse procedimento em seus próprios dados ou na empresa USMF de dados de demonstração.


## <a name="create-a-sales-quotation"></a>Criar uma cotação de venda
1. Vá para **Painel de navegação > Módulos > Vendas e marketing > Cotações de venda > Todas as cotações**.
2. Clique em **Novo**.
3. No campo **Tipo de conta**, selecione 'Cliente potencial'.
4. No campo **Cliente potencial**, insira ou selecione um valor.
5. Expanda a seção **Geral**. Como você optou por criar uma cotação na área Vendas e Marketing, o tipo é definido automaticamente como 'Cotação de venda'. Para criar uma cotação para um projeto, você deve acessá-lo no módulo **Gerenciamento e contabilidade do projeto**.
6. Clique em **OK**. Os campos e as ações nas linhas da cotação são muito semelhantes aos das linhas de ordem de venda.   Como as ordens de venda, as cotações podem ser criadas para um item específico, ou quando o número do item não é conhecido ou não existe no momento da criação da cotação, as cotações podem ser criadas para uma categoria de vendas.     
7. No campo **Item**, insira ou selecione um valor.
8. No campo **Local**, digite um valor.
9. No campo **Quantidade.**, insira um número Se houver contratos comerciais válidos para o item selecionado na linha, o preço e os descontos aplicáveis serão copiados automaticamente para a linha de cotação. Certifique-se de que o campo Preço unitário contém um valor e você também pode inserir valores de desconto, se quiser. 
10. Clique em **Salvar**.
11. No **Painel de Ação**, clique em **Cotação de venda**.
12. Clique em **Totais**.
13. Clique em **OK**.
14. Selecione a linha da cotação de venda.
15. No **Painel de Ação**, clique em **Cotação**.
16. Clique em **Simulação de preço**.
    - Na página **Executar simulação de preços**, você pode tentar ajustar a receita esperada ou a lucratividade de sua cotação com base no preço unitário, no valor do desconto, na porcentagem de desconto, no valor total, na margem ou no índice de contribuição desejados. Quando estiver satisfeito com os números de destino, aplique a sugestão à linha de cotação e os campos relacionados ao preço serão atualizados adequadamente.  
    - Você pode criar quantas simulações de preço quiser. Quando você clica em **Novo**, as condições de preço da linha da cotação atual são copiadas para a página. Você poderá modificar os valores de quaisquer campos relacionados a preço para os de destino. Uma alteração em um dos campos disparará o recálculo em todos os campos restantes. Para que o sistema calcule o índice de margem de contribuição e de venda, o custo unitário do produto deve ser conhecido. Use a guia Preços simulados para obter uma exibição detalhada dos preços originais, das alterações propostas e seus efeitos nos totais da cotação. Como regra geral, quando uma simulação que define um novo valor é aplicada à linha de cotação, o sistema recalcula e insere um novo valor no campo Preço unitário. Se a simulação for baseada em uma nova margem ou em um novo índice de contribuição, somente o campo Valor líquido será atualizado, e o Preço unitário ficará em branco. Nos dois casos, quaisquer descontos que ocorreram na linha da cotação antes da simulação serão excluídos.
17. No **Painel de Ação**, clique em **Cotação**.
18. Clique em **Enviar cotação**.
19. Selecione 'Sim' no campo **Imprimir cotação**.
20. Clique em **OK**. O relatório pode levar um minuto para ser gerado. Não feche a página até que isso ocorra.

## <a name="update-a-sales-quotation"></a>Atualizar uma cotação de venda
1. Vá para **Painel de navegação > Módulos > Vendas e marketing > Cotações de venda > Todas as cotações**.
2. No **Painel de Ação**, clique em **Acompanhamento**.
3. Clique em **Converter em cliente**.
4. No campo **Conta de cliente**, digite um valor.
5. Clique em **Verificar**. Verifique se aparece uma mensagem indicando que o número de conta que você digitou está livre para uso.  
6. Clique em **OK**. O sistema agora criou uma nova conta de cliente para o cliente potencial da cotação.  
7. Feche a página.
8. No **Painel de Ação**, clique em **Acompanhamento**.
9. Clique em **Confirmar**.
10. No campo **Motivo**, insira ou selecione um valor.
11. Clique em **OK**.
12. No **Painel de Ações**, clique em **Geral**.
13. Clique em **Ordens de venda**.
14. Feche a página.

