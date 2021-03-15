---
title: Visão geral de pagamento positivo
description: Este artigo oferece informações sobre o pagamento positivo, usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco.
author: panolte
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: ffb2ded8c6f1e86657f298f3638da39ac4c63b66
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972097"
---
# <a name="positive-pay-overview"></a>Visão geral de pagamento positivo

[!include [banner](../includes/banner.md)]

Este artigo oferece informações sobre o pagamento positivo, usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco. 

O pagamento positivo é usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco. Os arquivos de pagamento positivo podem ajudar os bancos a impedir fraudes com cheques. Você configura o pagamento positivo para gerar uma lista eletrônica de cheques todas as vezes que cheques forem impressos. Em seguida, quando um cheque é apresentado ao banco, o banco compara o cheque à lista de cheques emitidos anteriormente. Se o cheque corresponder a um cheque na lista, o banco o liberará. Se o cheque não corresponder a um cheque na lista, o banco o reterá para revisão.

O pagamento positivo é conhecido também como SafePay. 

Os arquivos de pagamento positivo podem conter dados sigilosos sobre o credor e valores de cheque. Portanto, certifique-se de usar medidas de segurança apropriadas a partir do momento em que os arquivos são geradas até o momento em que são recebidos pelo banco. Os arquivos de pagamento positivos são baixados de acordo com as instruções de download para o navegador da Web. 

Os arquivos de pagamento positivo são criados usando entidades de dados. Antes de gerar um arquivo de pagamento positivo, você deverá configurar os formatos de transformação para o XML que traduz os dados em um formato que o banco pode consumir. 

Para cada conta bancária que você deseja gerar as informações de pagamento positivo, é necessário atribuir o formato de pagamento positivo. Depois de gerar pagamentos, você poderá gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária. Como alternativa, você pode gerar arquivos de pagamento positivo para várias entidades legais e contas bancárias ao mesmo tempo. 

Depois que os cheques listados em um arquivo de pagamento positivo forem pagos, você receberá um número de confirmação do banco. Em seguida, será possível confirmar o arquivo de pagamento positivo no sistema. 

Se você tiver de alterar um arquivo de pagamento positivo, poderá cancelá-lo. Em seguida, para cada cheque no arquivo de pagamento positivo, o campo que indica se esse cheque foi incluído em um arquivo de pagamento positivo será redefinido.

Para obter mais informações, consulte [Configurar e gerar arquivos de pagamento positivo](set-up-generate-positive-pay-files.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]