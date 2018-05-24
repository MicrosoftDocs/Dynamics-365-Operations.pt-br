---
title: "Criar relações de tarefas de serviço"
description: "Você pode associar tarefas de serviço a contratos de serviço ou ordens de serviço para descrever a tarefa de serviço que deverá ser concluída para o contrato ou a ordem."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0892161605401420c0817b3b644271357446a99b
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-task-relations"></a>Criar relações de tarefas de serviço    

[!include [banner](../includes/banner.md)]

Você pode associar tarefas de serviço a contratos de serviço ou ordens de serviço para descrever a tarefa de serviço que deverá ser concluída para o contrato ou a ordem. Essas informações estão disponíveis para técnicos de serviço e clientes.

## <a name="create-a-relation-with-a-service-agreement"></a>Criar uma relação com um contrato de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.

2.  Selecione um contrato de serviço existente ou crie um novo.

3.  No Painel de Ações, clique no botão **Tarefas de serviço**.

4.  No formulário **Tarefas de serviço**, pressione CTRL+N para criar uma nova linha e selecione uma tarefa de serviço na lista **Tarefa de serviço** para anexar a tarefa de serviço ao contrato de serviço.

5.  Na guia **Descrição**, insira todas as descrições de observações internas ou externas nos campos de texto livre.

6.  Feche o formulário para salvar o registro.

Repita este procedimento até ter criado todas as relações de tarefas de serviço necessárias para o contrato de serviço. Agora, você pode especificar essas tarefas de serviço para qualquer linha do contrato de serviço em anexo.

Uma relação de tarefas de serviço que é criada em um contrato de serviço está disponível a partir de todas as ordens de serviço anexadas ao contrato de serviço.

## <a name="create-a-relation-with-a-service-order"></a>Criar uma relação com uma ordem de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.

2.  Selecione uma ordem de serviço existente ou crie uma nova.

3.  No Painel de Ações, clique no botão **Tarefas de serviço**.

4.  No formulário **Tarefas de serviço**, pressione CTRL+N para criar uma nova linha e selecione uma tarefa de serviço na lista **Tarefa de serviço** para anexar as tarefas de serviço à ordem de serviço.

5.  Na guia **Descrição**, insira todas as descrições de observações internas ou externas nos campos de texto livre.

6.  Feche o formulário para salvar o registro.

Repita este procedimento até ter criado todas as relações de tarefas de serviço necessárias para a ordem de serviço. Agora, você pode selecionar a tarefa de serviço para a qual você criou a relação ao criar linhas da ordem de serviço.

As relações de tarefas de serviço que são criadas em uma ordem de serviço estão disponíveis na ordem de serviço específica.

## <a name="see-also"></a>Consulte também

[Tarefas de serviço](service-tasks.md)


  



