---
title: Configurar códigos de relatório de imposto
description: Os códigos de relatório de imposto fazem referência a um número em um relatório de imposto.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4543cf7eaa0b1ef8e32d3fdafa2c354cd3739256
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554199"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Configurar códigos de relatório de imposto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Os códigos de relatório de imposto fazem referência a um número em um relatório de imposto. São usados em layouts de relatório específicos do país e o Pagamento de imposto sobre vendas por código de relatório para imprimir valores de imposto sobre vendas para um período de liquidação resumidos por código de relatório. Depois que você criar os Códigos de relatórios de imposto sobre vendas, poderá fazer referência a eles na guia rápida de configuração Relatório na página Código de imposto. 

Este registro usa a empresa de dados de demonstração DEMF.



1. Vá para Imposto > Configurações > Impostos > Códigos de relatório de impostos.
2. Clique em Novo.
3. Selecione o layout de relatório ao qual o código se refere.
    * Esse layout é usado para filtrar os códigos de relatórios disponíveis para um código de imposto sobre vendas. Cada código de imposto sobre vendas pertence a um período de liquidação que pertence a uma autoridade de imposto sobre vendas que usa um layout de relatório.  
4. Insira um número que seja referenciado em um relatório de imposto sobre vendas.
5. No campo de texto Relatório, insira uma descrição para a exibição nos relatórios.
6. No campo Descrição breve, digite uma descrição para fins internos.
7. Clique em Salvar.

