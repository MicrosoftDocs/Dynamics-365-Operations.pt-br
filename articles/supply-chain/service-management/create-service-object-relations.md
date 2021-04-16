---
title: Criar relacionamentos de objeto de serviço
description: Este tópico descreve como criar relações de objeto de serviço para um contrato de serviço e uma ordem de serviço.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 344037026399792d6da5777abbde8c9d0d9178f6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817620"
---
# <a name="create-service-object-relations"></a>Criar relacionamentos de objeto de serviço 

[!include [banner](../includes/banner.md)]


Este tópico descreve como criar relações de objeto de serviço para um contrato de serviço e uma ordem de serviço. Ao criar uma relação de objeto de serviço, você associa o objeto de serviço a um contrato de serviço ou à ordem de serviço. Quando um cliente solicita o serviço para um item que é um objeto de serviço, você pode selecionar o objeto de serviço na lista de relações de objeto de serviço.

## <a name="create-a-service-object-relation-for-a-service-agreement"></a>Criar uma relação de objeto de serviço para um contrato de serviço

Use as seguintes etapas para criar uma relação de objeto de serviço para um contrato de serviço:

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.

2.  Na lista de **Contratos de serviço**, selecione um contrato de serviço existente ou clique em **Novo** para criar um novo contrato de serviço.

3.  No formulário de **Contratos de serviço**, no **Painel de Ação**, na guia **Contrato de serviço**, no grupo **Relações**, clique em **Objetos de serviço**.

4.  No formulário **Objetos de serviço**, clique em **Novo** e, em seguida, selecione um objeto de serviço para este contrato de serviço.

5.  Para atribuir uma lista de materiais (BOM) de modelo ao contrato de serviço, clique em **Funções** e, em seguida, selecione **Anexar modelo de BOM**. No formulário **Selecionar modelo de BOM**, no campo **Modelo de BOM**, selecione um modelo. 

## <a name="create-a-service-object-relation-for-a-service-order"></a>Criar uma relação de objeto de serviço para uma ordem de serviço

Use as seguintes etapas para criar uma relação de objeto de serviço para uma ordem de serviço:

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.

2.  Na lista de **Ordens de serviço**, selecione uma ordem de serviço existente ou crie uma nova ordem de serviço.

3.  No formulário de **Ordens de serviço**, no **Painel de Ação**, na guia **Ordem de serviço**, no grupo **Relações**, clique em **Objetos de serviço**.

4.  No formulário **Objetos de serviço**, clique em **Novo** e, em seguida, selecione um objeto de serviço para esta ordem de serviço.

5.  Para atribuir uma lista de materiais (BOM) de modelo ao contrato de serviço, clique em **Funções** e, em seguida, selecione **Anexar modelo de BOM**. No formulário **Selecionar modelo de BOM**, no campo **Modelo de BOM**, selecione um modelo. 


## <a name="see-also"></a>Consulte também

[Visão geral de objetos de serviço](service-objects.md)

[Relações do objeto de serviço](service-object-relations.md)

[​BOMs de modelo​](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]