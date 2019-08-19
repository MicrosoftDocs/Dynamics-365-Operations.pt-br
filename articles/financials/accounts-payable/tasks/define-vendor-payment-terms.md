---
title: Definir condições de pagamento de fornecedor
description: Este tópico explica como configurar condições de pagamento para faturas de fornecedor.
author: abruer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6432d04aa821e76d67e2c430e514f4b9056d8228
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843184"
---
# <a name="define-vendor-payment-terms"></a>Definir condições de pagamento de fornecedor

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como configurar condições de pagamento para faturas de fornecedor. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para **Painel de navegação > Módulos > Contas a pagar > Configuração de pagamento > Condições de pagamento**.
2. Selecione **Novo**. A página de condições de pagamento é usada para definir como a data de vencimento será calculada. Não é usada para definir como a data de desconto à vista será calculada.  
3. No campo **Condições de pagamento**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. No campo **Dias**, insira um número. O número inserido aqui será usado para adicionar à data de vencimento, ou ao final do período identificado no método de pagamento. Por exemplo, se você selecionar **Rede**, o número será adicionado à data de vencimento. Se você selecionar **Mês atual**, ele adicionará o número ao último dia do mês atual para calcular a data de vencimento.  
6. Selecione **Salvar**.
7. Feche a página.
8. Vá para **Contas a pagar > Configuração de pagamento > Descontos à vista**.
9. Selecione **Novo**.
10. No campo **Desconto à vista**, insira uma ID.
11. No campo **Descrição**, digite um valor.
12. Se o fornecedor oferece um desconto estratificado, selecione o próximo desconto à vista após o atual ter vencido.
13. Feche a página.
14. No campo **Dias**, insira um número. A quantidade inserida no campo **Dias** será usada para calcular a Data do desconto à vista, com base na opção selecionada no campo **Líquido/atual**. Se **Líquido** foi selecionado, a quantidade será adicionada à data da fatura para determinar a data do desconto à vista. Se **Mês atual** foi selecionado, a quantidade será adicionada à data final do mês atual para determinar a data do desconto à vista.  
15. Insira a porcentagem do desconto à vista no campo **Desconto**. 
16. Insira a conta principal na qual o desconto à vista será lançado para faturas de clientes. Depois, insira a conta principal na qual o desconto à vista será lançado para faturas de fornecedor. Se **Contas de contrapartida de desconto** estiver definida como **Usar conta principal para desconto do fornecedor**, a conta principal será usada. Se a opção estiver definida como **Contas nas linhas de fatura**, o desconto à vista será lançado nas contas de ativo/despesas nas linhas da fatura.  
17. Selecione **Salvar**.

