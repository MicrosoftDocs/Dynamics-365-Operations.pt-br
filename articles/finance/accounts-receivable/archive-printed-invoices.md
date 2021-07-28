---
title: Arquivar faturas de clientes impressas com números de hash
description: Este tópico explica como habilitar o arquivamento a fim de armazenar faturas de clientes impressas com números de hash.
author: ilyako
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c627b6238a5c0ec1a45ebd9692aae7c634c4952e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356790"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a>Arquivar faturas de clientes impressas com números de hash

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Em alguns países, há um requisito legal de armazenar números de hash calculados no sistema juntamente com impressões de alguns documentos. Os números de hash podem ser usados para relatar autoridades e durante auditorias.

Este tópico explica como configurar o arquivamento a fim de armazenar faturas de clientes impressas com números de hash.

## <a name="prerequisites"></a>Pré-requisitos

- No espaço de trabalho **Gerenciamento de recursos**, ative o recurso, **Arquivar faturas de clientes impressas com números de hash**. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Configure os formatos imprimíveis dos documentos necessários em **Gerenciamento de impressão**.

Essa funcionalidade é aplicável aos documentos a seguir.

**Contas a receber**
- Fatura de cliente
- Nota de crédito de clientes
- Fatura de texto livre
- Nota de crédito em texto livre

**Gerenciamento e contabilidade do projeto**
- Fatura de projeto
- Nota de crédito do projeto

## <a name="configure-customer-master-data"></a>Configurar dados mestres do cliente
Conclua as etapas a seguir para configurar os dados do cliente e ativar a capacidade de salvar automaticamente as faturas impressas como anexos.

1. Acesse **Contas recebíveis** > **Todos os clientes**. 
2. Selecione um cliente e, na Guia Rápida **Fatura e entrega**, na seção **FATURA ELETRôNICA**, no campo **Anexo da fatura eletrônica**, selecione **Sim**.

## <a name="print-invoices"></a>Imprimir faturas
Você pode lançar e imprimir qualquer fatura do projeto, de cliente e de texto livre para o cliente configurado no procedimento anterior.

Abra a página **Anexos** da fatura impressa. Na Guia Rápida **Anexo**, no grupo de campos **Detalhes adicionais**, no campo **Número de hash do documento**, localize o número do hash armazenado calculado para a fatura impressa.

![Número hash do anexo.](media/attach-hash-num.jpg)

