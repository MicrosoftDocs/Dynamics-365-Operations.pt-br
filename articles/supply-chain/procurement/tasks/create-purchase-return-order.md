---
title: Criar uma ordem de devolução de compra
description: Este procedimento mostra a você como criar uma ordem do retorno de compra usando a ação da nota de crédito para copiar linhas de um documento da fatura do vendedor a uma PO nova.
author: GalynaFedorova
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying, InventMarking, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 841229434fc278224f85d8d6782f80a31f4e23a9
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678705"
---
# <a name="create-a-purchase-return-order"></a>Criar uma ordem de devolução de compra

[!include [banner](../../includes/banner.md)]

Este procedimento mostra a você como criar uma ordem do retorno de compra usando a ação da nota de crédito para copiar linhas de um documento da fatura do vendedor a uma PO nova. Ele igualmente mostra como confirmar a ordem e processar a expedição dos bens de volta ao vendedor. O exemplo mostrado neste procedimento pode ser usado na empresa dos dados do programa demonstrativo de USMF. Normalmente essa tarefa é realizada por um agente de compras.

## <a name="create-a-new-purchase-return-order"></a>Criar uma nova ordem de devolução
1. Acesse **Painel de navegação > Módulos > Compras e fornecimento > Ordens de compra > Todas as ordens de compra**. A primeira etapa é criar uma ordem de compra nova a ser usada como a ordem do retorno de compra.  
2. Clique em **Novo**.
3. No campo **Conta de fornecedor**, digite "US-102".
4. Clique em **OK**.
5. No **Painel de Ações**, clique em **Compra**.
6. Clique em **Nota de crédito**. Esta é a página da qual você pode copiar as faturas de fornecedor existente para sua ordem de devolução. Esta é a mesma página é usada para outras ações da cópia. Mas, como nós o abrimos da ação da nota de crédito, a página é configurada para oferecer suporte a criação de uma ordem de devolução que desativa as faturas de fornecedor.  
7. Expanda a seção **Parâmetros**.
    - A opção **Reverter sinal** é selecionada automaticamente e não pode ser alterada. Isto assegura que o sinal esteja ajustado às quantidades, e que as linhas da ordem que são adicionadas desativarão a fatura do vendedor.  
    - A opção **Copiar encargos** é selecionada automaticamente e não pode ser alterada. Isto significa que as cargas da fatura do vendedor estão adicionadas à ordem do retorno de compra para deslocar a carga original. É possível alterar mais tarde as mudanças no cabeçalho e nas linhas da ordem.  
    - A opção **Copiar exatamente** é selecionada automaticamente e não pode ser alterada. Isto assegura de que uma cópia exata esteja feita dos valores em todos os campos no cabeçalho e nas linhas da fatura do vendedor. Isto significa que uma ordem do retorno de compra está criada com os valores que combinam todos os termos usados com o documento da fatura do vendedor. 
    - A opção **Excluir linhas de compra** exclui todas as linhas da ordem de compra que já existem na ordem de compra antes de adicionar as novas linhas. Neste exemplo nós não adicionamos ainda nenhuma linhas à ordem do retorno de compra, então não teria nenhum efeito. Use esta opção com cuidado, pois ela suprime todas as linhas existentes sem aviso adicional.  
    * A opção **Copiar cabeçalho da ordem** é selecionada automaticamente e não pode ser alterada. Isto assegura que a informação está copiada da fatura do vendedor e aplicada ao cabeçalho da ordem do retorno de compra. Isto é útil porque ajuda a assegurar que a ordem do retorno de compra desloque a fatura usando termos similares.  
8. Recolha a seção **Parâmetros**.
9. Expanda a seção **Faturas**. A página foi aberta da ação da nota de crédito, assim que a única opção disponível é copiar a informação das faturas do vendedor. Esta aba mostra todas as faturas disponíveis para a conta do vendedor que é especificada na ordem do retorno de compra que você criou mais cedo.   As faturas são identificadas pelo comprovante da fatura ou pela identificação da ordem de compra.
10. Encontre a fatura do vendedor identificada pelo número de fatura AP-0006, e destaque-a clicando em todo o campo nessa linha.
11. Selecione a linha clicando na caixa de verificação para a linha. Observe que as linhas disponíveis nesta fatura de fornecedor estão selecionadas automaticamente junto com a ordem. Esta fatura particular do vendedor tem 2 linhas da ordem. Para este exemplo, nós retornaremos a parte da quantidade da segunda linha.
12. Destaque a segunda linha (a com item M0006) clicando em todo o campo nessa linha.
13. No campo **Quantidade**, altere a quantidade para 10. Esta é a quantidade que nós retornaremos ao vendedor. 
14. Destaque a primeira linha (a com item M0005) clicando em todo o campo nessa linha.
15. Desmarque a caixa de seleção da linha. Somente as linhas que você selecionou serão copiadas a sua ordem.
16. Recolha a seção **Faturas**.
17. Expanda a seção **Linhas ou cabeçalho selecionados para cópia**. Esta exibição mostra um sumário de todos os documentos e as linhas que você selecionou para serem copiados a sua ordem.  
18. Recolha a seção **Linhas ou cabeçalho selecionados para cópia**.
19. Clique em **OK**. A linha que você selecionou foi copiada agora a sua ordem do retorno de compra. O campo **Quantidade** mostra -10.   
20. Na seção **Linha da ordem de compra**, clique em **Estoque**.
21. Clique em **Marcação**. A linha da ordem que foi criada é marcada contra a transação do estoque da fatura do vendedor. Isto assegura que o estoque que é retornado ao vendedor seja o mesmo estoque que foi recebido deles mais cedo. Há algumas situações onde a marcação não ocorre, por exemplo, se o estoque já foi marcado como consumido, ou se o produto é um que não usa a marcação.  

22. Clique em **OK**.

## <a name="confirm-and-record-the-shipment-of-goods"></a>Confirme e grave a expedição dos bens
1. Clique em **Ações > Confirmar**.
2. No **Painel de Ação**, clique em **Receber**.
3. Clique em **Recebimento de produtos**.
    - Esta página é usada para gravar o recibo do produto para ordens de compra e para processar igualmente o retorno dos bens de volta ao vendedor. As linhas da ordem com uma média negativa da quantidade dos bens devem ser retornadas ao vendedor, e o documento que pode ser gerado desta página pode ser usado como a guia de remessa para este uso.   
    - No campo **Quantidade**, selecione a Quantidade encomendada para este exemplo. Isto assegura que a expedição está processada para a quantidade pedida completa com as quais as linhas da ordem foram criadas.   
4. No campo **Recebimento de produtos**, digite um valor. Este campo é usado para inserir uma referência que será usada como um comprovante para o diário de recebimentos de produtos.  
5. Clique em **OK**. Os bens foram gravados agora como enviados na ordem do retorno de compra, e um diário de recebimentos de produtos foi criado. Você pode usar a ação do recibo do produto para rever os jornais criados com a ordem de compra, e ver o que foi recebido ou retornado, e quando.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]