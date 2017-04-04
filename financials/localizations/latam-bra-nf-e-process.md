---
title: "Visão geral do processo de NF-e para O Brasil"
description: "Este tópico fornece uma visão geral do processo para configurar e enviar uma Nota fiscal eletrônica de NF-e () para registrar a movimentação de itens e de serviço entre duas partes."
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
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: aa8d34b5a10144e20c18210df2196dbed23088c4
ms.lasthandoff: 03/31/2017


---

# <a name="nf-e-process-overview-for-brazil"></a>Visão geral do processo de NF-e para O Brasil

Este tópico fornece uma visão geral do processo para configurar e enviar uma Nota fiscal eletrônica de NF-e () para registrar a movimentação de itens e de serviço entre duas partes.

Você pode usar uma Nota fiscal eletrônica de NF-e () para registrar a movimentação de itens e de serviço entre duas partes. Você pode gerar uma NF-e de qualquer uma das seguintes notas fiscais:

-   Ordens de venda
-   Ordens de compra para fornecedores não contribuinte
-   Faturas de projeto
-   Notas fiscais de transferência ou apropriação de imposto
-   Faturas de texto livre

Antes de gerar um NF-e, você deve concluir as seguintes tarefas:

-   Configure serviços da Web, códigos de rejeição e esquemas para um domínio.
-   Para cada, estabelecimento fiscal configurar um certificado, um ambiente, versões de NF-e, uma autoridade, modelo, a validação de esquemas, e um modo de contingência de NF-e o. Além disso, configure a impressão do auxiliar fiscal eletrônica de Documento Nota a Dinamarca (DANFE), assim o DANFE é impressa automaticamente após aprovação de NF-e.
-   Configure os serviços da Web relacionados a uma autoridade fiscal.
-   Configure um tipo de documento fiscal para uma NF-e.

Depois que você gera uma NF-e, pode enviar a NF-e assinada digitalmente para a Secretaria da Fazenda (SEFAZ) em uma mensagem XML. Os itens poderão ser entregues depois que a NF-e for aprovada eletronicamente pela SEFAZ. O processo da NF-e inclui as seguintes etapas:

1.  O estabelecimento fiscal lançar uma nota fiscal com um tipo de documento fiscal configurado para o modelo de documento fiscal 55 para gerar um NF-e.
2.  O processo da exportação ou importação de NF-e detecta a nota fiscal lançada para o modelo de documento fiscal 55 e gera uma mensagem no formato XML. Uma mensagem XML separada é gerada para cada NF-e. As mensagens XML é passado. a SEFAZ
3.  A SEFAZ processa a mensagem XML e retorna um protocolo e um status para cada NF-e. O status e o protocolo de NF-e são atribuídos no NF-e usado no processo da exportação ou importação de NF-e. O status que é retornado pode ser aprovada ** **, ** negada ** **, rejeitado ** **, cancelado ** **, não fixável rejeitado **, ** ** ou rejeitado. Esta informação é usada para atualizar o status de nota fiscal no Microsoft Dynamics 365 para as operações.

Depois que o status de NF-e for recebido de SEFAZ, execute as tarefas a seguir, dependendo do status:

-   Se a NF-e for aprovada, você poderá imprimir o DANFE. Alternativamente, se imprimir ** o DANFE quando o NF-e é aprovado ** a opção selecionada ** NF-e federal ** em FastTab ** estabelecimentos fiscais ** de página, o DANFE é impressa automaticamente.
-   Se a NF-e for negada, será necessário cancelá-la.
-   Se o NF-e é anulada e pode ser fixo, você pode corrigir informações incorretas, clique em enviar novamente ** ** ** NF-e federal ** ** na guia nota fiscal ** de página para reenviar o NF-e a SEFAZ.
-   Se o NF-e é anulada e não pode ser fixo, você deve cancelar o NF-e rejeitado que rejeitou o número. O processo da exportação ou importação de NF-e detecta a nota fiscal que é lançado e marcada para o descarte, e gera uma mensagem XML do formato especificado para o número de NF-e rejeitado. Esta mensagem XML é passado na SEFAZ, e o status de nota fiscal definido é como ** ** rejeitado.



