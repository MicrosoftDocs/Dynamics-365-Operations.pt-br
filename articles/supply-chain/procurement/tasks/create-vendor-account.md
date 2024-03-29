---
title: Criar uma conta de fornecedor
description: Este procedimento mostra como criar uma conta de fornecedor, e adicionar um endereço e as informações de contato.
author: GalynaFedorova
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 34c6d14923bcfdbcbeffc44a5fd08286c60bfc13
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673848"
---
# <a name="create-a-vendor-account"></a>Criar uma conta de fornecedor

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar uma conta de fornecedor, e adicionar um endereço e as informações de contato. O procedimento não mostra como preencher todos os campos para fins financeiros e de compra. Para obter mais informações sobre esses campos, por favor leia as descrições dos campos. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados. As contas de fornecedor são criadas tipicamente por um profissional de aquisição ou por equipes de contas a receber.


## <a name="create-a-vendor-account"></a>Criar uma conta de fornecedor
1. Acesse **Painel de Navegação > Módulos > Compras e fornecimento > Fornecedores > Todos os fornecedores**.
2. Clique em **Novo**.
3. No campo **Conta de fornecedor**, insira um valor.
    - O valor pode ser preenchido automaticamente. Nesse caso, é possível ignorar esta etapa.  
    - Você pode criar contas de fornecedor para uma pessoa ou uma organização. Isso irá afetar quais campos estão disponíveis. Neste exemplo, iremos criar uma conta de fornecedor para uma organização.   
4. No campo **Nome**, insira ou selecione um valor. Se o seu fornecedor já é um participante registrado no seu sistema, você pode usar o botão suspenso e selecioná-los nesse campo e a nova conta de fornecedor herdará as informações de endereço e contato já registradas.
5. No campo **Grupo**, insira ou selecione um valor. O grupo de fornecedores é usado para agrupar fornecedores que têm qualquer dos seguintes parâmetros em comum: condições de pagamento; período de liquidação; contas contábeis de lançamento de estoque, incluindo o grupo de impostos; contas contábeis padrão; códigos de filtro de produto ou configuração de previsão de fornecimento.
6. No campo **Número de funcionários**, insira um número.
7. No campo **Número da organização**, digite um valor.

## <a name="add-an-address"></a>Adicionar um endereço
1. Expanda a seção **Endereços**.
2. Clique em **Adicionar**.
3. No campo **Finalidade**, insira ou selecione um valor. Você pode selecionar um ou mais motivos. Esses são usados para selecionar o endereço correto para uma finalidade específica. Por exemplo, se a finalidade for "Nota fiscal", esse endereço será usado ao enviar notas fiscais.
4. No campo **Nome ou Descrição**, digite um valor.
5. No campo **País/região**, insira ou selecione um valor. Insira os detalhes do endereço. O país/região selecionado irá determinar os campos que serão apresentados, correspondente ao formato de endereço para o país/região. 
6. Clique em **OK**.

## <a name="add-contact-information"></a>Adicionar informações de contato
1. Expanda a seção **Informações do contato**.
2. Clique em **Adicionar**.
3. No campo **Descrição**, digite um valor.
4. No campo **Tipo**, selecione uma opção.
5. No campo **Número/endereço do contato**, digite um valor. Você pode selecionar a caixa de seleção Principal se este for o contato primário.  
6. Clique em **Salvar**.
7. Feche a página.
8. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]