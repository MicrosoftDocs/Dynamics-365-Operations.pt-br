---
title: Notas fiscais complementares de compra para O Brasil
description: "Este tópico descreve o conceito de uma nota complementar de compra da localização brasileira."
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

# <a name="purchase-complementary-fiscal-documents-for-brazil"></a>Notas fiscais complementares de compra para O Brasil

Este tópico descreve o conceito de uma nota complementar de compra da localização brasileira.

<a name="overview"></a>Visão Geral
--------

De acordo com as normas fiscais em O Brasil, uma nota fiscal específica que é conhecido como uma fatura complementar (complementar de Nota fiscal) é recebida ou emitida para fins de correção. Por exemplo, se os preços de mercadorias ou serviços da nota fiscal original foram registrados incorretamente, nota de complemento é necessário para corrigir o erro. Notas fiscais complementares são aplicáveis somente se a diferença for positiva. Ou seja são aplicados apenas se os preços atuais ou valores de impostos estão mais de preços afeta originais ou valores. Porque as notas fiscais deste tipo são consideradas complementos fiscais de vendas originais, as notas fiscais não precisam ser canceladas. As empresas são obrigadas emitir ou receber notas fiscais complementares pelos seguintes motivos:

-   Erro no preço de mercadorias ou serviços
-   Erro na quantidade de bens ou serviços
-   Erro em porcentagem
-   Erro no cálculo de impostos

## <a name="purchase-complementary-fiscal-document"></a>Nota fiscal complementar de compra
Você pode criar uma nota fiscal de compra de complemento para ajustar uma nota fiscal de compra que é gerado por um preço incorreto, um valor incorreto de Produtos Industrializados de sobre Impostos (IPI,) ou um valor incorreto de Circulação de Mercadorias e o de Imposto ICMS (). Uma nota fiscal complementar de compra é emitida para ajustar somente uma diferença positiva. Por exemplo, um documento fiscal complementar de compra será gerado se o preço de um item em nota fiscal de compra original está incorreto e, se o preço atual do item é mais do preço que está registrada em nota fiscal de compra original. É possível criar uma nota fiscal complementar de compra para ajustar um erro no preço ou quantidade de itens ou serviços, a porcentagem de imposto, ou o cálculo de imposto. A nota fiscal complementar de compra é uma nota fiscal de compra que complementa a nota fiscal de compra original. Todas as informações, exceto informações sobre, encargos é atualizada de documento fiscal de compra original. Você não pode adicionar linhas a ou excluir linhas de um documento fiscal complementar de compra. Os seguintes tipos de notas fiscais complementares de compra estão disponíveis:

-   ** O preço ** – esse tipo de documento fiscal de complemento é criado para ajustar o preço incorreto para um documento fiscal. O preço atual deve ser maior do que o preço que está registrada em nota fiscal original. A diferença de preço será cobrada do fornecedor.
-   ** IPI ** – esse tipo de documento fiscal de complemento é criado para ajustar incorreto um valor de IMPOSTO IPI para um documento fiscal. A diferença de imposto IPI será cobrada do fornecedor.
-   ** ICMS ** – esse tipo de documento fiscal de complemento é criado para ajustar o valor incorreto tributário de ICMS para um documento fiscal. A diferença de ICMS é recebida pela entidade legal e paga às autoridades fiscais.

Você pode criar um documento fiscal complementar ICMS somente se os grupos de impostos selecionado para a nota fiscal de compra de complemento incluem IMPOSTO ICMS. Também, crie um documento fiscal complementar IPI somente se os grupos de impostos selecionado para a nota fiscal de compra de complemento incluem IPI. Por exemplo, se você criar um documento fiscal complementar IPI, mas os grupos de impostos existentes não tenha o tipo de imposto IPI, selecione um grupo que tenha um imposto IPI. Você pode cancelar e consultar um documento fiscal complementar de compra que será lançado todos ** notas fiscais complementares de compra ** na página.

## <a name="prerequisites"></a>Pré-requisitos
Para criar e lançar a nota fiscal complementar de compra, os seguintes parâmetros devem ser configurados ** parâmetros brasileiros ** página em:

-   ** Documento fiscal complementar ** – especificar texto fonte padrão de documento fiscal.
-   ** Código de impostos para COFINS ** – especifique o código de impostos usado para valor de cálculo de impostos COFINS.
-   ** Código de impostos para PIS ** – especifique o código de impostos usado para valor de cálculo de OS impostos PIS.

## <a name="examples"></a>Exemplos
[exemplo![que mostra uma nota fiscal original com notas fiscais complementares de compra por um dos três tipos (]. /media/purchcomplementary-1024x349.png)](. /media/purchcomplementary.png)


