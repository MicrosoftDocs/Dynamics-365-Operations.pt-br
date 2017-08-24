--- 
title: "Configurar método de pagamento do débito direto ISO20022"
description: "Este procedimento mostra como configurar o método de pagamento de cliente do Débito direto ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 16ff0cc28b272add80b08ae43b9fe5b8e7370b70
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-method-of-payment-for-iso20022-direct-debit"></a>Configurar método de pagamento do débito direto ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar o método de pagamento de cliente do Débito direto ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo. 



Antes de concluir esta tarefa, você deve definir as configurações do formato de exportação e as contas de pagamento.



Este procedimento foi criado usando a empresa de dados de demonstração DEMF.



Este é o terceiro dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.

1. Vá para Contas a receber > Configurar pagamentos > Métodos de pagamento.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Método de pagamento com um valor de 'ELECTRONIC'.
3. Clique em Editar.
4. No campo Conta de pagamento, especifique os valores 'DEMF OPER'.
5. Expanda a seção Formatos de arquivo.
6. Selecione Sim no campo eletrônico Genérico do relatório.
7. No campo Exportar configuração de formato, insira ou selecione um valor.
    * Na lista, selecione Débito direto ISO20022 (DE).  Se a lista estiver vazia, a configuração de formato de exportação do pagamento do cliente não foi importada e não está ativa.  
8. Selecione Sim no campo de Solicitação obrigatório.
    * Selecione o parâmetro Exigir carta de ordem para os formatos de pagamento de cliente, o qual exige a inclusão das informações da carta de ordem na mensagem de pagamento, como Débito direto SEPA.  
9. Clique em Salvar.


