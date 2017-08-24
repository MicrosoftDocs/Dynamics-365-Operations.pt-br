--- 
title: "Configurar grupos de lançamento contábil do imposto sobre vendas"
description: "Os impostos sobre vendas são calculados e lançados nas contas principais que são especificadas nos grupos de lançamentos contábeis."
author: twheeloc
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
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: e0682afed4664e1491ed46e4e40f467015701711
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Configurar grupos de lançamento contábil do imposto sobre vendas

[!include[task guide banner](../../includes/task-guide-banner.md)]

Os impostos sobre vendas são calculados e lançados nas contas principais que são especificadas nos grupos de lançamentos contábeis. Os grupos de lançamentos contábeis são associados a cada código de imposto sobre vendas. Você pode configurar grupos de lançamentos contábeis individuais para cada código de imposto sobre vendas; também pode usar um grupo para todos os códigos ou atribuir múltiplos grupos aos códigos. Este registro usa a empresa de dados de demonstração DEMF. 

1. Vá para Imposto > Configuração > Imposto sobre vendas > Grupos de lançamento do razão.
2. Clique em Novo.
3. No campo grupo de Lançamento do razão, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Imposto sobre vendas a pagar, selecione a conta principal para impostos sobre vendas de saída que estão a pagar para a autoridade fiscal.
    * Os impostos sobre vendas serão coletados em nome da autoridade de imposto quando vender mercadorias e serviços tributáveis.  
6. No campo Imposto sobre vendas recebidas, selecione a conta principal para impostos sobre vendas de entrada que são recebidos da autoridade fiscal.
    * Os fornecedores coletam impostos em nome da autoridade de imposto quando você comprar mercadorias e serviços tributáveis. Esse campo não está disponível se a opção Aplicar regras de taxação de impostos estiver selecionada na página Parâmetros da contabilidade. Em vez disso, os impostos sobre vendas que são pagos para fornecedores para a mesma conta que as compras.   
7. No campo Despesas de imposto sobre o uso, selecione a conta principal para lançar o imposto sobre o uso dedutível que não foi reclamado ou relatado à Secretaria da Fazenda pelos fornecedores como parte dos encargos revertidos GST/HST da UE.
    * A opção de imposto sobre o uso precisa ser selecionada para o código do imposto sobre vendas no grupo de impostos sobre vendas que é usado na transação.  Esse campo não está disponível se a opção Aplicar regras de taxação de impostos estiver selecionada na página Parâmetros da contabilidade.   
8. No campo Imposto sobre vendas a pagar, selecione a conta principal para Impostos recebíveis que são pagáveis para as autoridades de imposto.
    * A opção de imposto precisa ser selecionada no código do imposto no grupo de imposto para lançar imposto sobre uso. Se Aplicar a opção de regras de tributação de imposto sobre vendas estiver selecionado nos parâmetros da contabilidade, a contrapartida é lançada na conta de despesas da transação.   
9. No campo Conta de liquidação, selecione a conta principal que o saldo líquido das contas contábeis especificadas no imposto sobre o uso a pagar e campos a receber de imposto sobre vendas será lançado.
    * O saldo será criado quando os trabalhos de liquidação e lançamento de impostos sobre vendas forem executados.  Se a autoridade de imposto para o período de liquidação for associado a uma conta de fornecedor, o saldo será lançado na conta de fornecedor.   
10. No campo Desconto à vista do fornecedor, selecione a conta principal para lançar o desconto à vista para os códigos de impostos sobre vendas associados a esse grupo de lançamentos contábeis.
    * Isso é opcional e se nenhuma conta for inserida, a conta principal em códigos de desconto à vista será usada. Pode ser útil usar contas diferentes para o grupo de lançamentos contábeis se usar os impostos sobre vendas que podem ser revertidos na opção de desconto à vista em grupos de impostos sobre vendas.  
11. No campo Desconto de caso de cliente, selecione a conta principal para lançar o desconto à vista para os códigos de impostos sobre vendas associados a esse grupo de lançamentos contábeis.
    * Isso é opcional e se nenhuma conta for inserida, a conta principal nos Códigos de desconto à vista será usada. Pode ser útil usar contas diferentes para o grupo de lançamentos contábeis se usar os impostos sobre vendas que podem ser revertidos na opção de desconto à vista em grupos de impostos sobre vendas.  
12. Clique em Salvar.


