---
title: Aplicar automaticamente os pagamentos antecipados para faturas de fornecedores
description: Este tópico descreve a capacidade de aplicar automaticamente pagamentos antecipados às faturas de fornecedores.
author: sunfzam
ms.date: 10/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5b07c1d4c2189184b2ad29d46ec2aef0ee03c1c0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985353"
---
# <a name="automatically-apply-to-vendor-invoices"></a>Aplicar automaticamente às faturas de fornecedores

[!include [banner](../includes/banner.md)]

Este tópico descreve a capacidade de aplicar automaticamente pagamentos antecipados às faturas de fornecedores. Um pagamento antecipado pode ser criado para uma ordem de compra como parte de um contrato de compra. Depois que uma fatura de fornecedor é recebida, o pagamento antecipado pode ser usado para liquidar as contas a pagar da fatura de fornecedor. O novo recurso permite que o sistema use automaticamente números de ordem de compra em uma fatura de fornecedor para procurar pagamentos antecipados correspondentes quando a fatura de fornecedor é importada.

Se os pagamentos antecipados forem encontrados e puderem ser aplicados, as linhas serão adicionadas às linhas da fatura existente para aplicar os pagamentos antecipados. As linhas de pagamento antecipado nunca são consideradas durante o processo de conciliação de faturas.

Os pontos a seguir descrevem como os pagamentos antecipados são aplicados quando diferentes processos de compra são seguidos:

- **Uma fatura de fornecedor por ordem de compra** – o pagamento antecipado da ordem de compra será aplicado à fatura do fornecedor.
- **Uma fatura de fornecedor para várias ordens de compra** – os pagamentos antecipados de todas as ordens de compra serão aplicados à fatura de fornecedor.
- **Várias faturas de fornecedor por ordem de compra** – o pagamento antecipado da ordem de compra será aplicado à primeira fatura de fornecedor importada. Se o valor do pagamento antecipado exceder o valor da fatura, a aplicação do pagamento antecipado falhará e você deverá aplicar manualmente o pagamento antecipado.
- **Várias faturas de fornecedor para várias ordens de compra** – os pagamentos antecipados de ordens de compra serão aplicados à primeira fatura relevante. Se o valor do pagamento antecipado exceder o valor da fatura, a aplicação do pagamento antecipado falhará e você deverá aplicar manualmente os pagamentos antecipados. Se houver pagamentos antecipados que permanecem depois que os pagamentos antecipados forem aplicados à primeira fatura, eles podem ser aplicados às faturas que seguem.

Se o sistema tentar aplicar um pagamento antecipado, mas a aplicação falhar, o comportamento dependerá da configuração da opção **Bloquear processo de automação de acompanhamento em caso de falha na aplicação de pagamento antecipado**:

- **Sim** – a mensagem de erro "Aplicação automática de pagamento antecipado: Com falha" é adicionada ao histórico de automação e a fatura permanece na lista de faturas de fornecedor pendentes. A fatura permanecerá bloqueada até que você aplique manualmente o pagamento antecipado.

    Para aplicar manualmente pagamentos antecipados, acesse a fatura de fornecedor pendente. Na página **Detalhes da fatura**, defina a opção **Incluir no processamento automatizado** para a fatura bloqueada como **Não**. Agora você pode aplicar manualmente o pagamento antecipado. Depois que o pagamento antecipado tiver sido aplicado, defina a opção **Incluir no processamento automatizado** novamente como **Sim** para que a fatura possa ser processada automaticamente.

    Você também pode ignorar a aplicação automática do pagamento antecipado definindo a opção **Incluir no processamento automatizado** como **Não** e, em seguida, configurando-a novamente como **Sim**. Você receberá a seguinte mensagem: "Já existe um pagamento antecipado para a ordem de compra. Deseja ignorá-lo para a fatura de fornecedor selecionada?" Selecione **Sim**. A mensagem "A aplicação de pagamento antecipado foi ignorada manualmente" é adicionada ao histórico de automação e a fatura de fornecedor não será bloqueada quando o processo automatizado for executado novamente.

- **Não** – os processos de automação de acompanhamento continuarão. Você ainda pode aplicar o pagamento antecipado durante a liquidação.
