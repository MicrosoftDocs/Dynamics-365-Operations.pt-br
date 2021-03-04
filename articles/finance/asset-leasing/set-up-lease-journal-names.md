---
title: Configurar nomes de diário de arrendamento
description: Este tópico explica como definir nomes de diário de arrendamento. Os nomes de diários de arrendamento especificam os diários em que as entradas originadas em Arrendamento de ativo são lançadas.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e8b1b908dfd6d1d6072b6efa83f13ae5784c85c1
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440541"
---
# <a name="set-up-lease-journal-names"></a>Configurar nomes de diário de arrendamento

[!include [banner](../includes/banner.md)]

Os nomes de diários de arrendamento especificam os diários em que transações de Arrendamento de ativo são lançadas. Somente os nomes de diário atribuídos ao tipo de diário **Arrendamento de ativo** aparecem nos campos **Reconhecimento Inicial** e **Nome de Diário Mensal** na página **Parâmetros de arrendamento de ativos**. Somente o tipo de diário de **registro de fatura de fornecedor** pode ser atribuído ao campo **Nome do diário de fatura**.

Para configurar nomes de diário de arrendamento, siga estas etapas.

1. Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de gerenciamento de ativos**.
2. Na guia **Geral**, no campo **Nome do diário de reconhecimento inicial**,selecione um diário. Todas as entradas do diário de reconhecimento inicial serão lançadas nesse nome de diário.
3. No campo **Nome de diário de fatura**, selecione um diário. Se a opção **Pagar ao fornecedor** for definida como **Sim** para o registro de arrendamento, as faturas de pagamento de arrendamento e despesa serão lançadas nesse nome de diário.
4. No campo **Nome de diário de arrendamento**, selecione um diário. Todas as entradas de depreciação, juros e reclassificação de curto prazo serão lançadas nesse nome de diário. Se a opção **Pagar ao fornecedor** for definida como **Não** para o registro de arrendamento, as entradas de pagamento do arrendamento e de pagamento da despesa também serão lançadas nesse nome de diário.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]