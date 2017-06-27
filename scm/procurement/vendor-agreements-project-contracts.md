---
title: Contratos de fornecedor de pagamento quando pago
description: "Este artigo explica os termos de pago-quando-pago (PWP) para contratos de fornecedor. Os termos de PWP permitem que você retenha total ou parcialmente pagamento a um fornecedor até que o cliente no projeto pague você. Este artigo também fornece um exemplo de vida real para mostrar como você pode usar condições de PWP para um projeto."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23131
ms.assetid: 20bf1d7f-8813-4c69-9cd7-576884a7e169
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7b21d4e93ec22715d530b75f75f3ba475e561f62
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="pay-when-paid-vendor-agreements"></a>Contratos de fornecedor de pagamento quando pago

[!include[banner](../includes/banner.md)]


Este artigo explica os termos de pago-quando-pago (PWP) para contratos de fornecedor. Os termos de PWP permitem que você retenha total ou parcialmente pagamento a um fornecedor até que o cliente no projeto pague você. Este artigo também fornece um exemplo de vida real para mostrar como você pode usar condições de PWP para um projeto.

Quando você aprova um fornecedor como um subcontratado para trabalhar em um projeto, pode optar por reter o pagamento do fornecedor ou subcontratado até que o cliente pague você pelo projeto. Para reter um pagamento para um fornecedor, você estabelece condições de pagamento quando pago (PWP) ao configurar a ordem de compra com o fornecedor. Quando você cria uma ordem de compra para o fornecedor e atribui uma ID do projeto à ordem de compra, as condições PWP do projeto são associadas à ordem de compra e ao fornecedor. Na página **Faturas de fornecedor com pagamento quando pago**, você pode ver uma lista das faturas de fornecedor não pagas para uma ordem de compra, e as faturas de cliente associadas. Use esse formulário para determinar se um fornecedor será pago e quanto pagar. Por exemplo, quando um cliente paga um valor em uma fatura de projeto, você pode liberar parte ou todas as faturas de fornecedores relacionadas para pagamento. Você pode configurar condições PWP para especificar o pagamento para um fornecedor depois de receber uma porcentagem específica do pagamento relacionado de um cliente. Quando você recebe o pagamento parcial de um cliente, você pode liberar manualmente algumas das faturas de fornecedores relacionadas para pagamento. O exemplo a seguir mostra como você pode usar as condições PWP para reter o pagamento de um fornecedor ou subcontratado até receber o pagamento do cliente. Sua organização firma um contrato com um cliente para fornecer 100 computadores nos quais você deve instalar o software solicitado pelo cliente. O preço com que você e o cliente concordam para cada computador é de R$ 150,00. Você contrata os serviços de um fornecedor terceirizado para lhe fornecer os computadores. O cliente quer aprovar a qualidade dos computadores antes de o cliente pagar sua organização. A política de sua empresa é reter o pagamento de um fornecedor terceirizado até receber o pagamento do cliente em um projeto. Sendo assim, você configura o projeto com uma porcentagem PWP de 100, de modo a reter todos os pagamentos ao fornecedor até receber a liquidação total da fatura de cliente. O fornecedor cobra R$ 100,00 por cada computador. Quando o fornecedor envia os computadores para você, a remessa inclui uma fatura no valor de R$ 10.000,00 referente a 100 máquinas. Como você configurou o projeto com condições PWP, você ainda não paga o fornecedor. Depois de receber os computadores do fornecedor, você instalar o software necessário nos computadores. Quando você envia os computadores para o cliente, também envia ao cliente uma fatura de R$ 15.000,00. O cliente inspeciona os computadores e aprova a qualidade do produto. O cliente paga à sua organização o valor total da fatura do projeto. Depois de receber o pagamento total do cliente, você paga R$ 10.000,00 ao fornecedor pelo valor total da fatura de fornecedor.




