---
title: O código do fornecedor não está autorizado para um produto e data específicos
description: Quando você tenta firmar uma ordem planejada ou adicionar uma linha a uma ordem de compra, você recebe uma mensagem de erro que afirma que o código do fornecedor não está autorizado para um produto e data.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 917526dfcefb36ce6e59af6f1f5bebc23ee6e53f
ms.sourcegitcommit: ab690bc897699ff8a4c489e749251fe0367050ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2022
ms.locfileid: "8489046"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a>O código do fornecedor não está autorizado para um produto e data específicos

Código de erro: SYP4881415

## <a name="symptoms"></a>Sintomas

Quando você tenta firmar uma ordem planejada ou adicionar uma linha a uma ordem de compra, você recebe a seguinte mensagem de erro:

> O código de fornecedor %1 não está autorizado para %2 em %3.

## <a name="cause"></a>Causa

O erro ocorre porque o campo **Método de verificação do fornecedor aprovado** está definido como *Apenas aviso* ou *Não permitido* para o produto especificado, e o fornecedor não está autorizado a fornecer esse produto.

## <a name="resolution"></a>Resolução

Para corrigir esse problema, desabilite a verificação de fornecedor para o produto relevante ou aprove o fornecedor.

Para desativar a verificação do fornecedor para um produto, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Abra o produto relevante.
1. No FastTab **Compra**, defina o campo **Método de verificação do fornecedor aprovado** como um valor diferente de *Apenas aviso* ou *Não Permitido*.

Para aprovar um fornecedor para um produto, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Abra o item relevante.
1. No Painel de ação, na guia **Compra**, no grupo **Fornecedor aprovado**, clique em **Configuração**.
1. Na página de lista **Fornecedor aprovado**, adicione uma linha à grade e defina os seguintes valores:

    - **Fornecedor** – Selecione o fornecedor para aprovar o produto atual.
    - **Data de vigência** – Selecione a primeira data para a aprovação do fornecedor.
    - **Data de vencimento** – Selecione a primeira data para a sua aprovação.

Para obter mais informações, consulte [Aprovar fornecedores para produtos específicos](../../procurement/tasks/approve-vendors-specific-products.md).
