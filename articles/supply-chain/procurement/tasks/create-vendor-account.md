---
title: Criar uma conta de fornecedor
description: Este procedimento mostra como criar uma conta de fornecedor, e adicionar um endereço e as informações de contato.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 22c7a1a2b7468f00aa25a67a2c5f62b088e2fe7c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546170"
---
# <a name="create-a-vendor-account"></a>Criar uma conta de fornecedor

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar uma conta de fornecedor, e adicionar um endereço e as informações de contato. O procedimento não mostra como preencher todos os campos para fins financeiros e de compra. Para obter mais informações sobre esses campos, por favor leia as descrições dos campos. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados. As contas de fornecedor são criadas tipicamente por um profissional de aquisição ou por equipes de contas a receber.


## <a name="create-a-vendor-account"></a>Criar uma conta de fornecedor
1. Vá para Aquisição e fornecimento > Fornecedores > Todos os fornecedores.
2. Clique em Novo.
3. No campo Conta de fornecedor, insira um valor.
    * O valor pode ser preenchido automaticamente. Nesse caso, é possível ignorar esta etapa.  
    * Você pode criar contas de fornecedor para uma pessoa ou uma organização. Isso irá afetar quais campos estão disponíveis. Neste exemplo, iremos criar uma conta de fornecedor para uma organização.   
4. No campo Nome, insira ou selecione um valor.
    * Se o seu fornecedor já é um participante registrado no seu sistema, você pode usar o botão suspenso e selecioná-los nesse campo e a nova conta de fornecedor herdará as informações de endereço e contato já registradas.  
5. No campo Grupo, insira ou selecione um valor.
    * O grupo de fornecedores é usado para agrupar fornecedores que têm qualquer um dos seguintes parâmetros em comum: Condições de pagamento; período de liquidação; contas contábeis de lançamento de estoque - incluindo o grupo de impostos sobre vendas; contas contábeis padrão; códigos de filtro de produto ou configuração de previsão de fornecimento.  
6. No campo Número de funcionários, insira um número.
7. No campo Número da organização, digite um valor.

## <a name="add-an-address"></a>Adicionar um endereço
1. Expanda a seção Endereços.
2. Clique em Adicionar.
3. No campo Motivo, insira ou selecione um valor.
    * Você pode selecionar um ou mais motivos. Esses são usados para selecionar o endereço correto para uma finalidade específica. Por exemplo, se a finalidade for "Nota fiscal", esse endereço será usado ao enviar notas fiscais.  
4. No campo Nome ou Descrição, digite um valor.
5. No campo País/região, insira ou selecione um valor.
    * Insira os detalhes do endereço. O país/região selecionado irá determinar os campos que serão apresentados, correspondente ao formato de endereço para o país/região.   
6. Clique em OK.

## <a name="add-contact-information"></a>Adicionar informações de contato
1. Clique em Adicionar.
2. No campo Descrição, digite um valor.
3. No campo Tipo, selecione uma opção.
4. No campo Número/endereço de contato, digite um valor.
    * Você pode selecionar a caixa de seleção Principal se este for o contato primário.  
5. Clique em Salvar.
6. Feche a página.
7. Feche a página.

