---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (24 de setembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 078b513b828b97a5cfaf613970edd581fb091f9e
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551304"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-september-24-2018"></a>Novidades ou alterações no Dynamics 365 Talent - Core HR (24 de setembro de 2018)

[!include [banner](includes/banner.md)]

**Compilação 8.1.1015.0**

Este tópico descreve os recursos novos ou alterados no Core HR.

## <a name="currency-added-to-benefits"></a>Moeda adicionada aos benefícios

Os planos de benefício foram atualizados para incluir a moeda do benefício. Este novo campo também está disponível em benefícios do trabalhador inscrito. Este novo campo faz parte do privilégio de segurança Manter benefícios e Exibir uma lista de benefícios.

## <a name="update-proration-process--leave-and-absence"></a>Atualizar processo de rateio – Licença e ausência

As organizações concedem folgas de maneira diferente com base em quando os funcionários entraram e saíram da empresa. Para funcionários que estão deixando de trabalhar na organização, pode ser necessários alguns deles encerrem a concessão na data de demissão, enquanto outros dependem do último dia de trabalho para interromper o processo de competência. Essas alterações oferecem às organizações a capacidade de escolher quando encerrar a inscrição durante o processo de demissão. As novas opções são parte dos privilégios para Demitir um trabalhador e Demitir um trabalhador do autoatendimento para gerentes. 

## <a name="other-changes"></a>Outras alterações

Esta versão inclui várias correções de bug adicionais.

## <a name="known-issue"></a>Problema conhecido

-   **Problema:** ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. **Solução alternativa:** antes de abrir a página do anexo, verifique se os quadros de fatos na página **Trabalhador** estão fechados. Se os quadros de fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões de anexos serão habilitados. (Esse problema será corrigido na próxima atualização de plataforma.)
