---
title: Notas fiscais complementares de vendas para o Brasil
description: "Este tópico descreve a fatura complementar de vendas da localização brasileira."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BrazilParameters, FBFiscalDocument_BR, SalesComplementaryInvoice, SalesComplementaryInvoiceCancel_BR, SalesComplementaryInvoiceListPage
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269194
ms.assetid: 0c52b508-1044-48c1-9dfc-a590bbda5696
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 3c6c3ab6c04841d229d54607487bb759107cd1d3
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="sales-complementary-fiscal-documents-for-brazil"></a>Notas fiscais complementares de vendas para o Brasil

[!include[banner](../includes/banner.md)]


Este tópico descreve a fatura complementar de vendas da localização brasileira.

<a name="overview"></a>Visão Geral
--------

De acordo com as normas fiscais do Brasil, uma nota fiscal específica que é conhecida como nota fiscal complementar é recebida ou emitida para fins de correção. Por exemplo, se os preços de mercadorias ou serviços da nota fiscal original foram registrados incorretamente, uma nota fiscal complementar é necessária para corrigir o erro. Faturas complementares aplicam-se somente se a diferença for positiva. Ou seja aplicam-se somente se os preços ou valores de impostos atuais forem maiores que os preços ou valores dos impostos originais. Porque as notas fiscais deste tipo são consideradas complementos das notas fiscais originais, as notas fiscais originais não devem ser canceladas. As empresas são obrigadas emitir ou receber a fatura complementar para os seguintes motivos:

-   Erro no preços de mercadorias ou serviços
-   Erro na quantidade de bens ou serviços
-   Erro em porcentagem de imposto

## <a name="sales-complementary-fiscal-document"></a>Nota fiscal complementar de venda
Você deve criar uma nota fiscal complementar de venda para ajustar uma nota fiscal de venda que foi gerada por um preço ou valor incorreto de IPI (imposto sobre produtos industrializados), ou de ICMS (Imposto sobre Circulação de Mercadorias e Serviços). Uma nota fiscal complementar de venda é emitida para ajustar somente uma diferença positiva. Por exemplo, uma nota fiscal complementar de venda é gerada se o preço de um item na nota fiscal original do cliente estiver incorreto, e se o preço correto do item for maior do que o preço registrado na nota fiscal original do cliente. É possível criar uma nota fiscal complementar de vendas para ajustar um erro no preço ou quantidade de itens ou serviços, porcentagem de imposto, ou o cálculo de imposto. A nota fiscal complementar de vendas é uma nota fiscal de vendas que complementa a nota fiscal de vendas original. Todas as informações, exceto informações para os encargos, são atualizadas a partir da nota fiscal de vendas original. Não é possível adicionar ou excluir as linhas de uma nota fiscal complementar de venda. Os seguintes tipos de notas fiscais complementares de venda estão disponíveis:

-   **Preço** – Este tipo de nota fiscal complementar é criado para ajustar um preço incorreto para uma nota fiscal. O preço atual deve ser maior que o preço registrado na nota fiscal original. A diferença de preço é cobrada do cliente.
-   **IPI** – Este tipo de nota fiscal complementar é criado para ajustar um preço incorreto para um valor de IPI de uma nota fiscal. A diferença de imposto IPI é cobrada do cliente.
-   **ICMS** – Este tipo de nota fiscal complementar é criado para ajustar um preço incorreto para um valor de ICMS de uma nota fiscal. A diferença de ICMS é recebida pela entidade legal e paga às autoridades fiscais.

Você pode criar uma nota fiscal complementar de ICMS somente se os grupos de impostos selecionados para a nota fiscal complementar de venda incluir os códigos do ICMS. Da mesma forma, você pode criar uma nota fiscal complementar de IPI somente se os grupos de impostos selecionados para a nota fiscal complementar de venda incluir os códigos do IPI. Por exemplo, se você criar uma nota fiscal complementar de IPI, mas os grupos de impostos existentes não tiverem o tipo de imposto IPI, selecione um grupo de impostos que tenha um código de IPI. Você pode cancelar e consultar uma nota fiscal complementar de venda que foi lançada na página **Todas as notas fiscais complementares de venda**.

## <a name="prerequisites"></a>Pré-requisitos
Antes de criar ou lançar notas fiscais complementares de venda, os seguintes parâmetros devem ser configurados na página **Parâmetros brasileiros**.

-   **Nota fiscal complementar** – – Especifica o texto fonte padrão de nota fiscal.
-   **Código de impostos para COFINS** – Especifique o código de impostos usado para valor de cálculo do imposto COFINS (Contribuição para o Financiamento da Seguraridade Social).
-   **Código de impostos para PIS** – especifique o código de impostos usado para valor de cálculo do PIS (Programa de Integração Social).

## <a name="examples"></a>Exemplos
[![Exemplos de uma fatura original e de notas fiscais complementares de vendas de cada um dos três tipos](./media/salescomplementary-1024x409.png)](./media/salescomplementary.png)




