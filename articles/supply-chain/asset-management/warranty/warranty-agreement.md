---
title: Contratos de garantia
description: Este tópico explica contratos de garantia no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f049165fd12dfae672293e0c30ddb186ad3ed12c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422323"
---
# <a name="warranty-agreements"></a>Contratos de garantia

[!include [banner](../../includes/banner.md)]

 


No Gerenciamento de Ativos, você pode definir termo de garantia que podem ser conectadas um ativo ou a um tipo de ativo. Os termos de garantia são criados para um período específico. A garantia pode ser configurada para fornecer cobertura total ou parcial, e você pode configurar os termos que são relacionados a horas, despesas e itens.

A primeira etapa é criar quaisquer contratos de garantia de fornecedor que tiver para o equipamento. Em seguida, anexe os contratos de garantia para ativos ou tipos de ativos. Contratos de garantia de fornecedor são usados somente para fins informativos. A garantia do fornecedor é configurada em um ativo, você pode ver o período de cobertura da garantia no ativo.

## <a name="create-a-warranty-agreement"></a>Criar um contrato de garantia

Um contrato da garantia pode incluir diversas linhas de contrato para cobrir a garantia de horas de trabalho, despesas e itens.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Garantia**.
2. Selecione **Nova** para criar um produto.
3. No campo **Garantia**, insira um ID de garantia. 
4. No campo **Nome**, insira uma descrição.

    Na Guia Rápida **Detalhes**, o campo **Ativos** exibe o número de ativos válidos que usam o contrato de garantia.

5. Na guia rápida **Linhas da garantia**, siga as etapas a seguir para adicionar linhas que devem ser incluídas em um contrato de garantia:

    1. Selecione **Adicionar linha** para adicionar uma nova condição à garantia. Um número de linha sequencial é inserido automaticamente no campo **Linha**.
    2. No campo **Período**, selecione o tipo de período de garantia.
    3. No campo **Intervalo**, insira um número. Este campo define o número de períodos para o qual a garantia deve ser válida.
    4. No campo **Porcentagem**, insira a porcentagem de cobertura para a linha de garantia. O percentual indica quanto é coberto por sua empresa.

![Página de garantia](media/01-warranty.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]