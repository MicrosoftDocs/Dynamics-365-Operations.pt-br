--- 
title: "Configurar códigos de disposições"
description: "Este procedimento se concentra na configuração de um código de disposição que pode ser usado em um dispositivo móvel para o processo de recebimento da ordem de devolução."
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c004543188656dfd53d7539717cd6e93d0b9f47a
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-dispositions-codes"></a>Configurar códigos de disposições

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento se concentra na configuração de um código de disposição que pode ser usado em um dispositivo móvel para o processo de recebimento da ordem de devolução. Códigos de disposição são um conjunto de regras que podem ser usadas quando itens são recebidos. Por exemplo, quando um usuário de trabalho utiliza um dispositivo móvel para receber itens que foram danificados, o usuário deve escanear um código de disposição para itens danificados. O status de estoque dos bens recebidos, o modelo de trabalho, e a diretiva de localização podem ser determinados a partir do código de disposição escaneado. Para os processos de recebimento da ordem de compra e de relatório de ordem de produção como concluída, o uso de um código de disposição é opcional. Para o processo de recebimento de devolução da ordem de venda, se os itens forem registrados utilizando um dispositivo móvel, o uso do código de disposição é obrigatório.  Esse guia foi criado usando a empresa de dados de demonstração USMF. Esse procedimento é destinado ao gerente do depósito. 

1. Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Códigos de disposição.
2. Clique em Novo.
    * Crie um novo código de disposição a ser usado para devoluções de clientes.  
3. No campo Código de descrição, digite um valor.
4. No campo Status do estoque, selecione um status de estoque onde exista bloqueio de estoque.
    * Se você estiver usando USMF, selecione 'Bloqueio'. Você pode adicionar um status de estoque ao código de disposição para substituir o status padrão que está nas linhas da ordem.  
5. No campo Modelo de trabalho, digite um valor.
    * Opcional: Selecione um código de modelo de trabalho associado a uma ordem de devolução. Se nenhum valor for fornecido, o modelo de trabalho será resolvido usando as regras padrão configuradas no sistema. Selecionar um modelo de trabalho irá limitar os processos para os quais este código de disposição pode ser usado. Por exemplo, se um código de disposição tem um modelo de trabalho com uma ordem de trabalho do tipo ordem de compra, ele não poderá ser usado para registrar os itens que são devolvidos por clientes.  
6. No campo Código de disposição de devolução, digite um valor.
    * O código de disposição de devolução determina o restante do processo da ordem de devolução para os itens registrados. Neste exemplo, o cliente deve receber uma nota de crédito. Adicione um código de disposição de devoluções que contenha uma ação de Crédito.  


