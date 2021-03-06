---
title: Configurar códigos de relatórios de imposto retido na fonte para o tipo de imposto de TDS
description: Os códigos de relatório de imposto retido na fonte são usados para gerar instruções do Formulário 26Q e do Formulário 27Q para Imposto Deduzido na Origem (TDS). Este tópico explica como configurar as etapas de códigos de relatório de imposto retido na fonte para que você possa configurar códigos de relatório de TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1f9325d182f89b98e8b943ae047c55e7e1aeb02f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023038"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a>Configurar códigos de relatórios de imposto retido na fonte para o tipo de imposto de TDS

[!include [banner](../includes/banner.md)]

Os códigos de relatório de imposto retido na fonte são usados para gerar instruções do Formulário 26Q e do Formulário 27Q para Imposto Deduzido na Origem (TDS). Este tópico explica como configurar as etapas de códigos de relatório de imposto retido na fonte para que você possa configurar códigos de relatório de TDS.

1. Vá para **Imposto \> Configuração \> Imposto retido na fonte \> Códigos de relatório de imposto retido na fonte**.

    [![Página códigos de relatório de imposto retido na fonte](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)

2. No campo **Tipo de imposto**, selecione **TDS** para definir códigos de relatórios de imposto retido na fonte para o tipo de imposto de TDS.
3. No campo **Componente de imposto retido na fonte**, selecione o componente de TDS para o qual você está definindo o código de relatório de imposto retido na fonte. O campo **Grupo de componentes do imposto retido na fonte** mostra o grupo de componentes de TDS definido para o componente de TDS que você está definindo.

    O campo **Código de seção** na FastTab **Geral** mostra o código de seção anexado ao grupo de componentes de TDS.

4. Na FastTab **Geral**, no campo **Código do relatório**, selecione o códigos de relatório de TDS:

    - TDS
    - TCS
    - Sobretaxa
    - PE\_Cess
    - SHE\_Cess

5. Feche a página.
