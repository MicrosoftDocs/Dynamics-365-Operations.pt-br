---
title: Editar dimensões financeiras para transações de varejo
description: Este artigo descreve como editar dimensões financeiras para transações de varejo no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: b382907cd79a13319601dd694261319875565947
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268384"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>Editar dimensões financeiras para transações de varejo

[!include [banner](../includes/banner.md)]

Este artigo descreve como editar dimensões financeiras para transações de varejo no Microsoft Dynamics 365 Commerce.

## <a name="edit-financial-dimensions"></a>Editar dimensões financeiras

Para editar dimensões financeiras para transações de varejo na matriz do Commerce, siga estas etapas:

1. Abra a página **Configuração de dimensões financeiras para integração de aplicativos**.
1. Selecione o registro **Integração de dimensões padrão** ativo.
1. Na Guia Rápida **Dimensões financeiras**, certifique-se de que todas as dimensões que você deseja editar na planilha do Excel estejam presentes na lista **Selecionado**. Para obter mais informações, consulte [Entidades de dados](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).
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
