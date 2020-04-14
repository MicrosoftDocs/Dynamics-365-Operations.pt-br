---
title: Configurar autoridades de imposto sobre vendas
description: As autoridades de impostos sobre vendas são as entidades que coletaram necessidades de impostos sobre vendas a serem informados e pagos.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc6aeb39591c68cae78537faa077010d68628b02
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144757"
---
# <a name="set-up-sales-tax-authorities"></a>Configurar autoridades de imposto sobre vendas

[!include [banner](../../includes/banner.md)]

As autoridades de impostos sobre vendas são as entidades que coletaram necessidades de impostos sobre vendas a serem informados e pagos. Você pode pagar impostos sobre vendas diretamente para a autoridade ou por meio de uma conta de fornecedor que você cria para a autoridade do imposto sobre vendas. Se você ficar isso, a empresa poderá usar suas rotinas de pagamento usuais para pagar a autoridade do imposto sobre vendas a tempo. Se você não configurar a autoridade fiscal como um fornecedor, alguém deve preparar um pagamento manual para a autoridade fiscal na data de vencimento apropriada. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Imposto > Impostos indiretos > Imposto sobre vendas > Autoridades de impostos sobre vendas.
2. Clique em Novo.
3. No campo Autoridade, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada.
8. Selecione o layout de relatório de seu país/região, se disponível. Se os layouts de relatório não corresponderem aos requisitos da autoridade de imposto sobre vendas, use o layout padrão.
9. Insira valores no formulário de arredondamento e nos campos redondos para especificar como o valor total do imposto a ser pago deve ser arredondado. Todas as diferenças de arredondamento serão lançadas para as transações automáticas configuradas na contabilidade.
10. No campo Arredondar, insira um número.
11. Clique em Salvar.

