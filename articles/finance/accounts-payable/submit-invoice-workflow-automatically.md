---
title: Enviar faturas para o sistema do fluxo de trabalho e conciliar as linhas de recebimento de produtos (versão preliminar)
description: Este tópico explica o processo de envio de faturas de fornecedor para o sistema de fluxo de trabalho e a conciliação automática das linhas de recebimento de produtos lançadas para faturas de fornecedor.
author: abruer
manager: AnnBe
ms.date: 09/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: cde164ee89b542d769d81d8d483049fb7ca001c4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440193"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines-preview"></a>Enviar faturas para o sistema do fluxo de trabalho e conciliar as linhas de recebimento de produtos (versão preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica o processo de envio de faturas de fornecedor para o sistema de fluxo de trabalho e a conciliação automática das linhas de recebimento de produtos lançadas para faturas de fornecedor.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Enviando faturas de fornecedor importadas para o sistema de fluxo de trabalho e conciliando linhas de recebimento de produtos lançadas para linhas de fatura de fornecedor pendentes

Como parte de um processo de faturamento de Contas a pagar, você pode fazer o sistema enviar automaticamente uma fatura importada para o sistema de fluxo de trabalho. Você pode configurar o processo de envio de faturas importadas para o sistema de fluxo de trabalho na guia **Automação de fatura de fornecedor** da página **Parâmetros de contas a pagar** (**Contas a pagar \> Configuração \> Parâmetros de contas a pagar**). O processo de envio para fluxo de trabalho será executado em segundo plano, na frequência especificada por você (por hora ou por dia).

Ao enviar faturas automaticamente para o sistema de fluxo de trabalho, você deve começar com uma fatura importada. Para garantir que a fatura possa ser processada do início ao fim sem intervenção manual, você deve incluir uma tarefa de lançamento automatizada na configuração do fluxo de trabalho. As faturas relacionadas a ordens de compra (POs) e faturas que contêm uma categoria de compras não-OC e linhas não estocadas podem ser automaticamente enviadas para o sistema de fluxo de trabalho. As faturas inseridas manualmente devem ser enviadas manualmente para o sistema de fluxo de trabalho.

O valor **Enviado por** no fluxo de trabalho é o ID do usuário que foi informado para a tarefa em segundo plano **Enviar faturas do fornecedor para fluxo de trabalho** na página **Automação do processo**. O usuário com essa ID de usuário poderá cancelar a fatura do sistema de fluxo de trabalho, conforme a necessidade.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Conciliação de recebimentos de produtos lançados para linhas da fatura que têm uma política de conciliação tripla

Como parte de um processo de faturamento de contas a pagar sem contato, o sistema pode coincidir automaticamente os recebimentos de produtos lançados para as linhas da fatura. Uma política de conciliação tripla deve ser definida para esta tarefa. Este recurso estará disponível se o recurso **Automação de fatura de fornecedor** tiver sido habilitado na página **Gerenciamento de recursos**.

O processo será executado até que a quantidade de recebimento de produtos conciliada seja igual à quantidade da fatura. Como parte desse processo, você pode especificar o número máximo de vezes que o sistema deve tentar conciliar os recebimentos de produtos em uma linha da fatura antes de concluir que o processo falhou. O processo será executado em segundo plano, tanto por hora quanto por dia. Você pode executar o processo de correspondência automatizado como parte do processo de envio de faturas para o sistema de fluxo de trabalho. Como alternativa, você pode executá-lo como um processo autônomo. As configurações do processo de conciliação de recebimentos do produto para linhas da fatura são definidas na guia **Automação da fatura do fornecedor** da página **Parâmetros de contas a pagar** (**Contas a pagar \> Configuração \> Parâmetros de contas a pagar**).

As linhas da fatura que têm uma política de conciliação tripla, na qual a quantidade de recebimento conciliada é menor do que a quantidade da fatura, será incluída no processo de conciliação automática de recebimento de produtos.

Para exibir o status **Última conciliação** para faturas que não fazem parte do processo de envio para fluxo de trabalho, abra a fatura da página **Faturas do fornecedor**. Quando você exibe a fatura, as informações de validação conciliadas são atualizadas.

Uma linha da fatura será excluída do processamento automatizado, se qualquer uma das seguintes condições forem atendidas:

- O valor **Status de conciliação automática de recibo** da linha da fatura for **Com falha**.
- A fatura está sendo usada.
- A fatura está no sistema de fluxo de trabalho.
