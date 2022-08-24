---
title: Notas fiscais de compra complementares do Brasil
description: Este artigo descreve o conceito de uma fatura complementar de compras da localização brasileira.
author: AdamTrukawka
ms.date: 08/08/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 269154
ms.search.form: BrazilParameters, FBFiscalDocument_BR, PurchComplementaryInvoice, PurchComplementaryInvoiceCancel_BR, PurchComplementaryInvoiceListPage
ms.openlocfilehash: 4560619346fd022735ef12c431d02adf48b09e30
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279213"
---
# <a name="purchase-complementary-fiscal-documents-for-brazil"></a>Notas fiscais de compra complementares do Brasil

[!include [banner](../includes/banner.md)]

Este artigo descreve o conceito de uma fatura complementar de compras da localização brasileira.

## <a name="overview"></a>Visão Geral

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
[![Exemplos que mostram uma nota fiscal original junto com notas fiscais complementares de compras de cada um dos três tipos.](./media/purchcomplementary-1024x349.png)](./media/purchcomplementary.png)


Para obter mais informações, consulte os seguintes tópicos:

[Criar e lançar uma nota fiscal complementar de compra (Brasil)](tasks/br-00026-1-create-post-purchase-complementary-fiscal-document.md)

[Cancelar uma nota fiscal complementar de compra (Brasil)](tasks/br-00026-2-cancel-purchase-complementary-fiscal-document.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
