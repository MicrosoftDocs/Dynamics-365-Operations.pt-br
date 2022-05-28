---
title: Imprimir informações de imposto sobre documentos de ordem de transferência
description: Este tópico explica como as informações de imposto determinadas pelo serviço de cálculo de imposto podem ser impressas em documentos de ordem de transferência.
author: Kai-Cloud
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-10-12
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: e74336270ab46fc19adb4c797745c9582028391a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687461"
---
# <a name="print-tax-information-on-transfer-order-documents"></a>Imprimir informações de imposto sobre documentos de ordem de transferência

[!include [banner](../../includes/banner.md)]

Este tópico explica como imprimir informações sobre impostos em documentos de ordem de transferência. Você pode imprimir o documento de fatura pro forma de uma ordem de transferência para transferências de estoque que são consideradas de fornecimento dentro da Comunidade e de aquisições da Comunidade sob as regulamentações da UE (União Europeia) e do IVA (imposto sobre valor agregado). 

Os seguintes dados relevantes de imposto são adicionados aos documentos da ordem de transferência:

- Os nomes e os endereços de remessa e reenvio para a transferência de estoque
- Os números de identificação de imposto do fornecedor e do destinatário
- O preço unitário e o valor tributável das mercadorias fornecidas
- O código de imposto, a taxa de imposto, o valor do imposto e as diretivas de imposto

Para configurar esses dados, você deverá concluir as etapas principais a seguir.

1. [Habilitar e configurar o recurso de imposto para ordens de transferência](tasks/Tax-feature-support-for-transfer-order.md).
2. [Criar e configurar vários números de registro de imposto para uma entidade legal](emea-multiple-vat-registration-numbers.md).
3. Configure o código de isenção, a descrição, as diretivas de imposto e o código de impressão em códigos de imposto. Neste exemplo, três códigos de imposto são criados e sincronizados no Microsoft Dynamics 365 Finance: **Isento de NL**, **BE-RC-21** e **BE-RC+21**.

    1. No Finance, acesse **Imposto** \> **Configuração** \> **Imposto** \> **Códigos de isenção de imposto**.
    2. Selecione **Editar** e insira uma descrição para o código de isenção **EC**. Por exemplo, insira **Remessas de EC isentas de imposto com número de registro de imposto**.
    3. Acesse **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Códigos de imposto**.
    4. Selecione o código de imposto **BE-RC-21** e, em seguida, selecione **Diretivas de imposto**.
    5. Selecione **Novo**.
    6. No campo **Idioma**, selecione **EN-US**. Em seguida, no campo **Texto**, insira **O documento que estabelece a transferência de mercadorias no sentido do artigo 138. 2. c) da Diretiva de IVA da UE 2006/112/EC**.
    7. Feche a página.
    8. Na Guia Rápida **Geral**, no campo **Imprimir**, selecione **Taxa de imposto**.
    8. Selecione o código de imposto **Isento de NL** e, em seguida, na Guia Rápida **Geral**, no campo **Imprimir**, selecione **Taxa de imposto**.

    > [!NOTE] 
    > O código de imposto, a taxa de imposto e a descrição de isenção de impostos não são impressos em documentos de ordem de transferência se nenhuma diretivas de código de isenção ou de imposto forem mantidas para o código de imposto.

## <a name="print-the-transfer-order---shipment-document"></a>Imprimir a ordem de transferência – documento de remessa

Depois que uma transferência for remetida, siga estas etapas para imprimir o documento de remessa da ordem de transferência.

1. Acesse **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Ordens de transferência** \> **Remessa**.
2. Na guia **Parâmetros**, no grupo **Imprimir**, habilite **Informações sobre impostos**.
3. Na guia **Registros a serem incluídos**, selecione **Filtrar**, selecione o número da ordem de transferência e, em seguida, selecione **OK**.
4. Selecione **OK** para imprimir a ordem de transferência – documento de remessa.

## <a name="print-the-transfer-order---receipt-document"></a>Imprimir a ordem de transferência – documento de recebimento

Depois que uma transferência for recebida, siga estas etapas para imprimir a ordem de transferência - documento de recebimento.

1. Acesse **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Ordens de transferência** \> **Receber**.
2. Na guia **Parâmetros**, no grupo **Imprimir**, habilite **Informações sobre impostos**.
3. Na guia **Registros a serem incluídos**, selecione **Filtrar**, selecione o número da ordem de transferência e, em seguida, selecione **OK**.
4. Selecione **OK** para imprimir a ordem de transferência – documento de recebimento.

## <a name="print-the-transfer-overview-document"></a>Imprimir o documento de visão geral de transferência

Siga estas etapas para imprimir o documento de visão geral de transferência.

> [!NOTE]
> As informações sobre impostos só estarão disponíveis quando a ordem de transferência tiver sido remetida ou recebida.

1. Acesse **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Ordens de transferência** \> **Visão geral da transferência**.
2. Na guia **Parâmetros**, no grupo **Imprimir**, habilite **Informações sobre impostos**.
3. Na guia **Registros a serem incluídos**, selecione **Filtrar**, selecione o número da ordem de transferência e, em seguida, selecione **OK**.
4. Selecione **OK** para imprimir o documento de visão geral de transferência.

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
