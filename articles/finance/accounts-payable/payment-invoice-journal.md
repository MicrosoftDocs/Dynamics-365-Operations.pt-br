---
title: Aplicar um plano de pagamentos ao diário de faturas
description: Este tópico descreve como adicionar um pagamento ao diário de faturas de fornecedores.
author: sunfzam
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: bd288ac48ef59d8e2a4e0922aa652276dddb666d
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075562"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>Aplicar um plano de pagamentos ao diário de faturas

[!include [banner](../includes/preview-banner.md)]

Na versão 10.0.25 do Microsoft Dynamics 365 Finance, agora há suporte para um plano de pagamentos no diário de faturas de fornecedores.

Para usar esta funcionalidade, você deve habilitar o recurso **Aplicar um plano de pagamentos ao diário de faturas** no gerenciamento de Recursos.

Depois que o recurso for habilitado, um novo campo **Plano de pagamentos** será adicionado à página **Diário de faturas**. Quando você cria uma linha de diário de faturas, se as condições de pagamento forem mantidas no fornecedor, e as condições de pagamento forem selecionadas no plano de pagamentos, o campo **Plano de pagamentos** é atualizado na página **Diário de faturas**.

Você pode alterar o plano de pagamentos usado, de acordo com a necessidade comercial. Durante o lançamento do diário de faturas de fornecedor, as transações abertas do fornecedor serão criadas de acordo com o plano de pagamentos.

Para revisar várias transações abertas do fornecedor que foram geradas a partir do plano de pagamentos, vá para **Contas a pagar \> Faturas \> Faturas de fornecedor em aberto** e informe o número da fatura ou a conta do fornecedor.

Para revisar ou configurar o plano de pagamentos, vá para **Contas a pagar \> Configuração de pagamento \> Plano de pagamentos**.

Para configurar as condições de pagamento e atribuir um plano de pagamentos, vá para **Contas a pagar \> Configuração de pagamento \> Condições de pagamento**.

Para manter as condições de pagamento em um fornecedor, vá para **Contas a pagar \> Todos os fornecedores**, selecione a conta do fornecedor e, em seguida, na guia **Pagamento**, defina o campo **Condições de pagamento**.

O recurso de plano de pagamentos também está disponível no processo **Registro de fatura de fornecedor**. Se um plano de pagamentos estiver selecionado no diário de registro de faturas, várias linhas de pagamento de fornecedor **não** serão geradas quando o registro de fatura for lançado. As linhas de pagamento do fornecedor serão geradas quando a fatura for aprovada.

## <a name="limitation"></a>Limitação

Para uma fatura de fornecedor pendente, se o plano de pagamentos estiver no cabeçalho da fatura, há uma página avançada que permite que os usuários editem as linhas de pagamento. (Por exemplo, os usuários podem editar a data de vencimento e o valor para cada linha de pagamento.) As linhas de pagamento geradas a partir do diário de faturas terão o valor do plano de pagamentos.

Essa funcionalidade estará disponível para o diário de faturas do fornecedor e faturas pendentes em uma versão futura.
