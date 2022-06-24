---
title: Tipos de problema para não conformidades
description: Este artigo descreve como criar e usar tipos de problema para não conformidades.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a73e692257c2a27085d60e75e028445811ee778a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857740"
---
# <a name="problem-types-for-nonconformances"></a>Tipos de problema para não conformidades

[!include [banner](../includes/banner.md)]

Este artigo descreve como criar e usar tipos de problema para não conformidades.

Use a página **Tipos de problema** para definir uma classificação dos problemas de qualidade que podem ocorrer nos vários tipos de não conformidade. Para cada tipo de problema criado, você deve especificar os tipos de não conformidades com os quais o tipo de problema pode ser usado. Você pode configurar os tipos de não conformidade a seguir:

- **Interno** – Não conformidades deste tipo estão relacionadas ao estoque disponível (por exemplo, ordens de qualidade ou ordens de quarentena).
- **Cliente** – Não conformidades deste tipo estão relacionadas a ordens de venda.
- **Fornecedor** – Não conformidades deste tipo estão relacionadas a ordens de compra.
- **Solicitação de serviço** – Não conformidades deste tipo estão relacionadas a ordens de serviço.
- **Produção** – Não conformidades deste tipo estão relacionadas a ordens de lote ou ordens de produção.
- **Produção de coprodutos** – Não conformidades deste tipo estão relacionadas a ordens de lote para coprodutos.

Ao criar um novo tipo de problema, selecione **Tipos de não conformidade** no Painel de Ações para criar uma lista de um ou mais tipos de não conformidade que estão autorizados para o tipo de problema. Por exemplo, um tipo de problema relacionado a um código de defeito pode ser aplicado a todos os tipos de não conformidade. No entanto, um tipo de problema relacionado a reclamações de clientes pode ser aplicado somente aos tipos de não conformidade **Cliente** e **Solicitação de serviço**.

## <a name="examples-of-problem-types"></a>Exemplos de tipos de problema

Veja alguns exemplos de cenários de tipos de problema que podem ser usados com os diferentes tipos de não conformidade:

- **Cliente:** um cliente registrou uma reclamação, um cliente fez uma devolução ou as especificações de qualidade não foram atendidas.
- **Fornecedor:** o produto foi danificado, as especificações de qualidade não foram atendidas ou o produto incorreto foi recebido.
- **Solicitação de serviço:** as especificações de qualidade não foram atendidas, um cliente registrou uma reclamação ou a manutenção da máquina é necessária.
- **Produção:** as especificações de qualidade não foram atendidas, a manutenção da máquina é necessária ou o produto foi danificado.
- **Produção de coprodutos:** as especificações de qualidade não foram atendidas, a manutenção da máquina é necessária ou o produto foi danificado.

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a>Criar um tipo de problema e atribuí-lo a tipos de não conformidade

1. Acesse **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Tipos de problema**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Tipo de problema** – Insira um nome ou uma ID exclusiva para o tipo de problema.
    - **Descrição** – Insira uma descrição detalhada do tipo de problema.

1. Enquanto a nova linha ainda estiver selecionada, selecione **Tipos de não conformidade** no Painel de Ações.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Em seguida, para a nova linha, defina o campo **Tipo de não conformidade** como o tipo de não conformidade que você deseja permitir para o tipo de problema.
1. Repita a etapa anterior para cada tipo de não conformidade adicional que você deseja autorizar para o tipo de problema.
1. Feche as páginas.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do gerenciamento de qualidade](quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Trabalhadores responsáveis por aprovar não conformidades](quality-responsible-workers.md)
- [Zonas de quarentena para não conformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico para não conformidades](quality-diagnostic-types.md)
- [Encargos de qualidade para não conformidades](quality-charges.md)
- [Operações para não conformidades](quality-operations.md)
- [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
