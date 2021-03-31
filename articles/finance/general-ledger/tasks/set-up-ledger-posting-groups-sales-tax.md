---
title: Configurar grupos de lançamento contábil do imposto
description: Os impostos são calculados e lançados nas contas principais que são especificadas nos grupos de lançamentos contábeis.
author: twheeloc
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAccountGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1860f338faf357ecb8faa04cc687a6ec08cdc6c3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222254"
---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Configurar grupos de lançamento contábil do imposto

[!include [banner](../../includes/banner.md)]

Os impostos são calculados e lançados nas contas principais que são especificadas nos grupos de lançamentos contábeis. Os grupos de lançamentos contábeis são associados a cada código de imposto sobre vendas. Você pode configurar grupos de lançamentos contábeis individuais para cada código de imposto sobre vendas; também pode usar um grupo para todos os códigos ou atribuir múltiplos grupos aos códigos. Este registro usa a empresa de dados de demonstração DEMF. 

1. Vá para **Painel de Navegação > Módulos > Imposto > Configuração > Imposto sobre vendas > Grupos de lançamento do razão**.
2. Clique em **Novo**.
3. No campo grupo de **Lançamento do razão**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. No campo **Imposto sobre vendas a pagar**, selecione a conta principal para impostos sobre vendas de saída que estão a pagar para a autoridade fiscal. Os impostos sobre vendas serão coletados em nome da autoridade de imposto quando vender mercadorias e serviços tributáveis.  
6. No campo **Imposto sobre vendas recebidas**, selecione a conta principal para impostos sobre vendas de entrada que são recebidos da autoridade fiscal. Os fornecedores coletam impostos em nome da autoridade de imposto quando você comprar mercadorias e serviços tributáveis. Esse campo não está disponível se a opção Aplicar regras de taxação de impostos estiver selecionada na página **Parâmetros da contabilidade**. Em vez disso, os impostos sobre vendas que são pagos para fornecedores para a mesma conta que as compras.   
7. No campo **Despesas de imposto sobre o uso**, selecione a conta principal para lançar o imposto sobre o uso dedutível que não foi reclamado ou relatado à Secretaria da Fazenda pelos fornecedores como parte dos encargos revertidos GST/HST da UE. A opção de **Imposto sobre o uso** deve ser selecionada para o **Código do imposto** no **Grupo de impostos** usado na transação. Esse campo não estará disponível se a opção **Aplicar regras de taxação de impostos** estiver selecionada na página **Parâmetros da contabilidade**.   
8. No campo **Imposto sobre vendas a pagar**, selecione a conta principal para Impostos recebíveis que são pagáveis para as autoridades de imposto. A opção de **Imposto sobre o uso** deve ser selecionada no **Código de imposto** no **Grupo de imposto** para lançar **Imposto sobre uso**. Se a opção **Aplicar regras de tributação de imposto sobre vendas** estiver selecionada na página **Parâmetros da contabilidade**, a contrapartida é lançada na conta de despesas da transação.   
9. No campo **Conta de liquidação**, selecione a conta principal que o saldo líquido das contas razão especificou nos campos **Imposto sobre o uso a pagar** e **Imposto a receber** será lançado. O saldo será criado quando os trabalhos de liquidação e lançamento de impostos forem executados.  Se a autoridade fiscal para o período de liquidação estiver associada a uma conta de fornecedor, o saldo será lançado na conta de fornecedor.
10. No campo **Desconto à vista do fornecedor**, selecione a conta principal para lançar o desconto à vista para os códigos de impostos sobre vendas associados a esse grupo de lançamentos contábeis. Isso é opcional e se nenhuma conta for inserida, a conta principal em **Códigos de desconto à vista** será usada. Pode ser útil usar contas diferentes para o grupo de **Lançamentos contábeis** se usar os impostos sobre vendas que podem ser revertidos na opção de desconto à vista em grupos de impostos sobre vendas.  
11. No campo **Desconto de caso de cliente**, selecione a conta principal para lançar o desconto à vista para os **Códigos de impostos sobre vendas** associados a esse grupo de **Lançamentos contábeis**. Isso é opcional e se nenhuma conta for inserida, a conta principal nos **Códigos de desconto à vista** será usada. Pode ser útil usar contas diferentes para o grupo de **Lançamentos contábeis** se usar os impostos sobre vendas que podem ser revertidos na opção de desconto à vista em grupos de **Impostos sobre vendas**.  
12. Clique em **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]