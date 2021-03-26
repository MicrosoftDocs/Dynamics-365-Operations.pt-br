---
title: Editar dimensões financeiras para transações de varejo
description: Este tópico descreve como editar dimensões financeiras para transações de varejo no Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4d4b7e383ca2089ee98e70d23ccd890d0e6a86c5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221789"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>Editar dimensões financeiras para transações de varejo

[!include [banner](../includes/banner.md)]

Este tópico descreve como editar dimensões financeiras para transações de varejo no Microsoft Dynamics 365 Commerce.

## <a name="edit-financial-dimensions"></a>Editar dimensões financeiras

Para editar dimensões financeiras para transações de varejo na matriz do Commerce, siga estas etapas:

1. Abra a página **Configuração de dimensões financeiras para integração de aplicativos**.
1. Selecione o registro **Integração de dimensões padrão** ativo.
1. Na FastTab **Dimensões financeiras**, certifique-se de que todas as dimensões que você deseja editar na planilha do Excel estejam presentes na lista **Selecionado**. Para obter mais informações, consulte [Entidades de dados](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).
1. Baixe e abra o arquivo Excel na página **Demonstrativos**, na página **Transações de varejo** ou no bloco **Falhas na validação de transações** no espaço de trabalho **Finanças da loja**.
1. Para alterar a dimensão financeira da transação, selecione **Design** e selecione o símbolo de lápis ao lado da linha **Transação (auditável)**.
1. Encontre e selecione o campo **FinancialDimensionDisplayValue**, selecione uma célula na parte do cabeçalho da planilha do Excel e selecione **Adicionar rótulo**.
1. Selecione uma célula abaixo da célula selecionada na etapa anterior, selecione **Adicionar valor** e, sem seguida, selecione **Atualizar**. As dimensões financeiras serão adicionadas à planilha do Excel e poderão ser editadas e publicadas.
1. Para alterar as dimensões nas linhas de transação, selecione a linha **Transações de vendas (auditável)**, selecione o símbolo de lápis e repita as etapas 6 e 7.
1. Para alterar as dimensões nas linhas de pagamento, selecione a linha **Transações de pagamento (auditável)**, selecione o símbolo de lápis e repita as etapas 6 e 7.

## <a name="additional-resources"></a>Recursos adicionais

[Editar e auditar transações cash and carry e de gerenciamento de caixa](edit-cash-trans.md)

[Editar e auditar transações da ordem do cliente assíncronas e ordem online](edit-order-trans.md)

[Criar uma pasta de trabalho do Excel para editar transações de varejo](create-excel-edit.md)

[Adicionar campos a uma pasta de trabalho do Excel para editar transações de varejo](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]