---
title: Configurações de fornecedor adicionadas para o Custo de entrega
description: Este tópico descreve os novos campos que são adicionados à página Fornecedores existente ao habilitar o módulo Custo de entrega. Use esses campos para configurar os fornecedores que serão usados juntamente com recursos de Custo de entrega.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 3a288517f77d1618f94f8539506d01a108e63fa5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829753"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Configurações de fornecedor adicionadas para o Custo de entrega

[!include [banner](../../includes/banner.md)]

Ao habilitar o módulo **Custo de entrega**, vários novos campos são adicionados à pagina **Fornecedores** existente. Use esses campos para configurar os fornecedores que serão usados juntamente com recursos de Custo de entrega.

Para definir os campos relevantes, vá para **Compras e fornecimento \> Fornecedores \> Todos os fornecedores**. Abra um fornecedor existente ou crie um novo fornecedor e, em seguida, selecione a FastTab **Detalhes diversos**. Todos os novos campos que o módulo **Custo de entrega** adiciona aparecem no cabeçalho **Viagens**. A tabela a seguir descreve esses campos.

| Campo | descrição |
|---|---|
| Tipo de remessa | <p>Selecione a função do fornecedor em relação ao Custo de entrega:</p><ul><li>**Nenhuma** – o fornecedor não tem uma função específica relacionada ao Custo de entrega. Esse valor é a configuração padrão, pois a maioria dos fornecedores provavelmente não terá uma função específica.</li><li>**Empresa de transporte** – o fornecedor é uma empresa de transporte. Os fornecedores que têm esse tipo de remessa estão disponíveis para seleção no campo **Empresa de transporte** na página **Viagens**.</li><li>**Agente alfandegário** – o fornecedor é um agente alfandegário. Os fornecedores que têm esse tipo de remessa estão disponíveis para seleção no campo **Agente alfandegário** na página **Fólios**.</li><li>**Agente** – o fornecedor é um agente. Os fornecedores que têm esse tipo de remessa estão disponíveis para seleção no campo **Agente** nas páginas **Fornecedores** e **Ordens de compra**.</li></ul> |
| Grupo de tipo de custo | Atribua o fornecedor a um grupo de tipos de custo com a finalidade de selecionar [custos automáticos](auto-cost-setup.md). |
| Porta de origem | Selecione o porto de origem para a viagem. |
| Agente | O agente padrão quando as compras são feitas do fornecedor. |
| Importar fornecedor de avaliação de custo | <p>Indique se o fornecedor é um fornecedor de Custo de entrega.</p><p>**Dica:** você pode usar este campo juntamente com a segurança em nível de registro para limitar as ordens de compra que são mostradas quando uma viagem é criada.</p> |
| Empresa transportadora | Selecione a empresa de transporte padrão usada quando as ordens de compra são criadas para o fornecedor. |
| Provedor de serviços | Indique se o fornecedor é provedor de serviços. |
| Grupo de tolerâncias excedentes/insuficientes | Selecione o grupo de tolerâncias excedentes/insuficientes padrão para o fornecedor. |
