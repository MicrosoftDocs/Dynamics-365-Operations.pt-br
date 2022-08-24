---
title: NT 2020.005 — atualizações de layout e validação na nota fiscal eletrônica (NF-e)
description: Este artigo fornece informações sobre as atualizações no layout XML e regras de validação na nota técnica NT2020.005.
author: gionoder
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: gionoder
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: 8
ms.openlocfilehash: 8abfbc7d31a1fb5930bbe2e5b232baa28e147807
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288568"
---
# <a name="nt2020005--layout-and-validation-updates-in-the-electronic-fiscal-document-nf-e"></a>NT2020.005 – atualizações de layout e validação na nota fiscal eletrônica (NF-e)

[!include [banner](../includes/banner.md)]

Este artigo descreve as atualizações no layout XML e regras de validação que foram introduzidas pela nota técnica NT2020.005 para a geração da nota fiscal eletrônica modelo 55 (NF-e).

## <a name="enable-the-technical-note-in-dynamics-365-finance-and-dynamics-365-supply-chain-management"></a>Habilitar a nota técnica no Dynamics 365 Finance e Dynamics 365 Supply Chain Management

1. Entre na sua instância do Microsoft Dynamics 365 Finance ou do Dynamics 365 Supply Chain Management.
2. Acesse **Administração da organização** \> **Organizações** \> **Estabelecimentos fiscais** \> **Estabelecimentos fiscais**.
3. Selecione o estabelecimento fiscal e, depois, selecione **Editar**.
4. Na guia **NF-e e NFC-e federal**, na seção **Notas técnicas da NF-e**, selecione **Habilitar nota técnica de NF-e**.
5. No campo **Notas técnicas da NF-e**, selecione **Nota técnica 2020.005 v1.10** para a versão 1.10 da nota técnica.

## <a name="scope-from-version-100110-of-the-technical-note"></a>Escopo da versão 1.00/1.10 da nota técnica

As seguintes atualizações e adições estão agora disponíveis no escopo da nova nota técnica:

- Novas opções foram adicionadas à marca **&lt;tpViaTransp&gt;**.
- A estrutura do nó &lt;adi&gt; foi atualizada.
- Novas marcas foram adicionadas aos nós &lt;ICMS10&gt;, &lt;ICMS70&gt; e &lt;ICMS90&gt;:

    - &lt;vICMSSTDeson&gt;
    - &lt;motDesICMSST&gt;

- Novas marcas foram adicionadas ao nó &lt;ICMS51&gt;:

    - &lt;pFCPDif&gt;
    - &lt;vFCPDif&gt;
    - &lt;vFCPEfet&gt;

- As regras de validação NA15-20 e NA17-10 durante o lançamento de notas fiscais foram atualizadas.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
