---
title: Materiais perigosos
description: Este tópico fornece informações sobre documentos e informações de materiais perigosos armazenados no seu ambiente.
author: lachlancashMS
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: bda81f72d5dea24c7ba678b9a86258a02f7b8cd5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829417"
---
# <a name="hazardous-materials"></a>Materiais perigosos

[!include [banner](../includes/banner.md)]

As informações sobre materiais perigosos são configuradas no Gerenciamento de informações sobre produtos. Este módulo também fornece documentos que podem ser impressos por meio do gerenciamento de depósito.

Quando você envia materiais que são classificados como mercadorias perigosas, a papelada adicional deve ser incluída nas remessas. A funcionalidade de materiais perigosos permite que os clientes armazenem informações de classificação e as relacionem para liberar itens. Essas informações podem ser usadas para ajudar a preparar a documentação de remessa.

> [!IMPORTANT]
> Os recursos de materiais perigosos no Microsoft Dynamics 365 Supply Chain Management fornecem uma coleção de campos úteis de informações de produtos e funcionalidades relacionadas que podem ajudar você a registrar e consultar informações relacionadas aos produtos perigosos. Esses recursos também podem ajudá-lo a criar e imprimir documentos de remessa que incluam algumas das mesmas informações sobre materiais perigosos que você está enviando. No entanto, o sistema não o tornará automaticamente compatível com todos os regulamentos aplicáveis em seu país ou região. Embora essas ferramentas tenham a finalidade de ajudá-lo a cumprir as regulamentações comuns, elas não são suficientes, nem garantidas. Sua organização é responsável por conhecer todas as regulamentações aplicáveis e por executar todas as etapas necessárias para cumpri-las.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]