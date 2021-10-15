---
title: Fazer referência a faturas originais em notas de crédito (faturas do fornecedor)
description: Este tópico descreve como criar uma referência a uma fatura original ao criar uma nota de crédito.
author: v-oloski
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6114ffb4d3b9e942887cbfa10c6039b0d73af7e1
ms.sourcegitcommit: 86f0574363fb869482ef73ff294f345f81d17c5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7562217"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Fazer referência a faturas originais em notas de crédito (faturas do fornecedor)

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar uma referência a uma fatura original ao criar uma nota de crédito.

## <a name="prerequisites"></a>Pré-requisitos

No espaço de trabalho **Gerenciamento de recursos**, habilite o recurso **Habilitar faturamento de crédito para faturas do fornecedor**. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

A funcionalidade descrita neste tópico aplica-se aos seguintes documentos comerciais.

**Contas a pagar:**

- Ordem de compra
- Diário de faturas
- Registro de fatura

**Contabilidade:**

- Diário geral

## <a name="define-a-reference-to-an-original-invoice"></a>Definir uma referência para uma fatura original

Use os procedimentos a seguir para definir uma referência para uma fatura original nos tipos de documento comercial especificados.

### <a name="vendor-credit-note-purchase-order"></a>Nota de crédito do fornecedor (ordem de compra)

1. Acesse **Contas a pagar** \> **Ordens de compra** \> **Todas as ordens de compra**.
2. Crie uma nova ordem de compra ou use uma existente para criar uma nota de crédito.
3. No Painel de Ações, na guia **Fatura**, no grupo **Introduzir**, selecione **Faturamento de crédito**.
4. Insira o motivo para a correção e a referência à fatura original.

### <a name="vendor-credit-note-ledger-journals"></a>Nota de crédito do fornecedor (diários do razão)

1. Siga uma destas etapas:

    - Acesse **Contas a pagar** \> **Diários de faturas**.
    - Acesse **Contas a pagar** \> **Registro de fatura**.
    - Acesse **Contabilidade** \> **Entradas do diário** \> **Diários gerais**.

2. Criar um diário e linhas do diário.
3. No Painel de Ações, selecione **Funções** \> **Faturamento de crédito**.
4. Insira o motivo para a correção e a referência à fatura original.

> [!NOTE]
> O comando **Faturamento de crédito** ficará visível em um comprovante de diário geral se o campo **Tipo de conta** estiver definido como **Fornecedor**.
