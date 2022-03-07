---
title: Configurar códigos de imposto
description: Este tópico explica como configurar códigos de imposto no Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 594e8f0595ecace748a70860c1ccacaf90b7d279
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222182"
---
# <a name="set-up-sales-tax-codes"></a>Configurar códigos de imposto

[!include [banner](../../includes/banner.md)]

Este tópico explica como configurar códigos de imposto. Códigos de imposto são criados para cada imposto ou direito indireto que a entidade legal é obrigada a calcular, arrecadar e pagar às autoridades de imposto sobre vendas.

Esta tarefa usa a empresa de demonstração USMF.

1. Vá para **Painel de navegação > Imposto > Impostos indiretos > Imposto > Códigos de imposto**.
2. Selecione **Novo**.
3. No campo **Código de imposto**, digite um valor.
4. No campo **Nome**, digite um valor.
5. Selecione um **Período de liquidação** ao abrir a lista suspensa para especificar em que a autoridade de impostos sobre vendas e em intervalos que esses impostos sobre vendas precisem ser informado e pago.
6. Selecione um **Grupo de lançamentos contábeis** para especificar as contas principais para lançar impostos sobre vendas na contabilidade.
7. Expanda a Guia Rápida **Cálculo**. Isso inclui vários campos que controlam como os valores do imposto sobre vendas será calculado. Preencha esses campos como necessário.  
8. No **Painel de Ações**, na parte superior de interface, selecione **Código de imposto**.
9. Selecione **Valores**.
10. Insira o valor para esse código de imposto na coluna **valor**.
    - Na Guia Rápida **Cálculo**, no campo Origem, se Valor por unidade estiver selecionado, o valor será multiplicado pela quantidade da transação para calcular o valor do imposto.  Se o código de imposto não for um imposto baseado na unidade, o valor é uma porcentagem que é aplicada na origem para a qual esse código de imposto calcula o valor do imposto sobre vendas.     
11. Selecione **Salvar**.
12. Feche a página.
13. Selecione **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]