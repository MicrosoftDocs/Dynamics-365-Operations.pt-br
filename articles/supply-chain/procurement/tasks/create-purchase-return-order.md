--- 
title: "Criar uma ordem de devolução de compra"
description: "Este procedimento mostra a você como criar uma ordem do retorno de compra usando a ação da nota de crédito para copiar linhas de um documento da fatura do vendedor a uma PO nova."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b9124100f84afb13acc2ac9dda7b9483afb01754
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-return-order"></a>Criar uma ordem de devolução de compra

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra a você como criar uma ordem do retorno de compra usando a ação da nota de crédito para copiar linhas de um documento da fatura do vendedor a uma PO nova. Ele igualmente mostra como confirmar a ordem e processar a expedição dos bens de volta ao vendedor. O exemplo mostrado neste procedimento pode ser usado na empresa dos dados do programa demonstrativo de USMF. Normalmente essa tarefa é realizada por um agente de compras.


## <a name="create-a-new-purchase-return-order"></a>Criar uma nova ordem de devolução
1. Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.
    * A primeira etapa é criar uma ordem de compra nova a ser usada como a ordem do retorno de compra.  
2. Clique em Novo.
3. No campo Conta de fornecedor, digite US-102.
4. Clique em OK.
5. No Painel de Ação, clique em Compra.
6. Clique em Nota de crédito.
    * Esta é a página da qual você pode copiar as faturas de fornecedor existente para sua ordem de devolução. Esta é a mesma página é usada para outras ações da cópia. Mas, como nós o abrimos da ação da nota de crédito, a página é configurada para oferecer suporte a criação de uma ordem de devolução que desativa as faturas de fornecedor.  
7. Expanda a seção Parâmetros.
    * A opção invertida do sinal é selecionada automaticamente, e não pode ser mudada. Isto assegura que o sinal esteja ajustado às quantidades, e que as linhas da ordem que são adicionadas desativarão a fatura do vendedor.  
    * A opção Copiar cargos é selecionada automaticamente, e não pode ser mudada. Isto significa que as cargas da fatura do vendedor estão adicionadas à ordem do retorno de compra para deslocar a carga original. É possível alterar mais tarde as mudanças no cabeçalho e nas linhas da ordem.  
    * A opção Copiar precisamente é selecionada automaticamente, e não pode ser mudada. Isto assegura de que uma cópia exata esteja feita dos valores em todos os campos no cabeçalho e nas linhas da fatura do vendedor. Isto significa que uma ordem do retorno de compra está criada com os valores que combinam todos os termos usados com o documento da fatura do vendedor.  
    * A opção Excluir linhas de compra exclui todas as linhas da ordem de compra que já existem na ordem de compra que você está copiando, antes de aplicar as novas linhas. Neste exemplo nós não adicionamos ainda nenhuma linhas à ordem do retorno de compra, então não teria nenhum efeito. Use esta opção com cuidado, pois ela suprime todas as linhas existentes sem aviso adicional.  
    * A opção Copiar cabeçalho da ordem é selecionada automaticamente, e não pode ser mudada. Isto assegura que a informação está copiada da fatura do vendedor e aplicada ao cabeçalho da ordem do retorno de compra. Isto é útil porque ajuda a assegurar que a ordem do retorno de compra desloque a fatura usando termos similares.  
8. Recolher a seção Parâmetros.
9. Expandir a seção Faturas.
    * A página foi aberta da ação da nota de crédito, assim que a única opção disponível é copiar a informação das faturas do vendedor. Esta aba mostra todas as faturas disponíveis para a conta do vendedor que é especificada na ordem do retorno de compra que você criou mais cedo.   As faturas são identificadas pelo comprovante da fatura ou pela identificação da ordem de compra.  
10. Encontre a fatura do vendedor identificada pelo número de fatura AP-0006, e destaque-a clicando em todo o campo nessa linha.
11. Selecione a linha clicando na caixa de verificação para a linha. 
    * Observe que as linhas disponíveis nesta fatura de fornecedor estão selecionadas automaticamente junto com a ordem. Esta fatura particular do vendedor tem 2 linhas da ordem. Para este exemplo, nós retornaremos a parte da quantidade da segunda linha.  
12. Destaque a segunda linha (a com item M0006) clicando em todo o campo nessa linha.
13. No campo Quantidade, altere a quantidade para 10. Esta é a quantidade que nós retornaremos ao vendedor. 
14. Destaque a primeira linha (a com item M0005) clicando em todo o campo nessa linha.
15. Desmarque a caixa de seleção da linha.
    * Somente as linhas que você selecionou serão copiadas a sua ordem.  
16. Recolher a seção Faturas.
17. Expanda as linhas ou o cabeçalho selecionado para a seção copiada.
    * Esta exibição mostra um sumário de todos os documentos e as linhas que você selecionou para serem copiados a sua ordem.  
18. Diminua as linhas ou o cabeçalho selecionado para a seção copiada.
19. Clique em OK.
    * A linha que você selecionou foi copiada agora a sua ordem do retorno de compra. O campo Quantidade mostra -10.   
20. Clique em Estoque.
21. Clique em Marcar.
    * A linha da ordem que foi criada é marcada contra a transação do estoque da fatura do vendedor. Isto assegura que o estoque que é retornado ao vendedor seja o mesmo estoque que foi recebido deles mais cedo. Há algumas situações onde a marcação não ocorre, por exemplo, se o estoque já foi marcado como consumido, ou se o produto é um que não usa a marcação.  
22. Clique em OK.

## <a name="confirm-and-record-the-shipment-of-goods"></a>Confirme e grave a expedição dos bens
1. Clique em Confirmar.
2. No Painel de Ação, clique em Receber.
3. Clique em Recebimento de produtos.
    * Esta página é usada para gravar o recibo do produto para ordens de compra e para processar igualmente o retorno dos bens de volta ao vendedor. As linhas da ordem com uma média negativa da quantidade dos bens devem ser retornadas ao vendedor, e o documento que pode ser gerado desta página pode ser usado como a guia de remessa para este uso.   
    * No campo Quantidade, selecione a quantidade pedida para este exemplo.   Isto assegura que a expedição está processada para a quantidade pedida completa com as quais as linhas da ordem foram criadas.   
4. No campo Recebimento de produtos, digite um valor.
    * Este campo é usado para inserir uma referência que será usada como um comprovante para o diário de recebimentos de produtos.  
5. Clique em OK.
    * Os bens foram gravados agora como enviados na ordem do retorno de compra, e um diário de recebimentos de produtos foi criado. Você pode usar a ação do recibo do produto para rever os jornais criados com a ordem de compra, e ver o que foi recebido ou retornado, e quando.  


