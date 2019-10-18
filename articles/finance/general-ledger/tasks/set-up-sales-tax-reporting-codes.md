---
title: Configurar códigos de relatório de imposto
description: Os códigos de relatório de imposto fazem referência a um número em um relatório de imposto.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4751256858da417ec9bb1b7d9ccd16fb6bef1cac
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185925"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Configurar códigos de relatório de imposto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Os códigos de relatório de imposto fazem referência a um número em um relatório de imposto. São usados em layouts de relatório específicos do país e o Pagamento de imposto sobre vendas por código de relatório para imprimir valores de imposto sobre vendas para um período de liquidação resumidos por código de relatório. Depois que você criar os Códigos de relatórios de imposto sobre vendas, poderá fazer referência a eles na guia rápida de configuração Relatório na página Código de imposto. 

Este registro usa a empresa de dados de demonstração DEMF.

1. No **Painel de navegação**, acesse **Imposto > Configuração > Imposto > Códigos de relatório de imposto**.
2. Clique em **Novo**.
3. Selecione o layout de relatório ao qual o código se refere. Esse layout é usado para filtrar os códigos de relatórios disponíveis para um código de imposto sobre vendas. Cada código de imposto sobre vendas pertence a um período de liquidação que pertence a uma autoridade de imposto sobre vendas que usa um layout de relatório.  
4. No campo **Código do relatório**, insira um número.
5. No campo **Texto do relatório**, insira uma descrição para a exibição nos relatórios.
6. No campo **Descrição breve**, digite uma descrição para fins internos.
7. Clique em **Salvar**.

