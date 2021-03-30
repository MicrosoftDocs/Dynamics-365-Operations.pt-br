---
title: Configurar códigos de relatório de imposto
description: Os Códigos de relatório de imposto fazem referência a um número listado um relatório de imposto.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: be24e18da63d1a613c3c6e72f7c767c7af9b6656
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222134"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Configurar códigos de relatório de imposto

[!include [banner](../../includes/banner.md)]

Os Códigos de relatório de imposto fazem referência a um número listado um relatório de imposto. Eles são usados em layouts de relatório específicos de um país/região. Eles também são usados no relatório Pagamento de imposto por código. Esse relatório mostra os valores de imposto para um período de liquidação resumido para cada código de relatório. Depois que você criar os Códigos de relatórios de imposto, poderá fazer referência a eles nas Guias Rápidas Configuração de relatório, que podem ser acessadas na página **Código de imposto**. 

Este registro usa a empresa de dados de demonstração DEMF.

1. No **Painel de navegação**, acesse **Imposto > Configuração > Imposto > Códigos de relatório de imposto**.
2. Clique em **Novo**.
3. Selecione o layout de relatório ao qual o código se refere. Esse layout é usado para filtrar os códigos de relatórios disponíveis para um código de imposto. Cada código de imposto pertence a um período de liquidação que pertence a uma Autoridade de imposto que usa um layout de relatório.  
4. No campo **Código do relatório**, insira um número.
5. No campo **Texto do relatório**, insira uma descrição para a exibição nos relatórios.
6. No campo **Descrição breve**, digite uma descrição para fins internos.
7. Clique em **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]