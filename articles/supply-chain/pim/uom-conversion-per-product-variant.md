---
title: Conversão de unidade de medida por variante de produto
description: Este tópico explica como as conversões de unidade de medida podem ser configuradas em grades do produto.
author: johanhoffmann
manager: AnnBe
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 9d5d6fd65717cd886f1c6576aabf2bc59ca4fcaf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "345918"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Conversão de unidade de medida por variante de produto

[!include [banner](../includes/banner.md)]

[!include [pivate-preview](../includes/pivate-preview-banner.md)]

Este tópico explica como as conversões de unidade de medida podem ser configuradas em grades do produto. Ele iInclui um exemplo da instalação.

Esse recurso permite que as empresas definam a conversão de unidades diferentes entre as grades do mesmo produto. O exemplo a seguir é usado neste tópico. Uma empresa vende camisetas nos tamanhos pequeno, médio, grande e extra grande. A camiseta é definida como um produto; os diferentes tamanhos são definidos como grades do produto. As camisetas são embaladas em caixas e uma caixa pode conter cinco camisetas, exceto no tamanho extra grande, em que há espaço para apenas quatro camisetas. A empresa deseja rastrear as diferentes grades das camisetas na unidade em **Peças** mas está vendendo as camisetas na unidade **Caixas**. A conversão entre a unidade de estoque e a unidade de venda é 1 caixa = 5 peças, exceto para a grade extra grande, onde a conversão é 1 caixa = 4 peças.

## <a name="setup"></a>Instalação

Você pode configurar parâmetros para usar o recurso para produtos habilitados para **Todos os processos** ou apenas para produtos habilitados para **Processos de depósito** usando a opção **Habilitar conversações de unidade de medida** na página **Parâmetros de informações do produto**.

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Configurar um produto para a conversão de unidade por grade

Grades de produto só podem ser criadas para o **Subtipo de produto**: **Produto mestre**. Para obter mais informações, consulte [Criar um produto mestre](tasks/create-product-master.md).

O recurso não está habilitado para produtos configurados para processos de peso variável. 

Durante a criação de uma produto mestre, habilite a conversão de unidade de medida usando a opção **Habilite as conversões de unidade de medida** na página **Detalhes do produto**.

Quando o produto mestre com grades de produtos liberados for criado, as conversões de unidade por grades poderão ser configuradas. Você pode encontrar o item de menu para abrir a página de conversão de unidade no contexto de um produto ou de uma grade de produtos nas páginas a seguir.

-   Página **Detalhes de produto**
-   Página **Detalhes de produtos liberados**
-   Página **Grades de produtos liberados**

Quando você abre a página **Conversão de unidades** no contexto de um produto mestre ou de uma grade de produtos liberados, pode selecionar se deseja configurar a conversão de unidade para o produto ou para uma grade de produtos. Para fazer isso, selecione **Grade de produto** ou **Produto** no campo **Criar conversão para**.

### <a name="product-variant"></a>Grade de produto

Se você selecionar **Grade de produto**, poderá selecionar para que grade deseja configurar a conversão de unidade no campo **Grade de produto**.

### <a name="product"></a>Produto

Se você selecionar **Produto**, poderá configurar uma conversão de unidade para os produtos mestres. Essa conversão de unidade será aplicada a todas as grades de produtos sem uma conversão de unidades definida.

### <a name="example"></a>Exemplo

Um produto mestre, **Camiseta**, tem quatro grades de produtos liberadas, pequeno, médio, grande e extra grande. As camisetas são embaladas em caixas e uma caixa pode conter cinco camisetas, exceto no tamanho extra grande, em que há espaço para apenas quatro camisetas.

Primeiro, abra a página **Conversão de unidades** da página Detalhes de produtos liberados para **Camiseta**.

Na página **Conversão de unidades**, configure a conversão de unidades para a grade de produtos liberados Extra Grande.

| **Campo**             | **Configuração**             |
|-----------------------|-------------------------|
| Criar conversão para | Grade de produto         |
| Grade de produto       | Camiseta: : extra grande: : |
| De unidade             | Caixas                   |
| Fator                | 4                       |
| Para unidade               | Partes                  |

As variantes de produtos liberados pequena, médio e grande têm a mesma unidade de conversão entre a caixa de unidade e peças. Isso significa que você pode definir a conversão de unidade para essas grades de produtos no produto mestre.

| **Campo**             | **Configuração** |
|-----------------------|-------------|
| Criar conversão para | Produto     |
| Produto               | Camiseta     |
| De unidade             | Caixas       |
| Fator                | 5           |
| Para unidade               | Partes      |

### <a name="using-excel-to-update-the-unit-conversions"></a>Usando o Excel para atualizar as conversões de unidade

Se um produto tiver muitas grades de produtos com conversões de unidade diferentes, será aconselhável exportar as conversões de unidades da página **Conversão de unidades** para uma planilha do Excel, atualizar as conversões e publicá-las novamente no Finance and Operations.

A opção para exportar para o Excel e publicar as edições no Finance and Operations é habilitada do item de menu **Abra no Microsoft Office** no painel de ações na página **Conversão de unidade**.
