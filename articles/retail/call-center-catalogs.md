---
title: "Catálogos de call center"
description: "Este artigo descreve a funcionalidade específica do call center para catálogos no Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: c98cdb9c94a179577caecff7f57a99b91e4878a4
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017

---

# <a name="call-center-catalogs"></a>Catálogos do call center

[!include[banner](includes/banner.md)]


Este artigo descreve a funcionalidade específica do call center para catálogos no Microsoft Dynamics 365 for Retail.

Em um call center, você pode usar catálogos de produtos para identificar os produtos que deseja oferecer para os clientes. Os call centers usam normalmente catálogos impressos. O design e a produção de um catálogo impresso são tratados fora do Dynamics 365 for Retail. No entanto, você pode criar e armazenar um formulário digital de um catálogo usando as mesmas páginas que você usa para configurar catálogos de varejo online. Antes de criar um catálogo, você deve configurar classificações de produtos e atribuir as classificações a um call center. Então, você pode adicionar produtos ao catálogo selecionando produtos desses sortimentos. Depois que o produtos tiverem sido adicionados ao catálogo, e o catálogo estiver concluído, você deve validar o catálogo para verificar os dados. Em seguida, é necessário enviar o catálogo para revisão e aprovação. Depois que o catálogo for aprovado, ele poderá ser publicado. Quando um catálogo de call center é criado, você pode fazer um instantâneo dos dados do catálogo no momento em que o catálogo é publicado. Essa funcionalidade do instantâneo permite acessar uma versão específica do catálogo, mesmo se ele for alterado e atualizado posteriormente. Catálogos de call center também podem ser configurados para incluir os seguintes recursos opcionais:

-   **Códigos de fonte** – Códigos de fonte são usados para rastrear a resposta do cliente para endereçamentos de catálogo específicos.
-   **Produtos gratuitos** – Produtos podem ser incluídos em uma ordem do cliente sem encargos adicionais. Esses produtos são adicionados automaticamente a uma ordem quando o código de origem do catálogo é inserido na ordem.
-   **Scripts** – Os scripts são textos que um trabalhador do call center lê para um cliente quando uma ordem de venda está sendo criada. Os scripts podem incluir cumprimentos ou sugestões de compra.
-   **Layout da página** – Um layout de página captura a posição da página de produtos no catálogo impresso. Essas informações são usadas para o relatório de análise da área de catálogo.




