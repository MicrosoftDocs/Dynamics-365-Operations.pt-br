---
title: Configurações de fornecedor adicionadas para o Custo de entrega
description: Este tópico descreve os novos campos que são adicionados à página Fornecedores existente ao habilitar o módulo Custo de entrega. Use esses campos para configurar os fornecedores que serão usados juntamente com recursos de Custo de entrega.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: b4e02397f7a4cdeaa21b451268b16e4fbe773612
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690516"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Configurações de fornecedor adicionadas para o Custo de entrega

[!include [banner](../../includes/banner.md)]

Ao habilitar o módulo **Custo de entrega**, vários novos campos são adicionados à pagina **Fornecedores** existente. Use esses campos para configurar os fornecedores que serão usados juntamente com recursos de Custo de entrega.

Para definir os campos relevantes, Acesse **Compras e fornecimento \> Fornecedores \> Todos os fornecedores**. Abra um fornecedor existente ou crie um novo fornecedor e, em seguida, selecione a FastTab **Detalhes diversos**. Todos os novos campos que o módulo **Custo de entrega** adiciona aparecem no cabeçalho **Viagens**. A tabela a seguir descreve esses campos.

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
