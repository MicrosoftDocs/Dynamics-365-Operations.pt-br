---
title: Configurar um técnico preferido
description: Você pode selecionar qualquer trabalhador como um técnico preferido para um contrato ou uma ordem de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 850d91372fb1a918840ebc316a4479f4a70bdc24
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421861"
---
# <a name="set-up-a-preferred-technician"></a>Configurar um técnico preferido 

[!include [banner](../includes/banner.md)]


Você pode selecionar qualquer trabalhador como um técnico preferido para um contrato ou uma ordem de serviço. Entretanto, é recomendável adicionar o trabalhador à equipe de expedição apropriada de forma que ele seja incluído em **Quadro de expedição**.

## <a name="assign-employee-to-a-dispatch-team"></a>Atribuir funcionário a uma equipe de expedição

1.  Clique em **Recursos humanos** \> **Comum** \> **Trabalhadores** \> **Trabalhadores**. Clique duas vezes em um trabalhador para abrir a página de detalhes sobre ele. No **Painel de Ação**, clique em **Configuração** \>**Equipe de expedição** para abrir o formulário **Trabalhadores de expedição**.

2.  No formulário **Equipe de expedição**, selecione a equipe para a qual o trabalhador será atribuído.

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a>Atribuir um técnico preferido a um contrato de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**. Clique duas vezes em um contrato de serviço para abrir o formulário de detalhes.

2.  Na guia **Geral**, selecione o campo **Técnico preferido** e então selecione um membro da equipe de expedição apropriada como o técnico preferido para o contrato de serviço.

## <a name="assign-a-preferred-technician-to-a-service-order"></a>Atribuir um técnico preferido a uma ordem de serviço

1.  Clique em **Gerenciamento de serviço** \> **Periódico** \> **Quadro de expedição**.
    

    > [!NOTE]
    > <P>No formulário <STRONG>Quadro de expedição</STRONG>, especifique um intervalo de datas para as atividades de expedição que deseja exibir. Também especifique se deseja exibir as atividades fechadas e limitar a lista de atividades de expedição a equipes às quais você pertence ou está autorizado a monitorar. Clique em <STRONG>OK</STRONG> para abrir a caixa de diálogo <STRONG>Quadro de expedição</STRONG>.</P>



2.  Selecione a linha da atividade de serviço a ser modificada.

3.  Na guia **Relacionado**, use a lista **Trabalhador** para atribuir um membro da equipe de expedição apropriada como o técnico preferido para a chamada de serviço.

## <a name="see-also"></a>Consulte também

[Visão geral de desenvolvimento e estabelecimento de contratos de serviço](service-agreements.md)

[Criar ordens de serviço manualmente](create-service-orders-manually.md)

[Contratos de serviço (formulário)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]