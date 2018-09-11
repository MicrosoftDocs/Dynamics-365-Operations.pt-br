--- 
title: "Criar e editar cotações de venda"
description: "Este procedimento demonstrativos como criar e atualizar uma cotação de venda."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f56b495131836689395a2124d5a834579e1646b7
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-edit-sales-quotations"></a>Criar e editar cotações de venda

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento demonstrativos como criar e atualizar uma cotação de venda. Você pode realizar esse procedimento em seus próprios dados ou na empresa USMF de dados de demonstração.


## <a name="create-a-sales-quotation"></a>Criar uma cotação de venda
1. Vá para Vendas e marketing > Cotações de venda > Todas as cotações.
2. Clique em Novo.
3. No campo Tipo de conta, selecione 'Cliente potencial'.
4. No campo Cliente potencial, insira ou selecione um valor.
5. Expanda a seção Geral.
    * Como você optou por criar uma cotação da área Vendas e Marketing, o tipo é automaticamente definido como Cotação de venda. Para criar uma cotação para um projeto, você deverá acessá-lo do módulo Gerenciamento e contabilidade de projeto.   
6. Clique em OK.
    * Os campos e as ações nas linhas da cotação são muito semelhantes aos das linhas de ordem de venda.   Como as ordens de venda, as cotações podem ser criadas para um item específico, ou quando o número do item não é conhecido ou não existe no momento da criação da cotação, as cotações podem ser criadas para uma categoria de vendas.  
7. No campo Item, insira ou selecione um valor.
8. No campo Item, digite um valor.
9. Feche a página.
10. No campo Quantidade, insira um número.
    * Se houver contratos comerciais válidos para o item selecionado na linha, o preço e os descontos aplicáveis serão copiados automaticamente para a linha de cotação. Certifique-se de que o campo Preço unitário contém um valor e você também pode inserir valores de desconto, se quiser.  
11. Clique em Salvar.
12. No Painel de Ação, clique em Cotação de venda.
13. Clique em Totais.
14. Clique em OK.
15. Clique em Linha de cotação de venda.
16. Clique em Preços.
    * Na página Executar simulação de preço você pode tentar ajustar a receita esperada ou a lucratividade de sua cotação, com base no preço unitário, no valor do desconto, na porcentagem de desconto, no valor total, na margem ou no índice de contribuição.   Quando estiver satisfeito com os números de destino, aplique a sugestão à linha de cotação e os campos relacionados ao preço serão atualizados adequadamente.  
    * Você pode criar quantas simulações de preço quiser. Quando você clica em Novo, as condições de preço da linha da cotação atual serão copiadas para a página. Você poderá modificar os valores de quaisquer campos relacionados a preço para os de destino. Uma alteração em um dos campos disparará o recálculo em todos os campos restantes. Para que o sistema calcule o índice de margem de contribuição e de venda, o custo unitário do produto deve ser conhecido. Use a guia Preços simulados para obter uma exibição detalhada dos preços originais, das alterações propostas e seus efeitos nos totais da cotação.   Como regra geral, quando uma simulação que define um novo valor é aplicada à linha de cotação, o sistema recalcula e insere um novo valor no campo Preço unitário. Se a simulação for baseada em uma nova margem ou em um novo índice de contribuição, somente o campo Valor líquido será atualizado, e o Preço unitário ficará em branco. Nos dois casos, quaisquer descontos que ocorreram na linha da cotação antes da simulação serão excluídos.  
17. Feche a página.
18. No Painel de Ação, clique em Cotação.
19. Clique em Enviar cotação.
20. Selecione Sim no campo Imprimir cotação.
21. Clique em OK.
    * O relatório pode levar um minuto para ser gerado. Não feche a página até que isso ocorra.  
22. Feche a página.

## <a name="update-a-sales-quotation"></a>Atualizar uma cotação de venda
1. No Painel de Ação, clique em Acompanhamento.
2. Clique em Converter em cliente.
3. No campo Conta de cliente, insira um valor.
4. Clique em Verificar.
    * Verifique se aparece uma mensagem indicando que o número de conta que você digitou está livre para uso.  
5. Clique em OK.
    * O sistema agora criou uma nova conta de cliente para o cliente potencial da cotação.  
6. Feche a página.
7. No Painel de Ação, clique em Acompanhamento.
8. Clique em Confirmar.
9. No campo Motivo, insira ou selecione um valor.
10. Clique em OK.
11. No Painel de Ação, clique em Geral.
12. Clique em Ordens de venda.
13. Feche a página.


