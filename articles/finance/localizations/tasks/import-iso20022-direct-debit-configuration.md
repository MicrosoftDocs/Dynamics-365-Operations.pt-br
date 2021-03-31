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
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 964f396625340d593a2fe3dd5be5a1b7da795e9a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218749"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]