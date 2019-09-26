---
title: Exibir ativo
description: Este tópico descreve a exibição de ativos no Asset Management.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63e5ec5b2a47706763df8105932d722986535a9b
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783067"
---
# <a name="asset-view"></a>Exibir ativo

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Este tópico descreve a exibição de ativos no Asset Management. A página **Exibição de ativos** mostra os ativos e locais funcionais em uma exibição de árvore. Portanto, você pode obter com facilidade uma visão geral das relações de ativos a locais funcionais. Além disso, você pode exibir informações detalhadas sobre locais funcionais, ativos e listas de materiais (BOMs) relacionadas. Você também pode obter uma rápida visão geral de solicitações de manutenção ativa e ordens de serviço relacionadas a um ativo.

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Exibição de ativos**.
2. Para alterar a exibição mostrada na página, selecione um novo valor no campo **Exibir**.

    > [!NOTE]
    > A exibição padrão que é mostrada quando você abre a página **Exibição de ativos** depende do valor selecionado no campo **Exibir** na guia **Ativos** da página **Parâmetros de gerenciamento de ativos** (**Gerenciamento de ativos** \> **Configuração** \> **Parâmetros de gerenciamento de ativos**).

No lado direito da página, as Guias Rápidas mostram detalhes de exibição selecionada.

A trilha de navegação que aparece acima da exibição de árvore mostra a seleção atual na exibição de árvore. Essa trilha de navegação usa o seguinte formato:

ID de local funcional/ID de local funcional (se houver mais de um local funcional) \> ID do Ativo/ID do Ativo (se houver mais de um ativo) - número de item.

Se tiver selecionado um ativo na exibição de árvore, você poderá selecionar **Solicitações ativos** ou **Ordens de serviço ativas** para exibir as solicitações de manutenção ou ordens de serviço relacionadas ao ativo. Você também pode selecionar **Abrir** \> **Localização funcional**, **Ativo** ou **BOM de ativos** para abrir a exibição relacionada.

A opção **Locais funcionais de ativo** que você pode selecionar no campo **Exibir** também está disponível em uma pesquisa de ativos onde você pode selecionar um ativo. O modo de exibição de árvore é mostrado em uma guia **Exibição de ativos**, por exemplo, onde você [cria um ativo](../objects/create-an-object.md), cria uma solicitação de manutenção ou cria uma ordem de serviço.