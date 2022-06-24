---
title: Configurar códigos de imposto
description: Este artigo explica como configurar códigos de imposto no Dynamics 365 Finance.
author: twheeloc
ms.date: 09/27/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b12133583f40cc17cb85f6dbd86697592af25caf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858458"
---
# <a name="set-up-sales-tax-codes"></a>Configurar códigos de imposto

[!include [banner](../../includes/banner.md)]

Este artigo explica como configurar códigos de imposto. Códigos de imposto são criados para cada imposto ou direito indireto que a entidade legal é obrigada a calcular, arrecadar e pagar às autoridades de imposto sobre vendas.

Esta tarefa usa a empresa de demonstração USMF.

1. Acesse **Painel de navegação > Imposto > Impostos indiretos > Imposto > Códigos de imposto**.
2. Selecione **Novo**.
3. No campo **Código de imposto**, digite um valor.
4. No campo **Nome**, digite um valor.
5. Selecione um **Período de liquidação** ao abrir a lista suspensa para especificar em que a autoridade de impostos sobre vendas e em intervalos que esses impostos sobre vendas precisem ser informado e pago.
6. Selecione um **Grupo de lançamentos contábeis** para especificar as contas principais para lançar impostos sobre vendas na contabilidade.
7. Expanda a Guia Rápida **Cálculo**. Isso inclui vários campos que controlam como os valores do imposto sobre vendas será calculado. Preencha esses campos como necessário.  
8. No **Painel de Ações**, na parte superior de interface, selecione **Código de imposto**.
9. Selecione **Valores**.
10. Insira o valor para esse código de imposto na coluna **valor**.

    Na FastTab **Cálculo**, no campo **Origem**, se **Valor por unidade** estiver selecionado, o valor será multiplicado pela quantidade na transação para calcular o valor do imposto.  Se o código de imposto não for um imposto baseado na unidade, o valor será uma porcentagem aplicada na origem para a qual esse código de imposto calcula o valor do imposto sobre vendas.     

11. Selecione **Salvar**.
12. Feche a página.
13. Selecione **Salvar**.

A partir do Microsoft Dynamics 365 Finance versão 10.0.22, se você estiver usando o [Serviço de imposto](../../localizations/global-tax-calcuation-service-overview.md) e o recurso [**Oferecer suporte a vários números de inscrição de IVA**](../../localizations/emea-multiple-vat-registration-numbers.md) estiver habilitado no espaço de trabalho **Gerenciamento de recursos**, você poderá usar o campo **Tipo de imposto** para especificar o tipo do código de imposto. Os valores a seguir estão disponíveis:

- IVA Padrão
- IVA reduzido
- 0% de IVA
- Imposto embutido
- Outro

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
