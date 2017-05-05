---
title: "Visão geral de pagamento positivo"
description: "Este artigo oferece informações sobre o pagamento positivo, usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 1fd606817b06a05b9abaaedf20ea9872bd7edd5d
ms.openlocfilehash: cb4806a1f023c1e60311ff9d8facb4ef5717ad94
ms.lasthandoff: 03/31/2017


---

# <a name="positive-pay-overview"></a>Visão geral de pagamento positivo

[!include[banner](../includes/banner.md)]


Este artigo oferece informações sobre o pagamento positivo, usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco. 

O pagamento positivo é usado para gerar uma lista eletrônica de cheques que pode ser apresentada a um banco. Os arquivos de pagamento positivo podem ajudar os bancos a impedir fraudes com cheques. Você configura o pagamento positivo para gerar uma lista eletrônica de cheques todas as vezes que cheques forem impressos. Em seguida, quando um cheque é apresentado ao banco, o banco compara o cheque à lista de cheques emitidos anteriormente. Se o cheque corresponder a um cheque na lista, o banco o liberará. Se o cheque não corresponder a um cheque na lista, o banco o reterá para revisão.

O pagamento positivo é conhecido também como SafePay. 

Os arquivos de pagamento positivo podem conter dados sigilosos sobre o credor e valores de cheque. Portanto, certifique-se de usar medidas de segurança apropriadas a partir do momento em que os arquivos são geradas até o momento em que são recebidos pelo banco. Os arquivos de pagamento positivos são baixados de acordo com as instruções de download para o navegador da Web. 

Os arquivos de pagamento positivo são criados usando entidades de dados. Antes de gerar um arquivo de pagamento positivo, você deverá configurar os formatos de transformação para o XML que traduz os dados em um formato que o banco pode consumir. 

Para cada conta bancária que você deseja gerar as informações de pagamento positivo, é necessário atribuir o formato de pagamento positivo. Depois de gerar pagamentos, você poderá gerar um arquivo de pagamento positivo para uma única entidade legal e uma única conta bancária. Como alternativa, você pode gerar arquivos de pagamento positivo para várias entidades legais e contas bancárias ao mesmo tempo. 

Depois que os cheques listados em um arquivo de pagamento positivo forem pagos, você receberá um número de confirmação do banco. Então, será possível confirmar o arquivo de pagamento positivo no Microsoft Dynamics 365 for Operations. 

Se você tiver de alterar um arquivo de pagamento positivo, poderá cancelá-lo. Em seguida, para cada cheque no arquivo de pagamento positivo, o campo que indica se esse cheque foi incluído em um arquivo de pagamento positivo será redefinido.

Para obter mais informações, consulte [Configurar e gerar arquivos de pagamento positivo](set-up-generate-positive-pay-files.md).



