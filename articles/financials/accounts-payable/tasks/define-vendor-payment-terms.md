--- 
title: "Definir condições de pagamento de fornecedor"
description: Configurar termos de pagamento para as faturas de fornecedores.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a00ca73b1bc301960132a86846749d12c39ed3f7
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="define-vendor-payment-terms"></a>Definir condições de pagamento de fornecedor

[!include[task guide banner](../../includes/task-guide-banner.md)]

Configurar termos de pagamento para as faturas de fornecedores. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contas a pagar > Configurar pagamento > Termos de pagamento.
2. Clique em Novo.
    * A página de condições de pagamento é usada para definir como a data de vencimento será calculada. Não é usada para definir como a data de desconto à vista será calculada.  
3. No campo Termos de pagamento, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Dias, insira um número.
    * O número inserido aqui será usado para adicionar à data de vencimento, ou ao final do período identificado no método de pagamento. Por exemplo, se você selecionar a rede, o número será adicionado à data de vencimento. Se você selecionar o mês atual, adicionará o número ao último dia do mês atual para calcular a data de vencimento.  
6. Clique em Salvar.
7. Feche a página.
8. Vá para Contas a pagar > Configurar pagamento > Descontos à vista.
9. Clique em Novo.
10. No campo Desconto à vista, insira uma ID.
11. No campo Descrição, digite um valor.
12. Se o fornecedor oferece um desconto estratificado, selecione o próximo desconto à vista após o atual ter vencido.
13. Feche a página.
14. No campo Dias, insira um número.
    * A quantidade inserida no campo de dias será usada para calcular a data do desconto à vista, com base na opção selecionada no campo líquido/atual. Se o líquido foi selecionado, a quantidade será adicionada à data da nota fiscal para determinar a data do desconto à vista. Se o Mês atual foi selecionado, a quantidade será adicionada à data final do mês atual para determinar a data do desconto à vista.  
15. Insira a porcentagem do desconto à vista no campo Desconto. 
16. Insira a conta principal a qual o desconto à vista será lançado para as notas fiscais do cliente.
17. Insira a conta principal a qual o desconto à vista será lançado para as notas fiscais do fornecedor.
    * Se 'Contas de contrapartida de desconto' são definidas para usar a conta principal para o desconto do fornecedor, a conta principal será usada.  Se a opção estiver definida para Contas nas linhas de fatura, o desconto à vista será lançado às contas de ativo/despesas nas linhas da fatura.  
18. Clique em Salvar.


