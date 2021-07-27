---
title: Imposto retido na fonte global
description: Este tópico fornece informações sobre a funcionalidade de imposto retido na fonte global e sobre como configurá-la. A funcionalidade de imposto retido na fonte global é aprimorada para transações de fornecedor e de cliente, de forma que o imposto retido na fonte seja calculado no nível do item.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 99e9571aed1679717eb776beb54ff3151a22cc14
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6338462"
---
# <a name="global-withholding-tax"></a>Imposto retido na fonte global

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre a funcionalidade de imposto retido na fonte global e explica como configurá-la. A nova funcionalidade está disponível na versão 10.0.17 e posteriores.

A funcionalidade de imposto retido na fonte global é aprimorada para transações de fornecedor e de cliente, de forma que o imposto retido na fonte seja calculado no nível do item. O saldo na conta de imposto retido na fonte das transações de compra pode ser liquidado com a execução do trabalho de pagamento de imposto retido na fonte na conta de liquidação de imposto retido na fonte.

> [!NOTE]
> O imposto retido na fonte global não dá suporte à função **Manter encargos** nas páginas ordem de compra, fatura de fornecedor e ordem de venda.

## <a name="turn-on-global-withholding-tax"></a>Ativar imposto retido na fonte global

1. No espaço de trabalho **Gerenciamento de recursos**, selecione **Imposto retido na fonte global** e selecione **Habilitar agora**.
2. Acesse **Imposto \> Configuração \> Parâmetros \> Parâmetros de contabilidade**. Depois, na guia **Imposto retido na fonte**, defina a opção **Habilitar imposto retido na fonte global** como **Sim**.
3. Selecione **Salvar**.
4. Atualize a página no navegador da Web.

> [!NOTE]
> A funcionalidade de imposto retido na fonte global não pode ser ativada para países/regiões em que já existem soluções localizadas de imposto retido na fonte. Essas áreas incluem, mas não estão restritas à Índia, Brasil, Tailândia, Arábia Saudita, Irlanda, Grã-Bretanha e Estados Unidos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]