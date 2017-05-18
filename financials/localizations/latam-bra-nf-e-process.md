---
title: "Visão geral do processo de NF-e para o Brasil"
description: "Este tópico fornece uma visão geral do processo para configurar e enviar uma Nota fiscal eletrônica de (NF-e) para registrar a movimentação de itens e de serviço entre duas partes."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EFDocContingencyMode_BR, EFDocContingencyModeHistory_BR, EFDocCorrectionLetter_BR, EFDocEmailAccountConfiguration_BR, EFDocEmailStatus_BR, EFDocHist_BR, EFDocParameters_BR, EFDocServiceInquire_BR, FiscalDocument_BR
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269114
ms.assetid: 7cb522a4-2f84-4399-a60d-8692df6e08f3
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: b20cc5f0f5448c3221e1ebd465b920d2ba576c46
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="nf-e-process-overview-for-brazil"></a>Visão geral do processo de NF-e para o Brasil

[!include[banner](../includes/banner.md)]


Este tópico fornece uma visão geral do processo para configurar e enviar uma Nota fiscal eletrônica de (NF-e) para registrar a movimentação de itens e de serviço entre duas partes.

Você pode usar uma Nota Fiscal eletrônica (NF-e) para registrar a movimentação de itens e serviços entre dois participantes. Você pode gerar uma NF-e de qualquer uma das seguintes notas fiscais:

-   Ordens de venda
-   Ordens de compra para fornecedores não contribuinte
-   Faturas de projeto
-   Notas fiscais de transferência ou apropriação de imposto
-   Faturas de texto livre

Antes de gerar uma NF-e, você deve concluir as seguintes tarefas:

-   Configure serviços da Web, códigos de rejeição e esquemas para um domínio.
-   Para cada estabelecimento fiscal configure um ambiente, uma versão de NF-e, uma autoridade, um modelo, validação de esquema e um modo de contingência para NF-e. Além disso, configure a impressão automática do Documento auxiliar da Nota fiscal eletrônica (DANFE), de forma que o DANFE seja impresso automaticamente após a aprovação da NF-e.
-   Configure os serviços da Web relacionados a uma autoridade fiscal.
-   Configure um tipo de documento fiscal para uma NF-e.

Depois que você gera uma NF-e, pode enviar a NF-e assinada digitalmente para a Secretaria da Fazenda (SEFAZ) em uma mensagem XML. Os itens poderão ser entregues depois que a NF-e for aprovada eletronicamente pela SEFAZ. O processo da NF-e inclui as seguintes etapas:

1.  O estabelecimento fiscal lança uma nota fiscal usando um tipo de nota fiscal que é configurado para o modelo de nota fiscal 55 para gerar uma NF-e.
2.  O processo de exportação ou de importação detecta a nota fiscal lançada para o modelo de nota fiscal 55 e gera uma mensagem XML no formato especificado. Uma mensagem XML separada é gerada para cada NF-e. A mensagem XML é transmitida à SEFAZ.
3.  A SEFAZ processa a mensagem XML e retorna um protocolo e um status para cada NF-e. O status da NF-e e o protocolo são então atribuídos à NF-e que é usada no processo de exportação ou importação de NF-e. O status que é retornado pode ser **Aprovado**, **Negado**, **Rejeitado**, **Cancelado**, **Rejeitado sem correção** ou **Rejeitado**. Esta informação é usada para atualizar o status da nota fiscal no Microsoft Dynamics 365 for Operations.

Depois que o status da NF-e for recebido da SEFAZ, você poderá executar as seguintes tarefas, dependendo do status:

-   Se a NF-e for aprovada, você poderá imprimir o DANFE. Como alternativa, se a opção **Imprimir DANFE quando NF-e for aprovada** for selecionada na FastTab **NF-e federal** da página **Estabelecimentos fiscais**, o DANFE será impresso automaticamente.
-   Se a NF-e for negada, será necessário cancelá-la.
-   Se a NF-e for rejeitada e puder ser corrigida, você poderá corrigir as informações incorretas e depois poderá clicar em **Reenviar** na guia **NF-e federal** da página **Documento fiscal** para reenviar a NF-e à SEFAZ.
-   Se a NF-e for rejeitada e não puder ser corrigida, você deverá cancelar a NF-e descartada que tem o número descartado. O processo de exportação ou de importação da NF-e detecta a nota fiscal lançada e marcada para descarte e então gera uma mensagem XML no formato especificado para o número da NF-e descartada. Esta mensagem XML é transmitida à SEFAZ, e o status da nota fiscal é definido é como **Rejeitado**





