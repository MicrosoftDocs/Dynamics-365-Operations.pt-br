---
title: NT 2020.006 – plataforma digital de vendas intermediárias para NF-e
description: Este tópico explica como marcar vendas digitais intermediárias para NF-e.
author: gionoder
ms.date: 07/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: 8
ms.openlocfilehash: 5602ad3450bf17639922b664d16e27602f3b35411612ded14e37ab7aadaba8f4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715003"
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

1. Acesse **Administração da organização** \> **Organizações** \> **Documentos eletrônicos** \> **Parâmetros federais de NF-e**.
2. Na guia **Códigos de rejeição**, selecione **Novo** para inserir os novos códigos de rejeição. Para a lista de novos códigos de rejeição, consulte a documentação da nota técnica NT2020.006 disponível no [Portal da NF-e](http://www.nfe.fazenda.gov.br/portal/principal.aspx).

## <a name="scope-from-version-100-of-the-technical-note"></a>Escopo da versão 1.00 da Nota técnica

### <a name="new-tag-ltindintermedgt"></a>Nova marca &lt;indintermed&gt;

Quando uma plataforma digital que é de propriedade do contribuinte serve como o intermediário para uma venda, se o tipo de presença for definido como um dos valores a seguir no cabeçalho da ordem de venda criada para a venda, a marca **&lt;indintermed&gt;** será adicionada ao XML da NF-e. O valor é definido como **0** (zero).

- Internet
- Teleatendimento
- Diversos

Se o tipo de presença for diferente dos listados, a marca **&lt;indintermed&gt;** não será colocada no XML.

## <a name="scope-from-version-110-of-the-technical-note"></a>Escopo da versão 1.10 da Nota técnica

- Atualização na regra de validação B25c-10: adicionada a opção "Em pessoa" para gerar a marca **&lt;indintermed&gt;**

## <a name="scope-from-version-120-of-the-technical-note"></a>Escopo da versão 1.20 da Nota técnica

- YA02: Adicionando opções à marca **&lt;tPag&gt;**
- 2.2.1, B25c-10: reversão da opção "Em pessoa" para gerar a marca **&lt;indintermed&gt;**
- YB01-10: Atualização das regras quando o nó **&lt;infIntermed&gt;** tiver que existir
- YB01-20: Atualização das regras quando o nó **&lt;infIntermed&gt;** não tiver que existir
- YA02a, YA02a-10, YA02a-20: nova marca **&lt;xPag&gt;** adicionada quando **&lt;tPag&gt;** = 99


## <a name="out-of-scope-for-the-feature"></a>Fora do escopo do recurso

- Esse recurso não oferece suporte à NF-e emitida de faturas de texto livre que são geradas de vendas em que o cliente não está fisicamente presente e uma plataforma digital de vendas serve como intermediário.
- Este recurso não oferece suporte à NF-e emitida de devoluções, ordens de transferência ou cenários de crédito complementares e tributários.
