---
title: Materiais perigosos
description: Este tópico fornece informações sobre documentos e informações de materiais perigosos armazenados no seu ambiente.
author: lachlancashMS
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 443d2eb545b2b7592e27ae037009720db0a71997
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092536"
---
# <a name="hazardous-materials"></a>Materiais perigosos

[!include [banner](../includes/banner.md)]

As informações sobre materiais perigosos são configuradas no Gerenciamento de informações sobre produtos. Este módulo também fornece documentos que podem ser impressos por meio do gerenciamento de depósito.

Quando você envia materiais que são classificados como mercadorias perigosas, a papelada adicional deve ser incluída nas remessas. A funcionalidade de materiais perigosos permite que os clientes armazenem informações de classificação e as relacionem para liberar itens. Essas informações podem ser usadas para ajudar a preparar a documentação de remessa.

> [!IMPORTANT]
> Para ajudar a gerenciar remessas de mercadorias perigosas, o Microsoft Dynamics 365 Supply Chain Management permite configurar informações de referência adicionais relacionadas aos produtos. Você também pode configurar documentos de remessa adicionais. No entanto, o sistema não é compatível automaticamente com as regulamentações de seu país ou região. Em vez disso, é uma ferramenta que pode ajudar eu programa geral.

Para poder usar essa funcionalidade, é necessária a seguinte configuração:

- **Gerenciamento de informações sobre produtos**: configure códigos que possam ser aplicados a produtos liberados.
- **Gerenciamento de depósito**: use documentos de remessa adicionais para imprimir informações de remessa.

## <a name="product-information-management"></a>Gerenciamento de informações sobre produtos

No Gerenciamento de informações sobre produtos, há uma gama de tabelas de configuração em que você pode adicionar as informações de referência fornecidas nas listas de mercadorias perigosas para frete rodoviário, aéreo e marítimo.

Veja a seguir algumas das normas que costumam ser mencionadas:

- **ADR** – regulamentações relacionadas ao transporte internacional de mercadorias perigosas por rodovias
- **CFR 49** – regulamentações nos Estados Unidos para o transporte de mercadorias perigosas
- **IMDG** – o código International Marine Dangerous Goods (Código Marítimo Internacional de Mercadorias Perigosas)
- **IATA** – os regulamentos de mercadorias perigosas da International Air Transport Association (Associação Internacional de Transportes Aéreos)

Cada uma dessas regulamentações tem uma lista de mercadorias perigosas que inclui códigos de referência. As listas para cada tipo de transporte são combinadas em classificações internacionais compartilhadas. O Supply Chain Management fornece uma tabela de referência para os códigos compartilhados nessas listas. Cada lista também tem alguns códigos exclusivos que podem ser definidos.

Para começar a configurar essas informações, crie uma regulamentação que possa ser usada para configurar os parâmetros iniciais.

## <a name="warehouse-management"></a>Gerenciamento de depósito

Quando uma remessa é preparada, vários relatórios novos podem ser impressos. Esses relatórios usam as informações configuradas no Gerenciamento de informações sobre produtos.
