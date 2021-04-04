---
title: NT 2020.006 – plataforma digital de vendas intermediárias para NF-e
description: Este tópico explica como marcar vendas digitais intermediárias para NF-e.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: 8
ms.openlocfilehash: f0fb4a05382ed798142527bd7783f17046ab0036
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585146"
---
# <a name="nt2020006--intermediary-sales-digital-platform-for-nf-e"></a>NT 2020.006 – plataforma digital de vendas intermediárias para NF-e

[!include [banner](../includes/banner.md)]

Uma venda pode ocorrer mesmo quando o cliente não está fisicamente presente. Em vez disso, uma plataforma ou um mercado digital pode servir como um intermediário para a transação. Nessas situações, o XML do modelo de nota fiscal eletrônica 55 (NF-e) que é emitido a partir da venda deve conter uma nova marca para indicar que um intermediário participou da operação.

Esse recurso oferece suporte a cenários em que uma plataforma ou um mercado digital são de propriedade ou licenciados pelo emissor da nota fiscal.

## <a name="enable-the-technical-note-in-dynamics-365-finance-and-dynamics-365-supply-chain-management"></a>Habilite a nota técnica no Dynamics 365 Finance e no Dynamics 365 Supply Chain Management

1. Entre na sua instância do Microsoft Dynamics 365 Finance ou do Dynamics 365 Supply Chain Management.
2. Acesse **Administração da organização** \> **Organizações** \> **Estabelecimentos fiscais** \> **Estabelecimentos fiscais**.
3. Selecione o estabelecimento fiscal e, depois, selecione **Editar**.
4. Na guia **NF-e e NFC-e federal**, no grupo de campos **Notas técnicas da NF-e**, selecione **Habilitar nota técnica de NF-e**.
5. No campo **Notas técnicas da NF-e**, selecione **Nota técnica 2020.006 v1.10** para a versão 1.10 da nota técnica.

## <a name="enable-the-technical-note-in-dynamics-ax-2012-r3"></a>Habilite a nota técnica no Dynamics AX 2012 R3

- Aplique KB 4611321 para habilitar a versão 1.10 da nota técnica no Dynamics AX 2012 R3.
- Aplique KB 4598546 para habilitar a versão 1.00 da nota técnica no Dynamics AX 2012 R3.

## <a name="enter-the-new-nf-e-rejection-codes"></a>Insira os códigos de rejeição novos da NF-e

A nota técnica NT 2020.006 apresentou novos códigos de rejeição de NF-e. Conclua as etapas a seguir para adicionar os códigos.

1. Vá para **Administração da organização** \> **Organizações** \> **Documentos eletrônicos** \> **Parâmetros federais de NF-e**.
2. Na guia **Códigos de rejeição**, selecione **Novo** para inserir os novos códigos de rejeição. Para a lista de novos códigos de rejeição, consulte a documentação da nota técnica NT2020.006 disponível no [Portal da NF-e](http://www.nfe.fazenda.gov.br/portal/principal.aspx).

## <a name="sales-that-are-intermediated-by-the-taxpayers-own-sales-digital-platform"></a>Vendas que são intermediárias pela plataforma digital de vendas própria do contribuinte

Quando uma plataforma digital que é de propriedade do contribuinte serve como o intermediário para uma venda, se o tipo de presença for definido como um dos valores a seguir no cabeçalho da ordem de venda criada para a venda, a marca **&lt;indintermed&gt;** será adicionada ao XML da NF-e. O valor é definido como **0** (zero).

- Presencial
- Internet
- Teleatendimento
- Diversos

Se o tipo de presença for diferente dos listados, a marca **&lt;indintermed&gt;** não será colocada no XML.

## <a name="out-of-scope-for-the-feature"></a>Fora do escopo do recurso

- Esse recurso não oferece suporte à NF-e emitida de faturas de texto livre que são geradas de vendas em que o cliente não está fisicamente presente e uma plataforma digital de vendas serve como intermediário.
- Este recurso não oferece suporte à NF-e emitida de devoluções, ordens de transferência ou cenários de crédito complementares e tributários.
