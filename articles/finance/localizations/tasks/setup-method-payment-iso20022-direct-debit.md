---
title: Configurar método de pagamento para débito direto de ISO20022
description: Este procedimento mostra como configurar o método de pagamento de cliente do Débito direto ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 38afbc3a49d9020540a56e58ce51196b53d6a9e1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440235"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a>Configurar método de pagamento para débito direto de ISO20022

[!include [banner](../../includes/banner.md)]

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

