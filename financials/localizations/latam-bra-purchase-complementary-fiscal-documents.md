---
title: Notas fiscais de compra complementares do Brasil
description: "Este tópico descreve o conceito de uma fatura complementar de compras da localização brasileira."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BrazilParameters, FBFiscalDocument_BR, PurchComplementaryInvoice, PurchComplementaryInvoiceCancel_BR, PurchComplementaryInvoiceListPage
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269154
ms.assetid: efff5c06-3ad6-45df-97d9-d714614c4e95
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 5f1c4ff1a8881966295319123b6a7e14a5adac17
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-complementary-fiscal-documents-for-brazil"></a>Notas fiscais de compra complementares do Brasil

[!include[banner](../includes/banner.md)]


Este tópico descreve o conceito de uma fatura complementar de compras da localização brasileira.

<a name="overview"></a>Visão Geral
--------

De acordo com as normas fiscais do Brasil, uma nota fiscal específica que é conhecida como nota fiscal complementar é recebida ou emitida para fins de correção. Por exemplo, se os preços de mercadorias ou serviços da nota fiscal original foram registrados incorretamente, uma nota fiscal complementar é necessária para corrigir o erro. Notas fiscais complementares aplicam-se somente se a diferença for positiva. Em outras palavras, aplicam-se somente se os preços ou valores de impostos atuais forem maiores que os preços ou valores dos impostos originais. Porque as notas fiscais deste tipo são consideradas complementos das notas fiscais originais, as notas fiscais originais não devem ser canceladas. As empresas são obrigadas emitir ou receber as faturas complementares para os seguintes motivos:

-   Erro no preços de mercadorias ou serviços
-   Erro na quantidade de mercadorias ou serviços
-   Erro em porcentagem de imposto
-   Erro no cálculo do imposto

## <a name="purchase-complementary-fiscal-document"></a>Nota fiscal complementar de compra
Você pode criar uma nota fiscal complementar de compra para ajustar uma nota fiscal de compra que foi gerada por um preço incorreto, um valor de IPI (Imposto sobre Produtos Industrializados) incorreto ou um valor de ICMS (Imposto sobre Circulação de Mercadorias e Serviços) incorreto. Uma nota fiscal complementar de compra é emitida para ajustar somente uma diferença positiva. Por exemplo, uma nota fiscal complementar de compra é gerada se o preço de um item na nota fiscal de compra original estiver incorreto, e se o preço correto para o item for maior do que o preço registrado na nota fiscal de compra original. É possível criar uma nota fiscal complementar de compra para ajustar um erro no preço ou quantidade de itens ou serviços, a porcentagem de imposto, ou o cálculo de imposto. A nota fiscal complementar de compra é uma nota fiscal de compra que complementa a nota fiscal de compra original. Todas as informações, exceto informações sobre encargos, são atualizadas a partir da nota fiscal de compra original. Não é possível adicionar ou excluir as linhas de uma nota fiscal complementar de compra. Os seguintes tipos de notas fiscais complementares de compra estão disponíveis:

-   **Preço** – Este tipo de nota fiscal complementar é criado para ajustar um preço incorreto para uma nota fiscal. O preço atual deve ser maior que o preço registrado na nota fiscal original. A diferença de preço será cobrada do fornecedor.
-   **IPI** – Este tipo de nota fiscal complementar é criado para ajustar um preço incorreto para um valor de IPI de uma nota fiscal. A diferença de imposto IPI será cobrada do fornecedor.
-   **ICMS** – Este tipo de nota fiscal complementar é criado para ajustar um preço incorreto para um valor de ICMS de uma nota fiscal. A diferença de ICMS é recebida pela entidade legal e paga às autoridades fiscais.

Você pode criar uma nota fiscal complementar de ICMS somente se os grupos de impostos selecionados para a nota fiscal complementar de compra incluir os códigos do ICMS. Da mesma forma, você pode criar uma nota fiscal complementar de IPI somente se os grupos de impostos selecionados para a nota fiscal complementar de compra incluir os códigos do IPI. Por exemplo, se você criar uma nota fiscal complementar de IPI, mas os grupos de impostos existentes não tiverem o tipo de imposto IPI, selecione um grupo de impostos que tenha um código de IPI. Você pode cancelar e consultar uma nota fiscal complementar de compra que foi lançada na página **Todas as notas fiscais complementares de venda**.

## <a name="prerequisites"></a>Pré-requisitos
Antes de criar ou lançar notas fiscais complementares de compra, os seguintes parâmetros devem ser configurados na página **Parâmetros brasileiros**:

-   **Nota fiscal complementar** – – Especifica o texto fonte padrão de nota fiscal.
-   **Código de impostos para COFINS** – especifique o código de impostos usado para valor de cálculo do COFINS.
-   **Código de impostos para PIS** – Especifique o código de impostos usado para valor de cálculo do PIS.

## <a name="examples"></a>Exemplos
[![Exemplos que mostram uma nota fiscal original junto com notas fiscais complementares de compras de cada um dos três tipos](./media/purchcomplementary-1024x349.png)](./media/purchcomplementary.png)



