---
title: Configurar método de pagamento para transferência de crédito de ISO20022
description: Este procedimento mostra como configurar o método de pagamento de fornecedor da transferência de crédito ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7f87cc0dfa47295f047ef97732f60733c362ca4066d9070418322b34934e3ce3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773651"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>Configurar método de pagamento para transferência de crédito de ISO20022

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como configurar o método de pagamento de fornecedor da transferência de crédito ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo. 

Antes de concluir esta tarefa, você deve exportar as configurações de formato e definir as contas de pagamento.

Essa tarefa foi criada usando a empresa de dados demonstrativos DEMF.

Este é o terceiro dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico. Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.

1. Acesse Contas a pagar > Configurar pagamento > Métodos de pagamento.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Método de pagamento com um valor de 'SEPA CT'.
3. Clique em Editar.
4. No campo Período, selecione 'Total'.
5. No campo Tipo de liquidação, selecione 'Pagamento eletrônico'.
6. Expanda a seção Formatos de arquivo.
7. Selecione Sim no campo eletrônico Genérico do relatório.
8. No campo Exportar configuração de formato, insira ou selecione um valor.
    * Na lista, selecione a transferência de crédito do valor ISO20022 (DE). Se a lista estiver vazia, a configuração de formato de exportação do pagamento do fornecedor não foi importada e não está ativa.  
9. No campo Tipo de conta, selecione 'Banco'.
10. No campo Conta de pagamento, especifique os valores 'DEMF OPER'.
11. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]