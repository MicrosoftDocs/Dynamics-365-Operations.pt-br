---
title: Configuração de transferência de crédito ISO20022 de importação
description: Este procedimento mostra como importar uma configuração de relatório eletrônico de pagamento de fornecedor.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a96827bc6e126a7f5de6d67338b5233a65d93c8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840904"
---
# <a name="import-iso20022-credit-transfer-configuration"></a>Configuração de transferência de crédito ISO20022 de importação

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como importar uma configuração de relatório eletrônico de pagamento de fornecedor. O formato alemão de transferência de crédito ISO 20022 é usado como exemplo. Este procedimento pode ser usado para outros formatos de relatório eletrônico disponíveis. 

Esta tarefa foi criada usando a empresa de dados de demonstração DEMF, mas você pode usar qualquer empresa de dados de demonstração para concluir a tarefa.

Esta é a primeira de cinco tarefas que, juntas, ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico. Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Na lista de provedores de configuração disponíveis, selecione Microsoft.
3. Clique em Definir como ativo.
4. Clique em Repositórios.
5. Clique em Abrir.
6. Clique em Mostrar filtros.
7. Aplicar os seguintes filtros: inserir um valor de filtro de "Transferência de Crédito ISO20022 (DE)", no campo "Nome da configuração" usando o operador de filtro "começa com"
    * Como alternativa, você pode localizar a configuração na lista, selecioná-la e movê-la para a tarefa de importação.  
8. Clique em Importar.
    * Se o botão Importar não estiver disponível, significa que a configuração já foi importada.  
9. Clique em Sim.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]