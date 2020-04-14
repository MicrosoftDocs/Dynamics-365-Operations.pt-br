---
title: Configuração do débito direto ISO20022 de importação
description: Este procedimento demonstra como importar uma configuração de relatório eletrônico de pagamento de cliente.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5d4256b155d3e06d63e425fab63b4025ef2577f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140009"
---
# <a name="import-iso20022-direct-debit-configuration"></a>Configuração do débito direto ISO20022 de importação

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como importar uma configuração de relatório eletrônico de pagamento de cliente. Este procedimento usa o formato de débito direto ISO 20022 como exemplo. 



Este procedimento foi criado usando a empresa de dados de demonstração DEMF, mas você pode usar qualquer empresa de dados de demonstração para essa finalidade.



Este é o primeiro dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Na lista de provedores de configuração disponíveis, selecione Microsoft.
3. Clique em Definir como ativo.
4. Clique em Repositórios.
5. Clique em Abrir.
6. Clique em Mostrar filtros.
7. Aplicar os seguintes filtros: inserir um valor de filtro de "Débito direto ISO20022 (DE)", no campo "Nome da configuração" usando o operador de filtro "começa com"
    * Opcionalmente, você pode localizar a configuração na lista, selecioná-la e ignorar essa etapa.  
8. Clique em Importar.
    * Se o botão Importar não estiver disponível, significa que a configuração já foi importada.  
9. Clique em Sim.

