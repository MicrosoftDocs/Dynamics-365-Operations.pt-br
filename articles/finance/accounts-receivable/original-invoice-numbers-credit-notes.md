---
title: Referências a faturas originais em notas de crédito
description: Este artigo explica como configurar e imprimir os números de fatura originais nas notas de crédito relacionadas.
author: mrolecki
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.search.form: ''
ms.openlocfilehash: f1f9ca3914aa02cc38ddfe9f8dd88eb7fc88fd4b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281225"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>Referências a faturas originais em notas de crédito

[!include [banner](../includes/banner.md)]


Em alguns países e regiões, há um requisito legal de que notas de crédito impressas incluem referências às faturas originais. Este artigo explica como configurar e imprimir os números de fatura originais nas notas de crédito relacionadas.

## <a name="prerequisites"></a>Pré-requisitos

- No espaço de trabalho **Gerenciamento de recursos**, ative o recurso **Layout de faturamento de crédito para vendas e relatórios de faturas de projetos**. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Os formatos imprimíveis dos documentos necessários devem ser configurados no gerenciamento de impressão.

A funcionalidade descrita neste artigo aplica-se aos seguintes documentos:

**Contas a receber**

- Nota de crédito em texto livre
- Nota de crédito de clientes

**Gerenciamento e contabilidade do projeto**

- Nota de crédito do projeto

## <a name="configure-accounts-receivable-parameters"></a>Configurar Parâmetros de contas a receber

Siga estas etapas para definir o parâmetro que controla se as referências às faturas originais são impressas em notas de crédito relacionadas.

1. Acesse **Contas a receber** \> **Configuração** \> **Parâmetros de contas a receber**.
2. Na guia **Atualizações**, na Guia Rápida **Fatura**, defina a opção **Aplicar o layout de faturamento de crédito para vendas e relatórios de faturas de projetos** como **Sim**.

![Configurar Parâmetros de contas a receber.](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>Definir referências a faturas originais

Use os procedimentos a seguir para definir referências a faturas originais com base no tipo de documento.

### <a name="free-text-credit-note"></a>Nota de crédito em texto livre

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Crie uma nova nota de crédito ou selecione uma nota de crédito existente.
3. Abra a fatura.
4. No Painel de Ações, na guia **Fatura**, no grupo **Funções**, selecione **Faturamento de crédito**.
5. Insira a referência à fatura original e selecione o motivo da correção.

![Definir a referência para uma fatura de texto livre.](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>Nota de crédito de clientes

1. Acesse **Contas a receber** \> **Ordens** \> **Todas as ordens de vendas**.
2. Selecione e abra a ordem de venda faturada a ser corrigida.
3. No Painel de Ações, na guia **Vender**, no grupo **Nota de crédito**, selecione **Nota de crédito**.
4. Insira o motivo da correção. A referência à fatura original é estabelecida automaticamente.

![Definir a referência para uma ordem de venda.](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>Nota de crédito do projeto

1. Acesse **Gerenciamento e contabilidade de projeto** \> **Faturas de projeto** \> **Faturas de projeto**.
2. Selecione e abra a fatura de projeto a ser corrigida.
3. No Painel de Ações, na guia **Fatura de projeto**, no grupo **Funções**, selecione **Selecionar nota de crédito**.
4. Selecione **Faturamento de crédito**.
5. Insira o motivo da correção. A referência à fatura original é estabelecida automaticamente.

![Definir a referência para uma fatura de projeto.](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>Imprimir notas de crédito

Quando você imprime notas de crédito de texto livre, cliente e projeto, elas incluem a referência à fatura original e a razão da correção.

![Nota de crédito impressa.](media/credit-note-FTI.jpg)

> [!NOTE]
> Verifique se os formatos imprimíveis dos documentos estão configurados corretamente, supondo que as referências a faturas originais serão impressas.

## <a name="references-to-original-invoices-in-debit-notes"></a>Referências a faturas originais em notas de débito

Por padrão, as referências a faturas originais podem ser inseridas para notas de crédito. Por exemplo, você pode inserir referências ao criar correções negativas (decrescentes) de faturas originais.

Para inserir referências ao fazer correções positivas (crescentes) de faturas originais, você deve habilitar o recurso **Referências a faturas originais no recurso de notas de débito** no espaço de trabalho **Gerenciamento de recursos**.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
