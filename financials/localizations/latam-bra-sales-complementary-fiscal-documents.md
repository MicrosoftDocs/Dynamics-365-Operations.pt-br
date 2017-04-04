---
title: Notas fiscais complementares de vendas para O Brasil
description: "Este tópico descreve a fatura complementar de vendas da localização brasileira."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: b03583cab0412721bc8eb5d6bf4ab7680d173319
ms.lasthandoff: 03/31/2017


---

# <a name="sales-complementary-fiscal-documents-for-brazil"></a>Notas fiscais complementares de vendas para O Brasil

Este tópico descreve a fatura complementar de vendas da localização brasileira.

<a name="overview"></a>Visão Geral
--------

De acordo com as normas fiscais em O Brasil, uma nota fiscal específica que é conhecido como uma fatura complementar (complementar de Nota fiscal) é recebida ou emitida para fins de correção. Por exemplo, se os preços de mercadorias ou serviços da nota fiscal original foram registrados incorretamente, nota de complemento é necessário para corrigir o erro. Notas fiscais complementares aplicam-se somente se a diferença for positiva. Ou seja aplicam-se somente se os preços atuais ou valores de impostos estão mais de preço originais ou taxam-se valores. Porque as notas fiscais deste tipo são consideradas complementos fiscais de vendas originais, as notas fiscais não precisam ser canceladas. As empresas são obrigadas emitir ou receber a fatura complementar para os seguintes motivos:

-   Erro no preço de mercadorias ou serviços
-   Erro na quantidade de bens ou serviços
-   Erro em porcentagem

## <a name="sales-complementary-fiscal-document"></a>Nota fiscal complementar de venda
Você deve criar um documento fiscal complementar de venda para ajustar uma nota fiscal de vendas gerado para um preço incorreto, um valor incorreto de Produtos Industrializados de sobre Impostos (IPI,) ou um valor incorreto de Circulação de Mercadorias e o de Imposto ICMS (). Um documento fiscal complementar de venda é emitido somente para ajustar uma diferença positiva. Por exemplo, um documento fiscal complementar de venda será gerado se o preço de um item em nota fiscal do cliente original está incorreto e, se o preço atual do item é mais do preço que está registrada em nota fiscal do cliente original. É possível criar uma nota fiscal complementar de vendas para ajustar um erro no preço ou quantidade de itens ou serviços, porcentagem de imposto, ou o cálculo de imposto. A nota fiscal complementar de vendas é uma nota fiscal de vendas que complementa a nota fiscal de vendas original. Todas as informações, exceto informações sobre, encargos é atualizada de documento fiscal de venda originais. Você não pode adicionar linhas a ou excluir linhas de um documento fiscal complementar de vendas. Os seguintes tipos de notas fiscais complementares de venda estão disponíveis:

-   ** O preço ** – esse tipo de documento fiscal de complemento é criado para ajustar o preço incorreto para um documento fiscal. O preço atual deve ser maior do que o preço que está registrada em nota fiscal original. A diferença de preço é cobrada do cliente.
-   ** IPI ** – esse tipo de documento fiscal de complemento é criado para ajustar incorreto um valor de IMPOSTO IPI para um documento fiscal. A diferença de imposto IPI é cobrada do cliente.
-   ** ICMS ** – esse tipo de documento fiscal de complemento é criado para ajustar o valor incorreto tributário de ICMS para um documento fiscal. A diferença de ICMS é recebida pela entidade legal e paga às autoridades fiscais.

Você pode criar um documento fiscal complementar ICMS somente se os grupos de impostos selecionado para o documento fiscal complementar de vendas incluindo IMPOSTO ICMS. Também, crie um documento fiscal complementar IPI somente se os grupos de impostos selecionado para o documento fiscal complementar de vendas incluindo IMPOSTO IPI. Por exemplo, se você criar um documento fiscal complementar IPI, mas os grupos de impostos existentes não tenha o tipo de imposto IPI, selecione um grupo que tenha um imposto IPI. Você pode cancelar e consultar um documento fiscal complementar de vendas que é lançado ** todas as notas fiscais complementares ** de venda na página.

## <a name="prerequisites"></a>Pré-requisitos
Antes de criar ou lançar notas fiscais complementares vendas, os seguintes parâmetros devem ser configurados ** parâmetros brasileiros ** página em:

-   ** Documento fiscal complementar ** – especificar texto fonte padrão de documento fiscal.
-   ** Código de impostos para COFINS ** – especifique o código de impostos usado para valor social de cálculo de impostos de Contribuição para o Financiamento a Dinamarca (Seguraridade COFINS).
-   ** Código de impostos para PIS ** – especifique o código de impostos usado para valor de cálculo de impostos do Programa de Integração Social (PIS).

## <a name="examples"></a>Exemplos
[exemplos do![de uma nota fiscal original e de um notas fiscais complementares de venda de cada um dos três tipos (]. /media/salescomplementary-1024x409.png)](. /media/salescomplementary.png)


